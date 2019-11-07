# Ansible-Playbooks
Install, setup, and run ansible awx on your ec2 hosts or run local
https://github.com/ansible/awx

run:
ansible-playbook -i inventory/{local,target}/main site.yml

make sure you update target with your own host

# Roles
install: Gets ansible, postgres, python, pip, docker, docker-compose, node, npm

setup: clones the awx repo, edits config files, setup external postgres db, creates docker group

run: runs the awx ansible install playbook

# Variables

Make sure to update variables for your own use. Here are the variables and default values

awx_location: /awx

awxcompose_location: /tmp/awxcompose
pgdocker_location: /tmp/pgdocker

postgres_host:
postgres_port: 5432
postgres_db: awx
postgres_user:
postgres_password:
postgres_admin_password:

# AWX CLI

Use to interact with the installed instances

install:
sudo pip install "https://github.com/ansible/awx/archive/8.0.0.tar.gz#egg=awxkit&subdirectory=awxkit"

run:
awx --help

documentation:
https://github.com/ansible/awx/tree/devel/awxkit/awxkit/cli/docs
