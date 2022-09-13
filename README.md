# Vagrant-Ansible-Docker_Nginx
# @Author: Anand Dasari
# @Date  : 13-Sept-2022

# Description:
Demo code to showcase the Nginx serving a simple HTML page running in docker container on  Vagrant machine using Ansible provisioner.

Vagrant let's us run custom provisioners such as Puppet, Chef, Ansible, Salt, or Shell.
In this case we are using ansible as a provisioner.
The ansible provisioner includes 2 roles
  1. The first role install and start/enable docker service on the guest machine
  2. The second role creates a nginx docker container using library/alpine:latest as base image
The nginx process with in the continer run as nobody user and serves a sample "Hello World" page

Note: This vagrant  file uses vb-guest plugin , make sure it is installed  and an ip address from your host network range.

Once vagrant provisioning is completed, you can access the sample web page on port 80 of that ip.
eg., http://<ip-address>:80

Once Provisioning is succesful, this code also tests the response from nginx server  by running test task in playbook. which can be observed in Ansible log.

# Pre-requisites
Following tools should be available on local machine
a) VirtualBox
can get one suitable to your OS from https://www.virtualbox.org
b) Vagrant   ---  https://www.vagrantup.com
c) Ansible 

# How to run
Checkout/unzip this code into a local folder
cd to the directory where downloaded
run  vagrant command
> vagrant up --> this should take about 3 to 4 minutes completly provisioning the nginx server
> vagrant destroy   --> to delete the Vagrant server.

