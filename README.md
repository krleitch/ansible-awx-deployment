# Ansible-Playbooks
Install, setup, and run ansible awx with docker on your ec2 hosts or run local

https://github.com/ansible/awx

### Run

ansible-playbook -i inventory/{local,awx-target}/hosts awx.yml

make sure you update inventory/awx-target/hosts with your own host

# Requirements

Running amazon linux 2

Uses yum and amazon-linux-extras for package management

# Roles

### Awx-Install

Gets ansible, postgres, python, pip, docker, docker-compose, node, npm, awx cli

### Awx-Setup

clones the awx repo, edits config files, create external psql db, creates docker group, set preload data, set awx user/pass

### Awx-Run

stops already running docker containers if any, runs the awx ansible install playbook

# Variables

Make sure to update variables for your own use. Here are the variables and default values

### Group Vars

awx_location: /awx

### Setup Vars

awxcompose_location: /tmp/awxcompose

pgdocker_location: /tmp/pgdocker

postgres_host:

postgres_port: 5432

postgres_db: awx

postgres_user:

postgres_password:

postgres_admin_password:

awx_user: admin

awx_password: password

preload_data: False

# AWX CLI

Use to interact with the installed instances

### Install

sudo pip install "https://github.com/ansible/awx/archive/8.0.0.tar.gz#egg=awxkit&subdirectory=awxkit"

This is already installed as part of the setup role

### Run

awx --help

### Documentation

https://github.com/ansible/awx/tree/devel/awxkit/awxkit/cli/docs
