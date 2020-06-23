# development environment and Vagrant 101

### What is an environment
A location where code is executed.

### What is a dev environment

### The 4 pillars of DevOps
- Cost
- Robustness
- Ease of use
- Flexibility 
### DevOps problems and solutions


## Vagrant and Virtual box

## Vagrant
Is a



## commands used in bash
1. Setting up VM (Virtual machine)
```
vagrant init ubuntu/xenial64
```
This lets oracle VirtualBox know which version of Linux to download and use.




2. Running the VM
```
vagrant up
```
This runs the virtual box using the ubuntu/xenial64.
which is a flavour (or a version) of Linux

2.1
```
vagrant plugin install vagrant-hostsupdater
```
This lets you change the name of the ip address.
In this case we want to change it into development.local

To do this open up vagrantfile in folder using atom
and adding the line:
```
config.hostsupdater.aliases = ["devolopment.local"]
```
In the end it should look like this.
```
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.10.100"

  # Make sure you first:
  # vagrant plugin install vagrant-hostsupdater

  config.hostsupdater.aliases = ["devolopment.local"]


end
```

3. Getting in to the VM's terminal
```
vagrant ssh
```
This switch to VM's terminal.

4. Updating ubuntu
```
sudo apt-get update -y
```
The ubuntu you download is not the latest version.
This will update it

5. Installing nginx
```
sudo apt-get install nginx -y
```
installs nginx

6. strat nginx
```
sudo systemctl start nginx
```
vagrant plugin install vagrant-hostsupdater
