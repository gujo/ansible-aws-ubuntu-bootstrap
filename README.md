ansible-aws-ubuntu-bootstrap
============================

Bootstrap and harden default ubuntu image on aws

[![Build Status](https://travis-ci.org/gujo/ansible-aws-ubuntu-bootstrap.png?branch=master)](https://travis-ci.org/gujo/ansible-aws-ubuntu-bootstrap)


Usage
-----

  * First of all you need ansible installed on the machine where this is executed
  * Install python and python-pip using the method preferred by your OS

Install ansible either from pip:
  * `pip install ansible`

Or from Github to get the latest version:
  * `pip install jinja2`
  * `pip install pyyaml`
  * `pip install paramiko`
  * `git clone git://github.com/ansible/ansible.git`
  * `source ansible/hacking/env-setup`

* Edit hosts.ini to include the ec2 instances you want to bootstrap
* Add your aws key to the ssh repo:

  `ssh-add ~/.ssh/my_aws_key.pem`

* Run the ansible playbook
  
  `ansible-playbook bootstrap.yml -i hosts.ini`


Measures Taken
--------------

* Update all packages
* Enable unattended security updates
* Disable direct root access and password login
* Create an admin group and restrict sudo to that group
* Install fail2ban
* Set up UFW firewall, allow only SSH as a default
* Reboot machine in case we have a new kernel installed


Future Development
------------------

For a 'real' server that is part of a bigger system and not just a standalone
machine a couple more measures should be taken. For example:
* SSH should only be open on a separate VPN-protected admin-network
* Ship all logs to a separate server
* Use SELinux or Apparmor
* ...
