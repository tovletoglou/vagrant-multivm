# Vagrant MultiVM with SSH blueprint

Create one or more VM with static/private IP/network and the same key to SSH seamlessly from one VM to another. Also, updates hosts file to use the hostnames of the VMs. Finally, adds your public key to the guest to behave them as normal VMs without the need to use vagrant commands; instead of `vagrant ssh VM_NAME` you can do `ssh vagrant@VM_HOSTNAME`.

## Information

On the first vagrant command it will create the SSH key in the `PATH_TO_PROJECT/.ssh` that will be used for the VMs instead of the vagrant-auto generated keys (one for every VM). We do that to ssh from one VM to another seamlessly. Compromise security for flexibility.

Also, it will get your `HOMEDIR/.ssh/id_rsa.pub` public key, and it will add it on the `authorized_keys` on every VM. Adding your public key on the VMs does not affect security.

Finally, it will update the `hosts` file of your computer, and it will do the same for the clients.

## Requirements

- Oracle VirtualBox (https://www.virtualbox.org/)
- Vagrant (https://www.vagrantup.com/)
- Vagrant Plugin Hostmanager (to install: `vagrant plugin install vagrant-hostmanager`)
- Terminal with SSH (on Windows https://git-scm.com/download/win)
- SSH public and private key under your `HOMEDIR/.ssh/id_rsa` and `HOMEDIR/.ssh/id_rsa.pub`
