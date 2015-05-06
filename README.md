# Provision development environment with Ansible

This vagrant file, provision.sh, and playbook allows you
to provision your favorite development environment even if you are on Windows or behind proxy.

## Requirement

This vagrant file, provision.sh, and playbook expects the following tools are already installed.

- [Oracle VM VirtualBox 4.3.6](https://www.virtualbox.org/)
- [Vagrant 1.4.1](http://www.vagrantup.com/)

Git client is also needed. If you are on Windows, msysgit is preferred.

- [Git for Windows 1.9.0](http://msysgit.github.io/)


## Target VM

As for now, This package supports only trusty.


## How to use

Create and move to directory where you want to create the virtual machine, then download this playbook via git.

```
$ mkdir -p ~/vagrants/
$ cd ~/vagrants/
$ git clone https://github.com/kyokk-viola/ansible-settings.git
```

If you are behind the proxy, configure your proxy host and port like below.

```
$ echo 'http_proxy: http://your.proxy.host:9999/' >> ansible-settings/$TARGET/ansible/roles/proxy/vars/main.yml
```

Finally, dive into the directory and boot the virtual machine.
**THIS PROCESS WILL TAKE A SEVERAL MINUTES**, please wait patiently.

```
$ cd ansible-settings/$TARGET
$ vagrant up
# THIS PROCESS WILL TAKE A SEVERAL MINUTES, please wait patiently.
$ vagrant ssh
```

You can also use general ssh command to private network address which defined in Vagrantfile.
The password of vagrant is `vagrant`, as you know ;-)

```
$ ssh vagrant@192.168.33.10
```

## Provisioned environment

This vagrant file, provision.sh, and playbook provisions the following environment.
Of course Python and Ansible are installed, too!
you can exclude roles which you don't need.

- Ubuntu 14.04.2 LTS x86_64
 - cdev : c/c++ development tools
 - git
 - lang : japanese language package
 - python-default:
 
