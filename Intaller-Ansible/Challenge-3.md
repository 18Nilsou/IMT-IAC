# Challenge n° 3 - Installation d'Ansible avec PIP et Virtualenv

## Objectif

Installer Ansible sur une VM Rocky Linux en utilisant PIP (Package Installer for Python) et Virtualenv pour créer un environnement virtuel isolé.

## Énoncé du challenge

Lancez une VM Rocky Linux et installez Ansible en utilisant PIP et Virtualenv.

## Contexte

L'utilisation de Virtualenv permet d'éviter de polluer le système avec des paquets Python et de créer un environnement isolé pour Ansible.

**Note :** Contrairement à Debian, le paquet `python3-venv` n'est pas nécessaire sur Rocky Linux, car Virtualenv fait partie des modules standard de Python dans cette distribution.

## Solution

### Démarrage de la VM

Démarrez la VM Rocky Linux :

```
$ vagrant up rocky
```

### Connexion à la VM

Connectez-vous à cette VM :

```
$ vagrant ssh rocky
```

### Mise à jour du système

Mettez à jour le système :

```
$ sudo dnf update
```

### Installation de PIP

Installez PIP (Package Installer for Python) :

```
$ sudo dnf install -y python3-pip
```

### Initialisation de l'environnement Virtualenv

Créez un environnement virtuel pour Ansible :

```
$ python3 -m venv ~/.venv/ansible
```

**Nommer l'environnement virtuel**

Le nom du répertoire est une convention et peut être choisi librement. Dans ce cas, nous utilisons `ansible` pour indiquer clairement le contexte.

### Activation de Virtualenv

Lancez l'environnement virtuel :

```
$ source ~/.venv/ansible/bin/activate
(ansible) [vagrant@rocky ~]$
```

Le prompt change pour indiquer que vous êtes maintenant dans l'environnement virtuel `(ansible)`.

### Mise à jour de PIP

Mettez à jour PIP pour cette première utilisation :

```
(ansible) [vagrant@rocky ~]$ pip install --upgrade pip
```

### Installation d'Ansible

Installez Ansible dans l'environnement virtuel :

```
(ansible) [vagrant@rocky ~]$ pip install ansible
```

### Vérification de l'installation

Vérifiez si l'installation s'est bien déroulée :

```
(ansible) [vagrant@rocky ~]$ ansible --version
ansible [core 2.15.13]
  config file = None
  configured module search path = ['/home/vagrant/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /home/vagrant/.venv/ansible/lib64/python3.9/site-packages/ansible
  ansible collection location = /home/vagrant/.ansible/collections:/usr/share/ansible/collections
  executable location = /home/vagrant/.venv/ansible/bin/ansible
  python version = 3.9.21 (main, Aug 19 2025, 00:00:00) [GCC 11.5.0 20240719 (Red Hat 11.5.0-5)] (/home/vagrant/.venv/ansible/bin/python3)
  jinja version = 3.1.6
  libyaml = True
```

**Version d'Ansible installée :** `ansible [core 2.15.13]`

Notez que l'emplacement d'Ansible pointe bien vers l'environnement virtuel : `/home/vagrant/.venv/ansible/`

### Désactivation de l'environnement virtuel

Quittez l'environnement Virtualenv :

```
(ansible) $ deactivate
```

### Déconnexion et suppression de la VM

Quittez la VM :

```
$ exit
```

Supprimez la VM :

```
$ vagrant destroy -f rocky
```

## Conclusion

L'installation d'Ansible via PIP et Virtualenv offre plusieurs avantages :

- **Isolation** : L'environnement virtuel isole Ansible du système
- **Version récente** : La version **2.15.13** est plus récente que celle des dépôts officiels
- **Flexibilité** : Possibilité d'avoir plusieurs versions d'Ansible sur la même machine
- **Portabilité** : Fonctionne sur toutes les distributions Linux avec Python

Cette méthode est particulièrement utile lorsque :
- Votre distribution ne propose pas de paquet Ansible
- Le paquet disponible est obsolète
- Les dépôts tiers ne sont pas une option
