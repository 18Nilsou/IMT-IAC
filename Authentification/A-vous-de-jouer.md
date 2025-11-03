# Authentification sur les Target Hosts - À vous de jouer !

## Objectif

Mettre en place l'authentification SSH par clé sur trois machines Ubuntu pour permettre à Ansible de s'y connecter sans mot de passe.

## Énoncé du challenge

Placez-vous dans le répertoire du troisième atelier pratique et configurez l'authentification SSH pour réussir un `ping` Ansible sur les trois Target Hosts.

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

### Vérification de l'installation d'Ansible

Vérifiez qu'Ansible est déjà installé sur cette machine :

```
vagrant@control:~$ type ansible
ansible is /usr/bin/ansible
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
```

### Test de connectivité réseau

Testez la connectivité de base vers les Target Hosts :

```
vagrant@control:~$ for HOST in target01 target02 target03; do ping -c 1 -q $HOST; done

PING target01.sandbox.lan (192.168.56.20) 56(84) bytes of data.

--- target01.sandbox.lan ping statistics ---
1 packets transmitted, 1 received, 0% packet loss, time 0ms
rtt min/avg/max/mdev = 0.422/0.422/0.422/0.000 ms
PING target02.sandbox.lan (192.168.56.30) 56(84) bytes of data.

--- target02.sandbox.lan ping statistics ---
1 packets transmitted, 1 received, 0% packet loss, time 0ms
rtt min/avg/max/mdev = 0.537/0.537/0.537/0.000 ms
PING target03.sandbox.lan (192.168.56.40) 56(84) bytes of data.

--- target03.sandbox.lan ping statistics ---
1 packets transmitted, 1 received, 0% packet loss, time 0ms
rtt min/avg/max/mdev = 0.498/0.498/0.498/0.000 ms
```

### Collecte des clés SSH publiques des Target Hosts

Collectez les clés SSH publiques des Target Hosts pour les ajouter au fichier `known_hosts` :

```
vagrant@control:~$ ssh-keyscan -t rsa target01 target02 target03 >> .ssh/known_hosts
# target02:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target01:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target03:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
```

### Test de connexion SSH

Testez la connexion SSH vers un Target Host (nécessite le mot de passe `vagrant`) :

```
vagrant@control:~$ ssh target01
vagrant@target01's password: 
Welcome to Ubuntu 22.04.5 LTS (GNU/Linux 5.15.0-160-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro
```

Quittez la session SSH pour revenir au Control Host.

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
SHA256:Zs8Aqzgndi2NLzT2ySpvYVzAdTKQyQ4H2Uep72rX31k vagrant@control
The key's randomart image is:
+---[RSA 3072]----+
|  .*.*=..        |
|  o O o+         |
|   + +.          |
|    o .o         |
|   . o. S        |
|   .B=.o +       |
|  =+**oo  o   E  |
| ..=+o* .  . o   |
|   =+=.  .. o    |
+----[SHA256]-----+
```

### Distribution de la clé publique sur les Target Hosts

Distribuez la clé publique sur chaque Target Host en fournissant le mot de passe `vagrant` :

```
vagrant@control:~$ ssh-copy-id vagrant@target01
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target01's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target01'"
and check to make sure that only the key(s) you wanted were added.
```

Répétez l'opération pour les autres Target Hosts :

```
vagrant@control:~$ ssh-copy-id vagrant@target02
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target02's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target02'"
and check to make sure that only the key(s) you wanted were added.

vagrant@control:~$ ssh-copy-id vagrant@target03
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/vagrant/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
vagrant@target03's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'vagrant@target03'"
and check to make sure that only the key(s) you wanted were added.
```

### Test avec Ansible

Un `ping` Ansible permet de tester le bon fonctionnement de l'authentification sur les Target Hosts :

```
vagrant@control:~$ ansible all -i target01,target02,target03 -m ping
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

## Résultat

✅ L'authentification par clé SSH est correctement configurée sur les trois Target Hosts.

✅ Ansible peut se connecter sans mot de passe à toutes les machines.

✅ Le module `ping` d'Ansible retourne `SUCCESS` pour chaque hôte.

## Conclusion

L'authentification par clé SSH est une méthode sécurisée et pratique pour permettre à Ansible de gérer des machines distantes. Les étapes clés sont :

1. **Configuration DNS locale** via `/etc/hosts`
2. **Collecte des clés d'hôtes** avec `ssh-keyscan`
3. **Génération de la paire de clés** avec `ssh-keygen`
4. **Distribution de la clé publique** avec `ssh-copy-id`
5. **Validation** avec une commande Ansible `ping`

Cette configuration permet désormais d'exécuter des commandes Ansible sur les Target Hosts sans interaction manuelle.

