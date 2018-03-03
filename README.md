# How to use terraform to spin up three ubuntu nodes using spot instances.

### Download and Install Terraform
https://www.terraform.io/downloads.html

### Edit the k8s.tf file:
1. Change "YOUR_KEY_NAME_HERE" to your ssh keyname (assumes it's already uploaded)
2. Update the AWS region as desired (make sure your ssh key is in this region)
3. Add your AWS "access key" and "aws_secret_key" to this file (NOT RECOMENDED). 
Terraform will use ~/.aws/credentials if not specified in the .tf file. (RECOMENDED)

### Bootstrap terraform
1. Run `terraform init`
2. Run `terraform plan`
3. Run `terraform apply`

If your IP Address changes, and you lose access to ssh into your hosts, just run `terraform apply` again and the security group will be updated with your new IP Address.


If you don't know how to create and upload a key pair to aws, see here.
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

### To tear down all the created resources
1. Run `terraform destroy`
