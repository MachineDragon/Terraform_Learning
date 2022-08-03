# Terraform_Learning

Installation
----------------------

Open Terminal

if you dont already have brew then run this command, otherwise skip this
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

type:    brew install terraform

Install visual studio code

on the left hand side of vsc select the 4 blocks and search terraform


<img width="268" alt="image" src="https://user-images.githubusercontent.com/58194115/182705597-e7076b09-4655-4c8b-847e-e339a3122abe.png">

install the hashicorp terraform extension


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

SAVE THE CREDENTIALS AND DO NOT SHARE download .csv

close


Inventory
---------------------------

create a new folder in Documents called terraform

open visual studio code

on top left select file

open folder

select the terraform directory under documents


Confic File
----------------------------
Open the .csv file

<img width="359" alt="image" src="https://user-images.githubusercontent.com/58194115/182642822-e35b573f-2d93-495a-8fb5-03a6289dcc61.png">

File

Save as(do not save over your current .csv file)



main.tf
---------------------------
in visual studio code


create a new file called main.tf in our terraform directory

copy this code into the file and command + s to save it

# Configure the AWS Provider
provider "aws" {
  region = "us-east-1"
}

now open your config file and paste the access key and secret key under region

(if you lost your config file follow these steps)

go to your aws management console

select your account on the top right

<img width="583" alt="image" src="https://user-images.githubusercontent.com/58194115/182706827-6f3514c4-fa7b-4f07-a17b-3dc98a122948.png">


Access key

create new access key

show access key

paste this into your main.tf it should look something like this


<img width="759" alt="image" src="https://user-images.githubusercontent.com/58194115/182707736-b78fef45-9c9b-4537-aaa7-c1d284c72bed.png">


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


