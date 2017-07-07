This repository contains the setup and provisioning files required to develop and deploy Pharos.

## Required Tools

- Install [Vagrant](http://downloads.vagrantup.com/)
  - Install the Virtualisation Provider [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Install [Terraform](https://www.terraform.io/intro/getting-started/install.html)
- Install [Ansible](http://docs.ansible.com/ansible/intro_installation.html)
  - For Ansible ensure you have python2 installed

## Clone the repository
```
git clone git@github.com:deploying-elixir/elixir_setup.git
```

## Change directory into the root
```
cd elixir_setup
```

## Install the NodeJS and Postgres playbooks
```
ansible-galaxy install geerlingguy.nodejs
ansible-galaxy install ANXS.postgresql
```

## Enable SSH agent forwarding

- Start the agent from the command line:
```
eval $(ssh-agent)
```
- Add your ssh key used for Git (default location is `~/.ssh/id_rsa`):
```
ssh-add
```

## Provision the Vagrant box
```
vagrant up
```

## Enter the virtual machine
```
vagrant ssh
```

## Check your installation

Verify the installation by running `elixir -v` from the virtual machine command prompt. Details similar to below should be returned.

```
Erlang/OTP 20 [erts-9.0] [source] [64-bit] [smp:1:1] [ds:1:1:10] [async-threads:10] [hipe] [kernel-poll:false]

Elixir 1.4.5
```

## Exit the virtual machine
When you have finished, exit the virtual machine by typing `cmd D` from the prompt.

## Commonly used vagrant commands

```
  vagrant up        # starts vagrant
  vagrant provision # provisions vm (without restarting)
  vagrant ssh       # SSH into vagrant
  vagrant reload    # restarts vagrant
  vagrant halt      # stops vagrant
  vagrant status    # check to see if vm is running
 ```
