# Terraform_Learning

Installation
----------------------

Open Terminal

if you dont already have brew then run this command, otherwise skip this step

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


Confic File and Security Credentials
----------------------------
Open the .csv file

<img width="359" alt="image" src="https://user-images.githubusercontent.com/58194115/182642822-e35b573f-2d93-495a-8fb5-03a6289dcc61.png">

File

Save as(do not save over your current .csv file)


(if you lost your config file follow these steps)

go to your aws management console

select your account on the top right

<img width="583" alt="image" src="https://user-images.githubusercontent.com/58194115/182706827-6f3514c4-fa7b-4f07-a17b-3dc98a122948.png">


Access key

create new access key

show access key


Launching an EC2 Instance manually within the aws console as compared to doing it with terraform
---------------------------

basically a virtual machine within aws

ex.) deploying a windows server, Linux machine, database etc

on aws 


click on services


ec2


running instances


<img width="581" alt="image" src="https://user-images.githubusercontent.com/58194115/182710338-0fd08af4-32ab-4832-9df1-1d88a3bfba8b.png">


launch instance


search for the ami of your choosing


<img width="643" alt="image" src="https://user-images.githubusercontent.com/58194115/182712966-e534682d-d04f-431a-afbf-2396e53b6a7a.png">


Make sure to copy the ami id you will need this for your main.tf



deploys an ami which is basically an image ubuntu, windows etc


select


t2micro (the more down on the list you go the faster and more $$$)


review and launch


proceed without creating a key pair


launch instances


view instances

main.tf
---------------------------
in visual studio code


create a new file called main.tf in our terraform directory


copy this code into the file and command + s to save it


provider "aws" {
  region = "us-east-1"
}


now open your config file, copy the access key and secret key and paste them under region

it should look something like this


<img width="759" alt="image" src="https://user-images.githubusercontent.com/58194115/182707736-b78fef45-9c9b-4537-aaa7-c1d284c72bed.png">


now copy this code into your main.tf



resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
}



we are going to change "web" to whatever you like to name your instance 

<img width="643" alt="image" src="https://user-images.githubusercontent.com/58194115/182712966-e534682d-d04f-431a-afbf-2396e53b6a7a.png">

paste your ami id to where it says data.aws_ami.ubuntu.id


command + s

<img width="850" alt="image" src="https://user-images.githubusercontent.com/58194115/182714182-82195bd7-7c3f-4019-9053-14a32e568ca8.png">


Launching in VS Code Terminal
------------------------

in vs code on the top left select terminal


new terminal


terraform init


looks at the providers we have defined and downloads necessary plugins to interact with aws api


terraform apply


creates the server, may take 5 - 10 minutes



your instance should now show up in your aws view instances web page



<img width="640" alt="image" src="https://user-images.githubusercontent.com/58194115/182716768-57f3ef84-40c8-42c9-848c-bde7f2f56a3d.png">






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






