# Ansible for newbie Devops

## Getting started
In this tutorial, you will learn how to use ansible

## Prerequisite
* OS: Ubuntu 22.04 LTS
* Cloud: GCP/AWS
* Install docker & docker-compose

## Setup Ansible on server
```sh
git clone git@github.com:bidvdo/ansible.git
cd ansible/
apt update && apt install -y jq
pip3 install ansible
ansible-playbook --version
```
Testing connection to target server
```sh
export ANSIBLE_FORCE_COLOR="true"
export ANSIBLE_CONFIG=./ansible.cfg

# Setup SSH Tunnel to target nodes
eval "$(ssh-agent -s)"
ssh-add <(cat <ssh_private_key>)
# Let's test it via ssh
ssh ubuntu@<ip> lscpu
```

## Ansible playbook
This command is to check playbook before we apply it into 
```sh
ansible-playbook playbook.yaml -i inventory.toml --check --diff
```

If everything is fine, let's apply it
```sh
ansible-playbook playbook.yaml -i inventory.toml
```
