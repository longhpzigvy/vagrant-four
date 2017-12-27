## Usage

1. Install at least the following software
   - [Vagrant](https://www.vagrantup.com/downloads)
   - Oracle virtualbox
   - Ansible
   - git
   - openssh

1. Clone this repository

1. `vagrant up` 

## Windows

Ansible is not supported on Windows. The current solution is to bring up the virtual machine without provisioning, then just have the virtual machine provision itself.

### Obtaining a sane environment

At a minimum, you need git and ssh. Your options are:

1. Install Cygwin. `git` and `openssh` are available through Cygwin
2. Install the official git client for windows, which includes an implementation of `bash` and `ssh` as well as `git`

### Provisioning

1. Remove the provisioning line from `Vagrantfile`
2. `vagrant up`
3. install `ansible` within the virtual machine
   1. `sudo apt-get update && sudo apt-get install python2.7-dev python-pip sshpass`
   2. `sudo pip install ansible`
   3. Create `/etc/ansible/hosts` with a single line containing the string `localhost`
   4. `ansible-playbook -k /vagrant/provisioning/playbook.yml`
