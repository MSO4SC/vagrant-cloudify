# vagrant-cloudify
Two (Vagrant) VirtualBox Machines to hold Cloudify CLI and Manager.
- cli install cloudify cli and set its own ssh keys. From it you can bootstrap the manager using ./bootstrap-manager.sh on the other machine
- manager is the machine in where the Cloudify manager is installed from the previous machine. It sets automatically the public ssh key of the cli

## Setup
To be able to connect from the host machine without using "vagrant ssh" command, change the first line in [cli|manager]/scripts/ssh-settings.sh with the host public key.
To change the gests Ip, modify the Vagrant files (config.vm.network "private_network", ip: "[IP]")

## Change SSH Key pair
It would be better to change the SSH key pair provided in cli/ssh folder that allows the cli to connect to the manager. To do that:
- Before running "vagrant up" you need to create an rsa SSH Key pair with default name and put it on the ssh folder. Then overwrite the content under the "" in the last line at manager/scripts/ssh-settings.sh with the content of id_rsa.pub.
