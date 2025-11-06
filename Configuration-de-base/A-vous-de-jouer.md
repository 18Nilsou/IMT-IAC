# Configuration de base - À vous de jouer !

## Énoncé du challenge

Le moment est venu de faire un petit atelier récapitulatif avec les tâches suivantes :

- Éditer `/etc/hosts` de manière à ce que les Target Hosts soient joignables par leur nom d'hôte simple
- Configurer l'authentification par clé SSH avec les trois Target Hosts
- Installer Ansible
- Envoyer un premier `ping` Ansible sans configuration
- Créer un répertoire de projet `~/monprojet`
- Créer un fichier vide `ansible.cfg` dans ce répertoire
- Vérifier si ce fichier est bien pris en compte par Ansible
- Spécifier un inventaire nommé `hosts`
- Activer la journalisation dans `~/journal/ansible.log`
- Tester la journalisation
- Créer un groupe `[testlab]` avec vos trois Target Hosts
- Définir explicitement l'utilisateur `vagrant` pour la connexion à vos cibles
- Envoyer un `ping` Ansible vers le groupe de machines `[all]`
- Définir l'élévation des droits pour l'utilisateur `vagrant` sur les Target Hosts
- Afficher la première ligne du fichier `/etc/shadow` sur tous les Target Hosts
- Quitter le Control Host et supprimer toutes les VM de l'atelier

## Environnement de l'atelier

Voici les quatre machines virtuelles Ubuntu 22.04 de cet atelier :

| Machine virtuelle | Adresse IP    |
|-------------------|---------------|
| control           | 192.168.56.10 |
| target01          | 192.168.56.20 |
| target02          | 192.168.56.30 |
| target03          | 192.168.56.40 |

## Solution

### Démarrage des VM

Démarrez toutes les machines virtuelles :

```
$ vagrant up
```

### Connexion au Control Host

Connectez-vous au Control Host :

```
$ vagrant ssh control
```

### Configuration de la résolution DNS locale

Éditez le fichier `/etc/hosts` pour ajouter les entrées des Target Hosts :

```
vagrant@control:~$ sudo vim /etc/hosts
```

Contenu du fichier `/etc/hosts` :

```
127.0.0.1 localhost
127.0.1.1 vagrant
192.168.56.20 target01.sandbox.lan target01
192.168.56.30 target02.sandbox.lan target02
192.168.56.40 target03.sandbox.lan target03

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
127.0.2.1 control control
```

### Collecte des clés SSH publiques des Target Hosts

Collectez les clés SSH publiques des Target Hosts :
```
vagrant@control:~$ ssh-keyscan -t rsa target01 target02 target03 >> .ssh/known_hosts
# target02:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target01:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target03:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
```

### Génération de la paire de clés SSH

Générez une paire de clés SSH en acceptant toutes les options par défaut :
```
vagrant@control:~$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/vagrant/.ssh/id_rsa
Your public key has been saved in /home/vagrant/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:vdHNc8XbfRhn/YqEW7hmeIzM2QLT/NeL+ZqDPef6j2c vagrant@control
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|               ..|
|              . *|
|       o . + o =*|
|      o S = + =.*|
|       = B B o +.|
|        B @oo o  |
|         =..++.oE|
|            *X*+.|
+----[SHA256]-----+
```

### Distribution de la clé publique sur les Target Hosts

Distribuez la clé publique sur les trois Target Hosts en utilisant une commande enchaînée :
```
vagrant@control:~$ ssh-copy-id vagrant@target01; ssh-copy-id vagrant@target02; ssh-copy-id vagrant@target03
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target01's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target01'"
and check to make sure that only the key(s) you wanted were added.

/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target02's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target02'"
and check to make sure that only the key(s) you wanted were added.

/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target03's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target03'"
and check to make sure that only the key(s) you wanted were added.
```

### Installation d'Ansible

Mettez à jour les paquets et installez Ansible :

```
vagrant@control:~$ sudo apt update
vagrant@control:~$ sudo apt install ansible
```

Vérifiez l'installation :

```
vagrant@control:~$ ansible --version
ansible 2.10.8
```

### Premier test sans configuration

Envoyez un `ping` Ansible sans configuration en spécifiant les hôtes directement :
```
vagrant@control:~$ ansible all -i target01,target02,target03 -m ping
target02 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target03 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target01 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```

L'authentification fonctionne correctement !

## Configuration du projet Ansible

### Création du répertoire de projet

Créez un répertoire de projet `~/monprojet` :

```
vagrant@control:~$ mkdir monprojet
vagrant@control:~$ cd monprojet
```

### Création du fichier de configuration

Créez un fichier `ansible.cfg` vide dans le répertoire du projet :
```
vagrant@control:~/monprojet$ touch ansible.cfg
```

### Vérification du fichier de configuration

Vérifiez si le fichier `ansible.cfg` est bien pris en compte par Ansible :

```
vagrant@control:~/monprojet$ ansible --version
ansible 2.10.8
  config file = /home/vagrant/monprojet/ansible.cfg
```

Le fichier de configuration est bien pris en compte !

### Configuration de l'inventaire

Spécifiez un inventaire nommé `hosts` dans le fichier `ansible.cfg` :

```
vagrant@control:~/monprojet$ cat ansible.cfg
[defaults]
inventory = ./hosts
```

Créez le fichier d'inventaire `hosts` avec un premier groupe :

```
vagrant@control:~/monprojet$ cat hosts
[target]
target01
target02
target03
```

### Configuration de la journalisation

Créez le répertoire pour les logs :

```
vagrant@control:~/monprojet$ mkdir ~/journal
vagrant@control:~/monprojet$ touch ~/journal/ansible.log
```

Activez la journalisation dans le fichier `ansible.cfg` :

```
vagrant@control:~/monprojet$ cat ansible.cfg
[defaults]
inventory = ./hosts
log_path = ~/journal/ansible.log
```

### Test de la journalisation

Testez la journalisation avec un `ping` Ansible :

```
vagrant@control:~/monprojet$ ansible all -i target01,target02,target03 -m ping
target02 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target01 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target03 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```

Vérifiez le contenu du fichier journal :

```
vagrant@control:~/monprojet$ cat ~/journal/ansible.log
2025-11-06 08:18:47,503 p=3402 u=vagrant n=ansible | target02 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
2025-11-06 08:18:47,514 p=3402 u=vagrant n=ansible | target01 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
2025-11-06 08:18:47,524 p=3402 u=vagrant n=ansible | target03 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```

La journalisation fonctionne correctement !

### Création du groupe testlab

Créez un groupe `[testlab]` dans le fichier `hosts` :

```
vagrant@control:~/monprojet$ cat hosts 
[target]
target01
target02
target03

[testlab]
target01
target02
target03
```

### Configuration de l'utilisateur

Définissez explicitement l'utilisateur `vagrant` pour la connexion aux Target Hosts :

```
vagrant@control:~/monprojet$ cat hosts
[target]
target01
target02
target03

[testlab]
target01
target02
target03

[testlab:vars]
ansible_user=vagrant
```

### Test du ping avec le groupe all

Envoyez un `ping` Ansible vers le groupe de machines `[all]` :

```
vagrant@control:~/monprojet$ ansible all -m ping
target01 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target03 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target02 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```

Le ping fonctionne sans avoir à spécifier l'inventaire !

### Configuration de l'élévation des droits

Définissez l'élévation des droits pour l'utilisateur `vagrant` sur les Target Hosts :

```
vagrant@control:~/monprojet$ cat hosts
[target]
target01
target02
target03

[testlab]
target01
target02
target03

[testlab:vars]
ansible_user=vagrant
ansible_become=yes
ansible_become_method=sudo
ansible_become_user=root
```

### Test de l'élévation des droits

Affichez la première ligne du fichier `/etc/shadow` sur tous les Target Hosts (nécessite des droits élevés) :

```
vagrant@control:~/monprojet$ ansible all -a "head -n 1 /etc/shadow"
target01 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::
target02 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::
target03 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::
```

L'élévation des droits fonctionne correctement !

### Nettoyage

Quittez le Control Host :

```
vagrant@control:~/monprojet$ exit
logout
Connection to 127.0.0.1 closed.
```

Supprimez toutes les VM de l'atelier :

```
$ vagrant destroy -f
```

## Résumé de la configuration

À l'issue de cet atelier, vous avez créé une configuration Ansible complète comprenant :

### Fichier `ansible.cfg`

```ini
[defaults]
inventory = ./hosts
log_path = ~/journal/ansible.log
```

### Fichier `hosts` (inventaire)

```ini
[target]
target01
target02
target03

[testlab]
target01
target02
target03

[testlab:vars]
ansible_user=vagrant
ansible_become=yes
ansible_become_method=sudo
ansible_become_user=root
```

## Conclusion

Cet atelier récapitulatif a permis de mettre en pratique les compétences suivantes :

**Authentification SSH** - Configuration des clés SSH pour un accès sans mot de passe

**Installation d'Ansible** - Installation du paquet depuis les dépôts Ubuntu

**Configuration de base** - Création d'un fichier `ansible.cfg` pour le projet

**Inventaire** - Définition des groupes et variables pour les Target Hosts

**Journalisation** - Activation des logs pour tracer les actions Ansible

**Élévation des droits** - Configuration de `sudo` pour les tâches administratives

Cette configuration de base est maintenant prête pour des tâches d'automatisation plus avancées avec Ansible !
