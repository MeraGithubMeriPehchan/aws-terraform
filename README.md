# AWS Infrastructure Creation using Terraform via Jenkins_Pipeline

Helpful Terraform Links:
- [Terraform Language Documentation](https://www.terraform.io/docs/language/index.html)
- [Resource: aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [Resource: aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance)

## Step 0: Jenkins pipeline
Create Jenkins Pipeline taking reference from _aws-terraform-jenkins-pipeline_
## Step 1: Initialize Terraform
```
terraform init
```

## Step 2: Plan Resources
```
terraform plan -var-file="vars/dev-east-1.tfvars"
```

## Step 3: Apply Resources
```
terraform apply -var-file="vars/dev-east-1.tfvars"
```

## Step 4: Commands to get the Jenkins admin password via command line
```
chmod 400 <keypair>
ssh -i <keypair> ec2-user@<public_dns>
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```

## Step 4: Cleanup Terraform Resources
```
terraform destroy -var-file="vars/dev-east-1.tfvars"
