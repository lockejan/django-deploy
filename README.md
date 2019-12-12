# django-deploy

is a basic config which aims to provide a setup to quickly spin up some local production ready django environment.
As can be seen in the Vagrantfile, after the vm is up and running ansible is used to handle the provisioning.

For the ansible part an extra role was created and does mainly the following:
- install and configure nginx
- install and configure gunicorn
- create a systemd service entry for gunicorn
- pull a private repo which contains a django project
- setup the virtual environment for the project

The ansible role can also be used directly to provision and deploy to a real webserver.
