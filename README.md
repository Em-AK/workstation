# Workstation

An experiment to automate the setup of my dev machine from a fresh ubuntu, while learning Ansible.

## Features:

* Install and update system packages from a list
* Install ruby versions from a list with rbenv and ruby-build
* Install and configure fish shell
* Install node versions from a list with [fnm](https://github.com/fisherman/fnm)

## Installation

Starting from a fresh install of ubuntu (tested with the latest LTS).

Install Ansible

```shell
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible git
```

Edit `/etc/ansible/hosts` to have this line uncommented/added

    localhost ansible_connection=local

Edit `etc/ansible/ansible.cfg` in the `[privilege_escalation]` section uncomment/add this line

    become_ask_pass=True

Clone the repo

    git clone https://github.com/Em-AK/workstation.git

## Usage

Adapt the list of packages, nodejs versions, ruby versions, fish plugins, ... to your needs in `workstation/ubuntu.yml`

Finally run the playbook

    ansible-playbook workstation/ubuntu.yml

## TODO

* install android + cordova to build hybrid apps
* sync dotfiles for tmux, vim, fish, ...
* install custom inconsolata font
* clone remote git repos from a list of current projects

## Inspiration

This [blog article from Nick Hammond](http://www.nickhammond.com/automating-development-environment-ansible/)

Thank you @nickhammond for showing me how to run ansible playbooks on localhost :pray: 
