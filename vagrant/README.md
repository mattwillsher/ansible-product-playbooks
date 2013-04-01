Vagrant playbook
================

This playbook is for managing vagrant. 

create_ansible_dev_env.yml
-------------------

TODO: Do full vagrant setup and install for MacOS & Linux

This playbook is designed to set up a vagrant environment in the root of the repo checkout in the vagrant/ folder (which is in .gitignore). To use it, call it with a suitable inventory from the inventory folder:

e.g.

```
ansible-playbook -i playbooks/vagrant/inventory/ubuntu-12.04-amd64-cloudimg.ini playbooks/vagrant/create_ansible_dev_env.yml
```

```
ansible-playbook -i playbooks/vagrant/inventory/centos-6.4-x86_64.ini playbooks/vagrant/create_ansible_dev_env.yml
```

The Vagrantfile will be populated with a box name and URL. A folder vagrant is create in the root of the checked out repository. 

Note that if the same play is run twice any changes could be overwritten. For this reason, consider using the -e vagrantdir in your playbook call.

Parameters
----------

The following parameters can be specified on the command line or in an inventory file:

* vagrantdir - directory name in which the various files for this installation are placed. e.g. ubuntu-12.04-amd64
* vagrantbox - the name of vagrant box to use. e.g. precise-server-cloudimg-vagrant-amd64-disk1
* vagrantboxurl - the URL to download the vagrant box from if not present as the name given in $vagrantbox.
* vagranthostonlyip - Host only IP to allocate to the Vagrant box.

e.g

```
ansible-playbook -i playbooks/vagrant/inventory/centos-6.4-x86_64.ini \
playbooks/vagrant/create_ansible_dev_env.yml \
-e vagrantdir=mydevvm \
-e vagranthostonlyip=192.168.33.200
```

Will create a new CentOS 6.4 x86_64 VM with a host only IP of 192.168.33.200 and an appropriate inventory file in the vagrant/mydevvm directory.
