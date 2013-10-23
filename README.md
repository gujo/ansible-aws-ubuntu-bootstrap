ansible-aws-ubuntu-bootstrap
============================

Bootstrap and harden default ubuntu image on aws

Usage
-----

* Edit hosts.ini to include the ec2 instances you want to bootstrap
* Add your aws key to the ssh repo:

      ssh-add ~/.ssh/my_aws_key.pem

* Run the ansible playbook
      ansible-playbook bootstrap.yml -i hosts.ini
