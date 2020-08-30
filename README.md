## Purpose ##

Provide reproducible environments for Anki development.

> Currently provides only a virtual machine but will be extended to produce a 
> Dockerfile as well.

This is an, as of yet, not incredibly well thought out Vagrantfile and Ansible 
playbook that provisions an Ubuntu VirtualBox with a lightweight Lubuntu desktop.
This emerged as a byproduct of my interest in learning about Vagrant, VirtualBox, 
Ansible, and Anki development. The Vagrantfile uses Ansible for the following:

- Installs system dependencies required to install Anki from source
- Builds Anki from source
- Installs a few goodies for a better development experience

Please take a look at `playbook.yml` and `Vagrantfile` for details.  YMMV!

Take a look at the lines I've commented out in `Vagrantfile` for examples on how 
to synchronize local folders into the VM.

## Prerequisites ##

 - Install VirtualBox, Vagrant, and Ansible.
 - Clone Anki into this repo's parent directory, i.e., `../anki`
   - This is important as the Vagrantfile and playbook assumes that is where 
     Anki's source code will be.

## Usage ##

 - Run `vagrant up --provision` in this repo.
 - Login as user vagrant and password vagrant

## TODO ##

- Install other goodies into Anki's virtual environment
- include some test add-ons
- Install PyCharm?
- Replicate to produce a Dockerfile
