# Ansible Vagrant profile for an Svn2Git VM

## Background

Vagrant and VirtualBox (or some other VM provider) can be used to quickly build or rebuild virtual servers.

This Vagrant profile installs [Svn2Git](https://lucene.apache.org/solr/) using the [Ansible](http://www.ansible.com/) provisioner.

With Svn2Git installed, you can convert an SVN repository to a Git repository using the command `svn-all-fast-export`. Read more here: [Switching an SVN repository to Git with KDE's Svn2Git](http://www.midwesternmac.com/blogs/jeff-geerling/switching-svn-repository-git2svn).

## Getting Started

This README file is inside a folder that contains a `Vagrantfile` (hereafter this folder shall be called the [vagrant_root]), which tells Vagrant how to set up your virtual machine in VirtualBox.

To use the vagrant file, you will need to have done the following:

  1. Download and Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  2. Download and Install [Vagrant](http://downloads.vagrantup.com/)
  3. Install [Ansible](http://ansibleworks.com/) ([guide for installing Ansible](http://docs.ansible.com/intro_installation.html)).
  4. Open a shell prompt (Terminal app on a Mac) and cd into the folder containing the `Vagrantfile`.
  5. This Ansible playbook uses a variety of roles to configure Svn2Git, and you'll need to install the roles before you can get the VM set up. Run the following command to get all the necessary roles: `$ ansible-galaxy install geerlingguy.repo-epel geerlingguy.svn geerlingguy.git geerlingguy.svn2git`

Once all of that is done, you can simply type in `vagrant up`, and Vagrant will create a new VM, install the base box, and configure it.

Once the new VM is up and running (after `vagrant up` is complete and you're back at the command prompt), you can log into it via SSH if you'd like by typing in `vagrant ssh`.
