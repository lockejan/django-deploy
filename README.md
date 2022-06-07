# django-deploy

is a basic ansible-role which aims to provide a quick and easy setup of django services.  
Local setups are provided with Vagrant.  

`vagrant up`

The ansible role includes the following tasks:
- install python3.7, pip and virtualenv
- pull a private repo which contains a django project
- setup the virtual environment for the project
- install all project dependencies inside the environment
- install and configure nginx
- install and configure gunicorn
- create a systemd service entry for gunicorn and nginx
- notify handlers to restart gunicorn and nginx when necessary

The ansible role can also be used directly to provision and deploy to a real webserver.

```shell
cd ansible
ansible-playbook playbook.yml --limit staging`

```

Nix is currently only used to pin the used ansible version.
