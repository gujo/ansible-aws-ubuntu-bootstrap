ansible-aws-ubuntu-bootstrap
============================

Bootstrap and harden default ubuntu image on aws

[![Build Status](https://travis-ci.org/gujo/ansible-aws-ubuntu-bootstrap.png?branch=master)](https://travis-ci.org/gujo/ansible-aws-ubuntu-bootstrap)


Usage
-----

* First of all you need ansible installed on the machine where this is executed
  * Install python and python-pip using the method preferred by your OS
  * `pip install ansible`
  * `pip install jinja2`
  * `pip install pyyaml`
  * `pip install paramiko`
  

* Edit hosts.ini to include the ec2 instances you want to bootstrap
* Add your aws key to the ssh repo:

      `ssh-add ~/.ssh/my_aws_key.pem`

* Run the ansible playbook
      `ansible-playbook bootstrap.yml -i hosts.ini`
