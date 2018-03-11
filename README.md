# aws-nginx-ansible
Ansible playbook for 2 tier nginx and go webapp solution

## Requirements
In order to run this playbook, you must have the following:

* Install requirements from requirements.txt
* An AWS account
* An AWS user with appropriate permissions to create EC2 instances and security groups.
* An AWS access and secret key
* A EC2 keypair created and added to your local system with ssh-add

## Variables
Certain variables are defined in `group_vars/all`.
These must be filled prior to deploying the playbook.
An example file exists to help.

## Deploy the playbook
To deploy the playbook, use the following ansible command:
```
ansible-playbook -vvv -i ./inventory/hosts aws-deploy.yml
```
