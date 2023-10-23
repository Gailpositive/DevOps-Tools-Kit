## ANSIBLE
===============================================

# 0. Introduction and Overview of Ansible
=====================
www.doc.ansible.com
=====================
1. Ansible Installation
=====================

apt update
apt install ansible -y
ansible --version

yum update
yum install ansible -y   
ansible --version

ansible.cfg file priority
1.    ANSIBLE_CONFIG
2.    ./ansible.cfg
3.    ~/.ansible.cfg
4.    /etc/ansible/ansible.cfg (this is a configuration parth)
( Create ansible.cfg and inventory.txt (txt,init or yml) with the touch command)
ansible --version

============================================

====================
2. Ansible Setup
====================

#Setup controller and node server :
a. create user and give password
b. add user to sudoer's file in /etc/sudoers file | achiever   ALL=(ALL) NOPASSWD: ALL
c. switch to achiever user
d. show the connection methods
  password or ssh keys => generate keys | ssh-keygen
  ssh-copy-id
  copy .ssh/id_rsa.pub from controller to all node servers at .ssh/authorized_keys
  ssh agent

hostKeyChecking => disable

=======================
3. Ansible Module Commands ( ping / Copy, File, Setup, Shell, Apt and others )
=======================
ansible-doc -l
ansible-doc ping
ansible all -m ping
ansible all -m ping -i inventory
ansible host -m ping => host must be present in inventory files
#ansible all -m ping --list-hosts
#ansible all -m ping -o => condense output
ansible host1:host2 -m ping
ansible group1:group2 -m ping



ansible all -m copy -a "src=./hosts dest=/tmp"
ansible all -m copy -a "content='Ansible\n' dest=/tmp/hosts" => File will be create if not present
ansible all -m copy -a "content='Ansible\n' dest=/tmp/hosts backup=yes"

ansible all -m file -a "path=/tmp/tmp2 state=touch" => value of state must be one of: absent, directory, touch
ansible all -m file -a "path=/tmp/tmp3 state=touch mode=0777"
ansible all -m file -a "path=/etc/etc1 state=touch" => Permission denied
ansible all -m file -a "path=/etc/etc1 state=touch" -b OR --become

ansible all -m file -a "path=1 state=touch" -k  # Or --ask-pass
ansible all -m file -a "path=1 state=touch" -k -u newuser


Facts - Information about managed nodes like os dist, releaes, processor etc
ansible all -m setup
ansible all -m setup -a "filter=ansible_all_ipv4_addresses"


ansible all -m shell -a "uptime"
ansible all -m shell -a "free -m"

RHEL - yum
debian / ubuntu - apt
ansible all -m apt -a "name=git state=present" -b  => present | absent | latest


==================
4. Parallel:
==================
ansible all -m shell -a "sleep 5"
grep fork /etc/ansible/ansible.cfg
#forks          = 5

ansible all -m shell -a "sleep 5; echo hi"
controller | CHANGED | rc=0 >>
hi achiever
node | CHANGED | rc=0 >>
hi achiever

cat ansible.cfg
[defaults]
inventory      = ./hosts
host_key_checking = False
forks   = 1


============================================
5. Ansible Playbooks
============================================
ansible-playbook a.yaml
ansible-playbook a.yaml -v
ansible-playbook a.yaml --check
ansible-playbook a.yaml --syntax-check
Default verbosity is 0



============================================

6. Ansible Variables, Roles and Vault
============================================
cat hosts  | head
node ansible_ssh_pass=devops

[group1]
node

[group1:vars]
ansible_ssh_user=devops
ansible_ssh_pass=devops

[all:vars]
ansible_ssh_user=devops1
ansible_ssh_pass=devops1


ansible-vault -h
ansible-vault create 1.yaml
ansible-vault decrypt 1.yaml
ansible-vault edit 1.yaml
ansible-vault view 1.yaml
ansible-vault encrypt 1.yaml
ansible-vault rekey 1.yaml
ansible-playbook 1.yaml --ask-vault-pass
ansible-playbook 1.yaml --vault-password-file mypass
=
