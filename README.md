# How to automate DNS and SSL with Terraform

## Requirements:
 - existing route53 zone in AWS account 
 - terraform v0.12.16 or newer
  
## Setup
* Set your demo_dns_zone (e.g. for account 643088008799 "mjheitland.de.") and demo_dns_name (e.g. "ssldemo" variables in terraform.tfvars
* Optionally: Setup your providers in provider.tf if your domain is registered in a different AWS account and comment in "provider = aws.account_route53" in ssl_cert.tf
* terraform init
* terraform apply --auto-approve

## Test
* Click on the link provided by Terraform output, now you should see a "Hello World" page

## Teardown
* terraform destroy --auto-approve

## Links
[How to automate DNS and SSL with Terraform] (https://www.oss-group.co.nz/blog/automated-certificates-aws)
