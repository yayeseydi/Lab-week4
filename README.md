# Lab-week4
Networking Lab week 4
# Week 4 Lab – Terraform + Cloud-Init on AWS

This repository contains the configuration files for the **CIT 4640 Week 4 Lab**.  
It uses **Terraform** to provision infrastructure on AWS and **cloud-init** to configure the EC2 instance at boot.

---

##  General Setup

1. **Install Terraform**  
   Follow the instructions in the Week 4 notes or [Terraform install docs](https://developer.hashicorp.com/terraform/downloads).

   Verify installation:
   ```
   terraform -version
Clone this repository

git clone https://github.com/yayeseydi/Lab-week4.git
cd Lab-week4
Configure AWS credentials
Set up your lab AWS account using the AWS CLI:


# aws configure
Provide:

AWS Access Key ID

AWS Secret Access Key

Default region: us-west-2

Default output format: json

## Create a New SSH Key Pair
Generate a new SSH key pair in your Linux environment:


ssh-keygen -t ed25519 -f ~/.ssh/lab4 -C "lab4"
This creates:

~/.ssh/lab4 (private key)

~/.ssh/lab4.pub (public key)

Import the public key into AWS:

aws ec2 import-key-pair \
  --key-name lab4 \
  --public-key-material fileb://~/.ssh/lab4.pub \
  --region us-west-2
## Terraform Workflow
Run these commands from the project root:


terraform init        # initialize providers
terraform fmt         # format files
terraform validate    # validate configuration
terraform plan        # preview changes
terraform apply       # create resources



terraform output instance_ip_addr
##  Connect to the Instance
SSH into the EC2 instance:


chmod 600 ~/.ssh/lab4
ssh -i ~/.ssh/lab4 debian@ec2-35-95-142-96.us-west-2.compute.amazonaws.com


