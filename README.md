ACIT 4640 – Week 4 Terraform Lab

Instructions on General Setup
1. Install Terraform in the Linux development environment using the official HashiCorp repository.
2. Verify Terraform is installed by running:
   terraform -help
3. Clone the starter repository:
   git clone https://gitlab.com/cit_4640/4640-w4-lab-start-w25
4. Change into the project directory:
   cd 4640-w4-lab-start-w25
5. Ensure AWS credentials are configured so Terraform can authenticate with AWS.
6. Edit the cloud-config.yaml file to add our SSH public key and required packages.
7. Complete the Terraform configuration in main.tf and apply it.

Command Used to Create a New SSH Key Pair
ssh-keygen -t ed25519 -f ~/.ssh/cloudinit_key

Commands Used to Initialize, Format, Plan, and Apply Terraform Configuration
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply

Any Other Instructions Needed to Set Up the Configuration
- The public SSH key (~/.ssh/cloudinit_key.pub) was added to cloud-config.yaml under ssh_authorized_keys.
- The cloud-init configuration installs nginx and nmap automatically at boot.
- Terraform stores infrastructure state locally in terraform.tfstate.
- SSH into the instance using:
  ssh -i ~/.ssh/cloudinit_key web@35.92.0.2

Documentation and References Used

  https://cloudinit.readthedocs.io/en/latest/index.html
  https://developer.hashicorp.com/terraform/install
  https://registry.terraform.io/providers/hashicorp/aws/latest/docs
  https://developer.hashicorp.com/terraform/language/state
  https://spacelift.io/blog/terraform-state
