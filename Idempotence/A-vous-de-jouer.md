# Ansible et l'idempotence - À vous de jouer !

## Objectif

Se familiariser avec la notion d'idempotence en exécutant une série de tâches administratives sur toutes les machines cibles, en observant les différences entre la première et la deuxième exécution.

## Énoncé du challenge

Pour vous familiariser avec la notion d'idempotence, exécutez une série de tâches administratives sur toutes les machines cibles. Prenez soin d'exécuter chaque commande deux fois et observez ce qui se passe dans l'affichage du résultat.

- Installez successivement les paquets `tree`, `git` et `nmap` sur toutes les cibles
- Désinstallez successivement ces trois paquets en utilisant le paramètre supplémentaire `state=absent`
- Copiez le fichier `/etc/fstab` du Control Host vers tous les Target Hosts sous forme d'un fichier `/tmp/test3.txt`
- Supprimez le fichier `/tmp/test3.txt` sur les Target Hosts en utilisant le module `file` avec le paramètre `state=absent`
- Enfin, affichez l'espace utilisé par la partition principale sur tous les Target Hosts. Que remarquez-vous ?

## Contexte

Se placer dans le répertoire du projet :

```
[vagrant@ansible ~]$ cd ansible/projets/ema/
```

## Solution

### Installation du paquet tree

#### Première exécution - Installation

```
[vagrant@ansible ema]$ ansible all -m package -a "name=tree"
```

**Résultat résumé :**
- **suse** : `CHANGED`  - Le paquet `tree 2.0.2-1` a été installé
- **rocky** : `SUCCESS`  - Le paquet était déjà présent ("Nothing to do")
- **debian** : `CHANGED`  - Le paquet `tree 2.0.2-1` a été installé

#### Deuxième exécution - Idempotence

```
[vagrant@ansible ema]$ ansible all -m package -a "name=tree"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
debian | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
suse | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
```

**Observation :** 
- Toutes les machines retournent `SUCCESS` avec `"changed": false`
- L'idempotence fonctionne : le paquet étant déjà installé, aucune action n'est effectuée
-  **Principe d'idempotence respecté**

---

### Installation du paquet git

#### Première exécution

```
[vagrant@ansible ema]$ ansible all -m package -a "name=git"
```

**Résultat résumé :**
- **debian** : `SUCCESS` avec `"changed": false` (déjà installé)
- **suse** : `SUCCESS` avec `"changed": false` (déjà installé)
- **rocky** : `CHANGED`  - Installation de git-2.47.3 et ses dépendances

#### Deuxième exécution

```
[vagrant@ansible ema]$ ansible all -m package -a "name=git"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do"
}
suse | SUCCESS => {
    "changed": false
}
debian | SUCCESS => {
    "changed": false
}
```

**Observation :**  **Idempotence confirmée**

---

### Installation du paquet nmap

#### Première exécution

```
[vagrant@ansible ema]$ ansible all -m package -a "name=nmap"
```

**Résultat résumé :**
- **rocky** : `CHANGED`  - Installation de nmap-3:7.92-3.el9.x86_64
- **suse** : `CHANGED`  - Installation de nmap et dépendances (6113 kB)
- **debian** : `CHANGED`  - Installation de nmap et dépendances (6113 kB)

#### Deuxième exécution

```
[vagrant@ansible ema]$ ansible all -m package -a "name=nmap"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do"
}
debian | SUCCESS => {
    "changed": false
}
suse | SUCCESS => {
    "changed": false
}
```

**Observation :**  **Idempotence validée**

---

### Désinstallation des paquets

#### Suppression de nmap

```
[vagrant@ansible ema]$ ansible all -m package -a "name=nmap state=absent"
```

**Résultat :**
- Toutes les machines : `CHANGED`  - Paquet supprimé

#### Suppression de git

```
[vagrant@ansible ema]$ ansible all -m package -a "name=git state=absent"
```

**Résultat :**
- **rocky** : `CHANGED`  - Suppression de git et perl-Git
- **debian** : `CHANGED`  - Suppression de git (18.9 MB libérés)
- **suse** : `CHANGED`  - Suppression de git (18.9 MB libérés)

#### Suppression de tree

```
[vagrant@ansible ema]$ ansible all -m package -a "name=tree state=absent"
```

**Résultat :**
- Toutes les machines : `CHANGED`  - Paquet tree supprimé

---

### Copie de fichier

#### Préparation

```
[vagrant@ansible ema]$ cp /etc/fstab /tmp/test3.txt
[vagrant@ansible ema]$ cat /tmp/test3.txt

#
# /etc/fstab
# Created by anaconda on Fri Oct 24 19:39:48 2025
#
UUID=857c800e-4079-4023-b9be-38c4dc944806 /                       xfs     defaults        0 0
UUID=2635f2a2-b00d-4ea8-b7ae-83a0dbab13b1 none                    swap    defaults        0 0
#VAGRANT-BEGIN
vagrant /vagrant vboxsf uid=1000,gid=1000,_netdev 0 0
#VAGRANT-END
```

#### Copie vers les Target Hosts

```
[vagrant@ansible ema]$ ansible all -m copy -a "src=/etc/fstab dest=/tmp/test3.txt"
```

**Résultat :**
- **suse** : `CHANGED`  - Fichier copié (checksum: 0fe1d6..., 679 bytes)
- **debian** : `CHANGED`  - Fichier copié (md5sum: 31623c38...)
- **rocky** : `CHANGED`  - Fichier copié avec SELinux context

---

### Suppression de fichier

```
[vagrant@ansible ema]$ ansible all -m file -a "path=/tmp/test3.txt state=absent"
suse | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}
rocky | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}
debian | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}
```

---

### Affichage de l'espace disque

```
[vagrant@ansible ema]$ ansible all -m command -a "df -h /"
suse | CHANGED | rc=0 >>
Filesystem                         Size  Used Avail Use% Mounted on
/dev/mapper/ubuntu--vg-ubuntu--lv   31G  5.0G   24G  18% /

rocky | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        61G  2.0G   59G   4% /

debian | CHANGED | rc=0 >>
Filesystem                         Size  Used Avail Use% Mounted on
/dev/mapper/ubuntu--vg-ubuntu--lv   31G  5.0G   24G  18% /
```

### Observation importante

**Que remarquez-vous ?**

Toutes les machines retournent `CHANGED` même lors d'une deuxième exécution !

**Explication :** 
- Le module `command` n'est **PAS idempotent** par nature
- Il exécute simplement une commande et retourne toujours `changed: true`
- Contrairement aux modules `package`, `copy`, ou `file`, il ne vérifie pas l'état du système
- Il ne peut pas déterminer si l'exécution a modifié quelque chose

---

## Résumé des observations

| Module | Idempotent | Comportement |
|--------|------------|--------------|
| **package** |  Oui | Installe uniquement si absent |
| **copy** |  Oui | Copie uniquement si le fichier diffère |
| **file** |  Oui | Modifie uniquement si l'état diffère |
| **command** |  Non | Exécute toujours et retourne `CHANGED` |