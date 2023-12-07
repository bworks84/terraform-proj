# Learn Terraform (and AWS) by Building a Dev Environment - Full Course for Beginners

This is a follow along project by Derek Morgan hosted on FreeCodeCamp utilizing Terraform and AWS to build a dev environment

[!Alt text]("../images/architecture.png")

## Table of Contents

- [Project Title](#project-title)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Features](#features)
  - [Steps](#steps)
  - [Documentation](#documentation)
  - [Acknowledgments](#acknowledgments)

## Introduction

Learn Terraform basics as you utilize Visual Studio Code (On Windows, Mac, or Linux!) to deploy AWS resources and an EC2 instance that you can SSH into to have your own re-deployable environment.

## Features

Build out a dev environment with Docker installed by setting up a remote Ubuntu server

## Steps

[x] - Create AWS User account with proper permissions for building out EC2 and VPC resources. Also install AWS CLI with Access keys.  
[x] - Start up VSCode and create an new directory for project. Initialize with Github via the terminal. Add plugins like AWS (to be able to see active AWS resources in VSCode).  
[x] - Become familiar with terraform plan, apply, state/show <resource>, etc.  
[x] - Build Basic AWS Environment:

- VPC: VPC give you full control over your virtual environment, including resource placement, connectivity, and security
- Subnet: Created a subnet within the VPC with specific CIDR block. This will enable auto assignment of public IP addresses to any instances launched within the subnet.
- IGW: create an IGW that allows access from the VPC to the public internet (and enables the user to connect to an EC2 instance)
- Route Table: a route table is necessary to create and store rules to determine how network traffic is directed to/from the subnets and VPC. Additionally, need to associate the route table with the subnet created.
- Security Groups: similar to a virtual firewally, security groups add another layer of protection around the EC2 instance(s) that provide traffic direction for the EC2 instance
- Create Key Pair to access the EC2 instance
- EC2 Instance: create an EC2 instance that will allow us to set up a remote dev environment. Also, while the EC2 is created, I added a userdata.tpl script to install Docker, to practice having the container available to use in a remote dev environment
- Set up a provisioner: generated an SSH configuration file based on the host OS and included the public IP of the EC2 instance.

[x] - Verify build by either running `ssh -i /Path/to/SSH/key ubuntu@<publicIP>` or using the command palette, searching for Remote-SSH: Connect to Host, searching for the public IP address created for the new EC2 Instance and press Enter. This should load a new VSCode editor with Docker already installed!  
[!Alt text]("./images/docker_installed.png")
[!Alt text]("./images/VSCodeinstalled.png")

## Documentation

Terraform documentation - https://developer.hashicorp.com/terraform/docs

## Acknowledgments

Learn Terraform (and AWS) by Building a Dev Environment - Full Course for Beginners - https://www.youtube.com/watch?v=iRaai1IBlB0&t=1889s
