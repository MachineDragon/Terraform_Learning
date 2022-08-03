# Terraform_Learning

Installation
----------------------

Open Terminal

type:    brew install terraform



AWS
------------------------
in okta search aws sre-dev and select dev-admin

aws.amazon.com

search for IAM     
(identity and access management)

This is where you setup users, groups, rolls and permissions

Users

Add user

user name ---> terraform

check programmatic access

permissions

attach existing policies

administrator access

next:tags

next

create user

SAVE THE CREDENTIALS AND DO NOT SHARE download .cs√

close

Confic File
----------------------------
<img width="359" alt="image" src="https://user-images.githubusercontent.com/58194115/182642822-e35b573f-2d93-495a-8fb5-03a6289dcc61.png">





What is Terraform?
----------------------------

Infrastructure Management Tool made by HashiCorp that lets you provision manage and maintain cloud resources like servers, networking, storage etc all in one centralized set code

terraform is a command line program you run to define and make changes to your infrastructure and also a language that defines those changes

Terraform IS NOT FOR CONFIGURATION MANAGEMENT

ex.) Deploy a server, but not what's on it

Terraform cant change whats running on that server once its deployed, for that you need a config management tool such as puppet


Containers
---------------------------

Terraform can work directly with docker and kubernetes

You can use terraform to provision a kubernetes cluster on a cloud provider and then use terraform kubernetes provider to provision containers on that cluster


