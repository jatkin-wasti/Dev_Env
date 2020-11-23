# First Virtual Box, Vagrant Dev Environment

This repo is our first virtual environment to create a dev environment

## Linux distros
- Ubuntu - an opensource OS
- Ubuntu with GUI (Graphical User Interface) - Looks like a desktop and works
like opensource
- Ubuntu headless - Terminal UI (This is the one we will use)
  - Faster
  - More secure
  - Lighter
## Virtual Box
- Opensource software that can be used for virtualisation
- It creates VMs (Virtual Machines) to run another OS
- OS where it runs is the **host** OS
- OS running in the VM is the **guest** OS

## Vagrant
- Tool to manage virtual machines

- Vagrant boxes - pre loaded vagrant files that create virtual machines. Usually
just an OS (Operating System)

### Main commands
- ```vagrant init``` This intialises the current directory to be a Vagrant
environment and creating an initial Vagrantfile if one does not exist already
- ```vagrant init <box>``` Replace <box> with the given distribution you want
to install to create a Vagrantfile for that distribution. Can look up boxes at
https://app.vagrantup.com/
- ```vagrant up``` This creates and configures guest machines according to your
Vagrantfile so that we can actually use the machine
- ```vagrant destroy``` This stops the running virtual machine and destroys all
resources that were created during the machine creation process
- ```vagrant ssh``` This will ssh (essentially access the machine over a
  network) into a running vagrant machine, giving access through a shell
- ```exit``` to leave the guest machines shell and take you back to your
regular host terminal
- ```vagrant halt``` This will suspend the development of or stop the virtual
machines

## Task 1
- Vagrant up with ubuntu/xenial64
- Vagrant destroy
- Delete your Vagrantfile
- Use vagrant init to create Vagrantfile with centos 7
- vagrant up again
- vagrant destroy

## Task 2
- Create a vagrant box with ubuntu version 10.04
- Find the command to SSH into the machine
  - starts with vagrant
  - you want to ssh
- Create a README.md file inside machine and write your name and your favourite
movie
