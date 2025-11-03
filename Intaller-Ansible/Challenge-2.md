Répétez le challenge précédent en configurant un dépôt PPA (Personal Package Archive) pour Ansible :

$ sudo apt-add-repository ppa:ansible/ansible

Notez la version fournie par ce dépôt tiers et comparez avec la version officielle du challenge précédent.


$ vagrant up ubuntu
$ vagrant ssh ubuntu
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt update 
vagrant@ubuntu:~$ sudo apt search --names-only ansible
Sorting... Done
Full Text Search... Done
ansible/jammy 10.7.0-1ppa~jammy all
  Ansible collections for ansible-core

ansible-core/jammy 2.17.14-1ppa~jammy all
  Ansible IT Automation

$ sudo apt install ansible/jammy

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

