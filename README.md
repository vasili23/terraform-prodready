# terraform-prodready
this is terraform project. 

Modules:

ssh-key: Generates an ssh key pair

network: Sets up a VPC with IGWs, NAT GWs, 2 public subnets, 2 private subnets, SG to SSH in from anywhere

ec2: Currently creates a bastian ec2 instance in a public subnet and a ec2 instance in a private subnet

each subnet is in a different AZ

private key is copied over to the bastion ec2 instance so it can ssh into the private subnet

ec2 in private subnet has outgoing network access though the NAT gateway

may add ansible playbook to take care of copying over the shh key to the bastian ec2## Requirements


how to use.
1) clone repo
2) manage credentials best practice to use with variables
3) terraform init
4) terraform plan
5) terraform apply -auto-approve
6) output will be 3 ssh conection connect to public after you can connect to private vms
