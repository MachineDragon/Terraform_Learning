# Terraform_Learning

Installation
_______________________

Open Terminal

type:    brew install terraform






What is Terraform?
___________________________

Infrastructure Management Tool made by HashiCorp that lets you provision manage and maintain cloud resources like servers, networking, storage etc all in one centralized set code

terraform is a command line program you run to define and make changes to your infrastructure and also a language that defines those changes

Terraform IS NOT FOR CONFIGURATION MANAGEMENT

ex.) Deploy a server, but not what's on it

Terraform cant change whats running on that server once its deployed, for that you need a config management tool such as puppet


Containers
___________________________

Terraform can work directly with docker and kubernetes

You can use terraform to provision a kubernetes cluster on a cloud provider and then use terraform kubernetes provider to provision containers on that cluster


