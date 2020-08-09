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
* Click on the testing link provided by Terraform output, now you should see a "Hello World" page

## Teardown
* terraform destroy --auto-approve

## Links
[How to automate DNS and SSL with Terraform](https://www.oss-group.co.nz/blog/automated-certificates-aws)

## Outputs
```
certificate_arn = arn:aws:acm:eu-west-1:643088008799:certificate/d5fd2943-135f-4571-821c-2752f1b7dac6
fqdn = ssldemo.mjheitland.de
route53_record_name = ssldemo.mjheitland.de
testing = Test this demo code by going to https://ssldemo.mjheitland.de and checking your have a valid SSL cert
validation_options = {
  "domain_name" = "ssldemo.mjheitland.de"
  "resource_record_name" = "_b26f54ceeec12ab62a108783530d8f01.ssldemo.mjheitland.de."
  "resource_record_type" = "CNAME"
  "resource_record_value" = "_5c8cbc70b516729b75f6489ef9884a92.jfrzftwwjs.acm-validations.aws."
}
zone_id = Z09847291R3SOT2YPFLR7
```
