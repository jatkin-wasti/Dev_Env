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
### Bash commands
- Inside linux machine we can use bash commands
- ```sudo``` lets you run commands as the admin
- ```ls```, ```ll```, ```cd```, ```mkdir```, ```rm```, ```rm -rf```, ```ls -a```
- ```apt-get``` is the package manager for ubuntu (can just use ```apt``` now)
- ```apt-get update``` updates the install list

## What is an environment
- The dependencies and systems that exist on a computer while developing for
that development to take place i.e. Operating System, IDE, databases etc.

## Why use VMs?
- Different developers may have different environments (could be different
  Operating Systems, different versions of the language, different IDE's etc)
- The developers may have different environments than the ones used to test the
code or the environments used by the user
- This means that what works on one persons machine may not work on someone
else's
- Having all developers develop in a virtual machine that matches the test and
target environment we can stop this issue from happening and increase
the speed at which code makes it into deployment

## Virtual Box
- Opensource software that can be used for virtualisation
- It creates VMs (Virtual Machines) to run another OS
- OS where it runs is the **host** OS
- OS running in the VM is the **guest** OS

## Vagrant
- Tool to manage virtual machines
- Vagrantfile is a file that specifies the environment to create, here is an
example of a Vagrantfile for ubuntu 18.04 (this can be switched for any distro)
```
Vagrant.configure("2") do |config|

  config.vm.box = "generic/ubuntu1804"
end
```
- Can also specify an ip address or url to connect to in the Vagrantfile (
  though this does require running ```vagrant plugin install hostspluginipdater```
   first)
```
config.vm.network "private_network", ip:"192.168.10.2"
config.vm.hostname = "www.jamie.local"
```
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
- ```vagrant suspend``` This will suspend the guest machine that vagrant is
managing, saving the current state of the machine so that it may be resumed
later
- ```vagrant halt``` This will stop the guest machine that vagrant is managing
- ```vagrant reload``` This will update the vagrant environment without
deleting it
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
