# Devops

It's a mind set, whole set of process, a way of practice.

Dev+ops

 
**dev** - plan, code, build
 
**ops** - test , deploy, monitor


### ci/cd (PIPELINES)

# Continuous Integration(CI)

Process of integration

Test => Build Image(docker or artifactory) =>Push to repository

# Continuous Deployment(CD)

- Deploy to DEV
- Deploy to TESTing
- Deploy to PROD




Terraform Tutorial for Beginners + Labs: Complete Step by Step Guide!
https://www.youtube.com/watch?v=YcJ9IeukJL8
https://kodekloud.com/lessons/labs/


# IAC(Infrastructure As a Code)


## Configuration Management  
- Ansible
- puppet 
- Saltstack	

## Server Templating 
- docker
- Packer
- Vagrant

## Provisional Tools 
- Terraform 
- CloudFormation


# Configuration Management:

Configuration management refers to the process by which all environments hosting software are configured and maintained.

https://www.browserstack.com/guide/configuration-management-in-devops


- Designed to install and manage software
- Maintains standard structure
- Version control 
- Idempotent


# Terraform
- init
- plan
- apply

Terrform cloud and terraform enterprise


Resource
-----------

HCL(Hashicorp configuration Lang)

```
<block><parameters>{
key1=value1
key2=value2
}
```

```
resource "aws_s3_bucket" "data"{
bucket=""
acl= "private"
}
```
```
"aws_s3_bucket"  =>
aws = provider
s3_bucket - resource
```

## Terraform commands
- terraform init
-  terraform plan
- terraform execute
- terraform show


Terraform follows an immutable infrastructure approach, the file was recreated although the contents are the same.

A common configuration naming called **main.tf**, containing multiple blocks

- main.tf    - main config containing resource definition
- variables.tf - contain variables declaration
- outputs.tf - contains outputs from resources
- provider.tf - contains provider definition
