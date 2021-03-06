# Terraform AWS

## Terraform Commands

* [`terraform get`](https://www.terraform.io/docs/commands/get.html)
* [`terraform plan`](https://www.terraform.io/docs/commands/plan.html)
* [`terraform apply`](https://www.terraform.io/docs/commands/apply.html)
* [`terraform destroy`](https://www.terraform.io/docs/commands/destroy.html)

## AWS Basic Compute Demo

This basic compute demo will consist of the orchestration of blank t2.micro (free tier) EC2 instances into AWS.

### Pre-requisites

- It is assumed that this demo is being ran from a UNIX based machine
- An AWS account [-Sign up here-](https://aws.amazon.com/premiumsupport/signup/)
  - AWS SSH key-pair created and private key stored locally (this is used as the SSH key placed onto each new instance by Terraform, this key is then used for SSH access after creation is complete)
- This repository cloned locally (install Git [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))
- Terraform installed (install it [here](https://www.terraform.io/downloads.html))

### Instructions

1. open 'terraform.tfvars' and enter a value for variable 'owner' and 'ssh_key_name' (the name of the key associated with your AWS account), and save
2. run command 'export AWS_ACCESS_KEY_ID={your_access_key}'  
3. run command 'export AWS_SECRET_ACCESS_KEY={your_secret_key}'  
4. run command 'export AWS_DEFAULT_REGION={your_preferred_region}'  
5. run command 'terraform get'  
6. run command 'terraform plan -var-file=./terraform.tfvars'
7. run command 'terraform apply -state=./terraform.tfstate -var-file=./terraform.tfvars'  

To destroy the infrastructure you have built, run command 'terraform destroy -state=./terraform.tfstate -var-file=./terraform.tfvars'
