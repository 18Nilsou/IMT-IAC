# A vous de jouer

$ vagrant up
$ vagrant ssh controle
vagrant@control:~$ vim /etc/hosts
vagrant@control:~$ sudo vim /etc/hosts
vagrant@control:~$ cat /etc/hosts
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

vagrant@control:~$ ssh-keyscan -t rsa target01 target02 target03 >> .ssh/known_hosts
# target02:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target01:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13
# target03:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.13

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


vagrant@control:~$ ssh-copy-id vagrant@target01;ssh-copy-id vagrant@target02;ssh-copy-id vagrant@target03
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

vagrant@control:~$ sudo apt update
vagrant@control:~$ sudo apt install ansible

vagrant@control:~$ ansible --version
ansible 2.10.8

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


vagrant@control:~$ mkdir monprojet
vagrant@control:~/monprojet$ touch ansible.cfg

vagrant@control:~/monprojet$ ansible --version
ansible 2.10.8
  config file = /home/vagrant/monprojet/ansible.cfg

vagrant@control:~/monprojet$ cat ansible.cfg
[defaults]
inventory = ./hosts
vagrant@control:~/monprojet$ cat hosts
[target]
target01
target02
target03


vagrant@control:~/monprojet$ mkdir ~/journal
vagrant@control:~/monprojet$ touch ~/journal/ansible.log
vagrant@control:~/monprojet$ cat ansible.cfg
[defaults]
inventory = ./hosts
log_path = ~/journal/ansible.log


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


vagrant@control:~/monprojet$ cat hosts 
[target]
target01
target02
target03

[testlab]
target01
target02
target03

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
vagrant@control:~/monprojet$ ansible all -a "head -n 1 /etc/shadow"
target01 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::
target02 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::
target03 | CHANGED | rc=0 >>
root:*:19977:0:99999:7:::


vagrant@control:~/monprojet$ exit
logout
Connection to 127.0.0.1 closed.
[ema@localhost:atelier-06] $ vagrant destroy -f
