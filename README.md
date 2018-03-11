# aws-nginx-ansible
Ansible playbook for 2 tier nginx and go webapp solution

## Requirements
In order to run this playbook, you must have the following:

* Install requirements from requirements.txt
* An AWS account - you are responsible for all costs incurred
* An AWS user with appropriate permissions to create EC2 instances and security groups.
* An AWS access and secret key
* A EC2 keypair created and added to your local system with ssh-add

## Architectural diagram
![alt text](https://github.com/attree/aws-nginx-ansible/blob/master/nginx-go-ansible.png "Architectural Diagram")

## Variables
Certain variables are defined in `group_vars/all`.
These must be filled prior to deploying the playbook.
An example file exists to help.

## Things to note & improvements
This playbook will deploy 3 servers.
It will configure the two GoApp servers with static private IP's assuming it is deployed into a default AWS VPC. The subnet ID variable in `group_vars/all` needs to match the subnet which contains `172.31.0.50` & `172.31.0.50`. These are hard coded into the deployment.
All three servers are provisioned with a public IP. Not something that is required for the GoApp servers if we had an ansible deployment server elsewhere in the VPC.

## Deploy the playbook
To deploy the playbook, use the following ansible command:
```
ansible-playbook -vvv -i ./inventory/hosts aws-deploy.yml
```
