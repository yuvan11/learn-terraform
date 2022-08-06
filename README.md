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
-validate
- plan
- apply
- output

Terrform cloud and terraform enterprise


# Resource
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
- terraform validate
-  terraform plan
- terraform execute
- terraform show
- terraform output 
- terraform fmt
- terraform show or terraform show -json
- terraform providers
- terraform refresh
- terraform graph 

Terraform follows an immutable infrastructure approach, the file was recreated although the contents are the same.

A common configuration naming called **main.tf**, containing multiple blocks

- main.tf    - main config containing resource definition
- variables.tf - contain variables declaration
- outputs.tf - contains outputs from resources
- provider.tf - contains provider definition

# Input variables 

# variable Precedence

- Environment variables

```
export TF_VAR_FILENAME="/roots/cat.txt"
```
- Terraform.tfvars
```
 filename="/root/pets.txt"
```
- *.auto.tfvars(alphabetical order)
```
filename="/root/mypet.txt"
```
- passing -var or --var file (command-line args)(High precedence)
```
terraform apply -var "filename="/root/home/pets.txt"
```

# Interpolation

- Syntax
```
 ${resource_type.resource_block_name}
```
- example
```
 ${random_pet.my-pet.id}
```

# Dependencies
- Implicit - tf automatically finds out and execute the dependencies
- Explicit - This requires additional parameters to be passed inside resource
```
depands_on = [
    resource_type.resource_block_name
]
```
```
depands_on = [
    random_pet.my-pet.id
]
```

# Output variables

```
output <variable_name>{
    value = <variable_value>
    <arguments>
}
```

- terraform.tfstate - like a blueprint, tracking metadeta
- Immutable Infrastructure

# Lifecycle

```
    lifecycle{
      <var>=<val>
    }
```
```
    lifecycle{
      create_before_destroy = true
    }
```
- create_before_destroy = true, creates new resources before the resource has been deleted
- prevent_destroy = true, prevents the resources getting deleted
- ignore_changes- accepts the list of values and whichever added to it, can be prevented


# Data

```
<block><parameters>{
key1=value1
key2=value2
}
```

```
data "aws_s3_bucket" "data"{
bucket=""
acl= "private"
}
```


# Resource Vs Data

| 
RESOURCE                  |           DATA SOURCE       |
| :---:   |                                         :-:  |
| KEYWORD : resource      |           KEYWORD : data   | 
| create, read, delete  infrastructure  |           only read    infrastructure    |
| managed resources       |           data resources   |


# Meta Arguments

- depends_on
- lifecycle
- for_each (works only for set and map) , output as map
- count - output as list