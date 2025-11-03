# Challenge n° 2 - Installation d'Ansible via un dépôt PPA

## Objectif

Installer Ansible sur une VM Ubuntu en utilisant un dépôt PPA (Personal Package Archive) tiers et comparer la version obtenue avec celle du dépôt officiel.

## Énoncé du challenge

Répétez le challenge précédent en configurant un dépôt PPA (Personal Package Archive) pour Ansible :

```
$ sudo apt-add-repository ppa:ansible/ansible
```

Notez la version fournie par ce dépôt tiers et comparez avec la version officielle du challenge précédent.

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

### Configuration du dépôt PPA

Ajoutez le dépôt PPA pour Ansible :

```
$ sudo apt-add-repository ppa:ansible/ansible
```

### Mise à jour des informations sur les paquets

Rafraîchissez les informations sur les paquets :

```
$ sudo apt update
```

### Recherche du paquet Ansible

Recherchez le paquet `ansible` avec l'option `--names-only` :

```
$ sudo apt search --names-only ansible
Sorting... Done
Full Text Search... Done
ansible/jammy 10.7.0-1ppa~jammy all
  Ansible collections for ansible-core

ansible-core/jammy 2.17.14-1ppa~jammy all
  Ansible IT Automation
```

### Installation d'Ansible

Installez Ansible depuis le dépôt PPA :

```
$ sudo apt install ansible/jammy
```

### Vérification de l'installation

Vérifiez si l'installation s'est bien déroulée :

```
$ ansible --version
ansible [core 2.17.14]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/vagrant/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /home/vagrant/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible
  python version = 3.10.12 (main, Aug 15 2025, 14:32:43) [GCC 11.4.0] (/usr/bin/python3)
  jinja version = 3.0.3
  libyaml = True
```

**Version d'Ansible installée :** `ansible [core 2.17.14]`

## Comparaison des versions

| Source | Version |
|--------|---------|
| **Dépôt officiel Ubuntu** | ansible 2.10.8 |
| **Dépôt PPA tiers** | ansible [core 2.17.14] |

## Conclusion

Le dépôt PPA `ppa:ansible/ansible` fournit une version beaucoup plus récente d'Ansible (**2.17.14**) comparée à la version du dépôt officiel Ubuntu (**2.10.8**). Cette différence significative permet d'utiliser les fonctionnalités les plus récentes d'Ansible, au prix d'une source de paquets tierce.

