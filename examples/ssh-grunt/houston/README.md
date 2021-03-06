**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-security>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-security/blob/master/examples/ssh-grunt/houston/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# SSH Grunt with Houston Example

This is an example of how to install [ssh-grunt](/modules/ssh-grunt) on an EC2 Instance so that you can manage SSH
access for the Instance with any Identity Provider (IdP) such as Google or ADFS by using Gruntwork Houston (if you're
looking for how to use `ssh-grunt` with IAM, see the [ssh-grunt IAM example](/examples/ssh-grunt/iam). You can
upload your public SSH Key to your user account in Houston and `ssh-grunt` will allow you to SSH to the EC2 Instances
using your IdP user name and SSH key for authentication.




## Quick start

To try these templates out you must have Terraform and Packer installed:

1. Upload your public SSH Key to Houston.
1. Build the AMI for `ssh-grunt` with Houston by following the
   [instructions in the packer folder](/examples/ssh-grunt/packer).
1. Open `vars.tf`, set the environment variables specified at the top of the file, and fill in any other variables that
   don't have a default, including the ID of the AMI you built in the previous step.
1. Run `terraform init`.
1. Run `terraform apply`.
1. When the templates are done applying, you'll see the IP address of the EC2 Instance. You should now be able to SSH
   to it using your IdP username and the public key you uploaded in step 1: `ssh <IAM-USERNAME>@<SERVER-IP>`.