# Challenge n° 1 - Installation d'Ansible sur Ubuntu

## Objectif

Installer Ansible sur une VM Ubuntu en utilisant le paquet officiel fourni par la distribution.

## Énoncé du challenge

- Démarrez la VM `ubuntu` depuis le répertoire `atelier-01`.
- Connectez-vous à cette VM.
- Rafraîchissez les informations sur les paquets.
- Recherchez le paquet `ansible` avec les options qui vont bien.
- Installez le paquet officiel fourni par la distribution.
- Vérifiez si l'installation s'est bien déroulée.
- Notez la version d'Ansible.
- Déconnectez-vous et supprimez la VM.

## Solution

### Démarrage de la VM

Démarrez la VM Ubuntu :

```
$ vagrant up ubuntu
```

### Connexion à la VM

Connectez-vous à cette VM :

```
$ vagrant ssh ubuntu
```

### Mise à jour des informations sur les paquets

Rafraîchissez les informations sur les paquets :

```
$ sudo apt update
```

### Recherche du paquet Ansible

Recherchez le paquet `ansible` avec les options appropriées :

```
$ apt search ansible
Sorting... Done
Full Text Search... Done
ansible/jammy 2.10.7+merged+base+2.10.8+dfsg-1 all
  Configuration management, deployment, and task execution system

ansible-core/jammy-updates 2.12.0-1ubuntu0.1 all
  Configuration management, deployment, and task execution system

ansible-lint/jammy 5.4.0-2 all
  lint tool for Ansible playbooks

ansible-mitogen/jammy 0.3.1-3 all
  Fast connection strategy for Ansible

ara-client/jammy 1.5.7-1 all
  ARA Records Ansible - Client

ara-server/jammy 1.5.7-1 all
  ARA Records Ansible - Server

podman-toolbox/jammy 0.0.99.2-2ubuntu1 amd64
  unprivileged development environment using containers

python-ansible-runner-doc/jammy 2.1.1-1 all
  library that interfaces with Ansible (docs)

python-ara-doc/jammy 1.5.7-1 all
  ARA Records Ansible - doc

python-network-runner-doc/jammy 0.2.2-2 all
  abstraction of Ansible for interaction with networking devices (docs)

python-networking-ansible-doc/jammy 17.0.0-2 all
  OpenStack virtual network service - Ansible plugin (docs)

python3-ansible-runner/jammy 2.1.1-1 all
  library that interfaces with Ansible (Python 3.x)

python3-ara/jammy 1.5.7-1 all
  ARA Records Ansible

python3-network-runner/jammy 0.2.2-2 all
  abstraction of Ansible for interaction with networking devices (Python 3.x)

python3-networking-ansible/jammy 17.0.0-2 all
  OpenStack virtual network service - Ansible plugin (Python 3.x)

python3-reclass/jammy 1.7.0-1.1 all
  hierarchical inventory backend for configuration management systems

reclass/jammy 1.7.0-1.1 all
  hierarchical inventory backend for configuration management systems

reclass-doc/jammy 1.7.0-1.1 all
  reclass documentation

shade-inventory/jammy 1.31.0-0ubuntu2 all
  Ansible inventory script for OpenStack clouds

vim-syntastic/jammy 3.10.0-2 all
  Syntax checking hacks for vim
```

### Installation d'Ansible

Installez le paquet officiel fourni par la distribution :

```
$ sudo apt install -y ansible
```

### Vérification de l'installation

Vérifiez si l'installation s'est bien déroulée :

```
$ ansible --version
ansible 2.10.8
  config file = None
  configured module search path = ['/home/vagrant/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.10.12 (main, Aug 15 2025, 14:32:43) [GCC 11.4.0]
```

**Version d'Ansible installée :** `2.10.8`

### Déconnexion et suppression de la VM

Quittez la VM :

```
$ exit
logout
Connection to 127.0.0.1 closed.
```

Supprimez la VM :

```
$ vagrant destroy -f ubuntu
==> ubuntu: Forcing shutdown of VM...
==> ubuntu: Destroying VM and associated drives...
```

## Conclusion

Le paquet `ansible` version **2.10.8** a été installé avec succès depuis les dépôts officiels d'Ubuntu Jammy (22.04).

