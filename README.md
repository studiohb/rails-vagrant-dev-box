# Studio HB Vagrant Rails development environment

## Introduction

This project automates the setup of a Rails development environment. It uses [Vagrant](https://www.vagrantup.com/) and [Ansible](https://www.ansible.com/) to provision a Virtual Machine with Ubuntu.

## Requirements

You need to install:

- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/)

## How to use

**Warning! You don't need to open the VirtualBox at all. Everything should be managed by Vagrant!**

```bash
$ vagrant up # To start the VM
$ vagrant up --provision # To start and privision
$ vagrant reload # To reload your vm
$ vagrant provision # To force the provisionning
$ vagrant status # To check the machine state
$ vagrant halt # To stop the VM
```

Connect into the VM:
```bash
$ vagrant ssh
> cd /www/your_project
```

Your VM is accessible on the `192.168.10.10` ip address.

For example, open the [192.168.10.10:3000](http://192.168.10.10:3000) on your host.

## How to configure

You can change the `Vagrantfile` with the desired configuration or change these environment variables:

- `RAILS_VAGRANT_BOX_FOLDER`: The path to your code folder. Default: '.'
- `RAILS_VAGRANT_BOX_RAM`: The amount of RAM in megabytes. Default: 2048
- `RAILS_VAGRANT_BOX_CPUS`: The amount of CPUs. Default: 2

The default postgres user is `postgres` with the password `secret`.

## What's in the box

- Postgres
- RVM
- Git
- Curl
- htop
- imagemagick
- Tmux
- Vim
- Webp
- Yarn
- Zsh

## Licence

This project is released under the [MIT](https://opensource.org/licenses/MIT) license.

## About us

<img src="https://www.studio-hb.com/assets/logo-studio-hb-b65681ecbcfbb2c56154ef3da19c09cf20378bb4e341e5f9b57ab319bfec43bc.svg" width="400" />

[Studio HB](https://www.studio-hb.com/) is a Web agency specialized in the custom development.
