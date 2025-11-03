# Challenge 3

Lancez une VM Rocky Linux et installez Ansible en utilisant PIP et Virtualenv.

$ vagrant up rocky
$ vagrant ssh rocky
$ sudo dnf update
$ sudo dnf install -y python3-pip
$ python3 -m venv ~/.venv/ansible
$ source ~/.venv/ansible/bin/activate
(ansible) [vagrant@rocky ~] $ pip install --upgrade pip
(ansible) [vagrant@rocky ~] $ pip install ansible
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

(ansible) $ deactivate
$ exit
$ vagrant destroy -f
