<<<<<<< HEAD
## Ansible playbook - MEAN stack

This Vagrant and Virtualbox based Ansible playbook sets up a MEAN stack (Mongodb, Node + Express suitable for back-end for Angular SPAs).

### Instructions

* Install VirtualBox and Vagrant (make sure Vagrant is version 1.6.5 or later)
* Install Ansible
  * On MacBook Air and Pro, I had best results using Python's pip, which doesn't come with the version of Python that comes pre-installed on Macs. So if you have homebrew installed (and you should) you can do:

````
$ brew install python
$ sudo pip install ansible
````

* Clone this project to a folder where you keep your VMs
* First execute `vagrant box list` to check if `ubuntu/trusty64` is already on your laptop or desktop host system. If it isn't download the box with `vagrant box add ubuntu/trusty64`.
* On the cammand-line in that folder, type `vagrant up`
* The process will take a while, on my 4GB RAM MacBook Pro it took about 10 minutes. But that's just the first time, once you have it provisioned it starts up again very quickly. A large part of the initial slowness is the one-time provisioning via Ansible of the MEAN components.
* Associate `http://mean01/` (or any other name you'd like) with local machine IP specified in the Vagrantfile (192.168.46.100 initially) by including the following line in `/etc/hosts`:

    192.168.46.100  mean01

* Within the guest VM box, if you do your work in, say, `/vagrant/dev/project01` then in the VM dir `./dev/project01` you can access the files with your favorite editor or IDE or else edit via ssh remoting.  
* If you create and run a node.js app on port 3000, you can access it in your browser by pointing it at `http://mean01:3000`.

### Vagrantfile

* Box used: [Ubuntu 14.04 64-bit (Trusty)](https://vagrantcloud.com/ubuntu/boxes/trusty64)
* [Virtualbox settings:](https://www.virtualbox.org/manual/ch08.html#vboxmanage-modifyvm)
 * memory 512
 * IP 192.168.46.100

### Playbook tasks

* Installs build-essential and git packages from Apt.
* MongoDB installation:
 * Imports MongoDB's public GPG key.
 * Adds MongoDB's Apt source.
 * Installs MongoDB
* Node.js installation:
 * Sets up [NodeSource](https://github.com/nodesource/distributions) for Ubuntu.
 * Installs latest version of Node.js.
 * Installs [Grunt](http://gruntjs.com/).
 * Installs [Gulp](http://gulpjs.com/).

### References

* [Geerling, Jeff, *Ansible for DevOps*](https://leanpub.com/ansible-for-devops)
  * [Ansible for DevOps Examples on GitHub](https://github.com/geerlingguy/ansible-for-devops)
* [Vagrant & Ansible Quickstart Tutorial](http://adamcod.es/2014/09/23/vagrant-ansible-quickstart-tutorial.html)
* [Ansible playbook - MEAN stack](https://github.com/dennmart/vagrant-ansible-playbooks/tree/master/mean)
=======
# ansible-mongo-node
>>>>>>> d2296c4cb63e34d1b920ac428b7b45ef05fc4e8e
