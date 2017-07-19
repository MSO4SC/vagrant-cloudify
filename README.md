# vagrant-cloudify
Two (Vagrant) VirtualBox Machines to hold Cloudify CLI and Manager.
- cli install cloudify cli and set its own ssh keys. From it you can bootstrap the manager using ./bootstrap-manager.sh on the other machine
- manager is the machine in where the Cloudify manager is installed from the previous machine. It sets automatically the public ssh key of the cli

## Change SSH Key pair
It would be better to change the SSH key pair provided in cli/ssh folder. To do that:
- Before running "vagrant up" you need to create an rsa SSH Key pair with default name and put it on the ssh folder. Then overwrite the content under the "" in the last line at manager/scripts/ssh-settings.sh with the content of id_rsa.pub.
