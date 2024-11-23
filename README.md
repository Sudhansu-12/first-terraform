# Terraform Script: AWS VPC and Web Server Deployment

This Terraform script automates the creation of an AWS Virtual Private Cloud (VPC) along with associated resources for deploying a simple web server running Apache on an Ubuntu instance.

```markdown

## Prerequisites

Before using this script, ensure you have the following:
1. **AWS Account**: Active AWS account with access keys.
2. **Terraform**: Installed on your local machine. [Download Terraform](https://www.terraform.io/downloads).
3. **AWS CLI**: Installed and configured. [Download AWS CLI](https://aws.amazon.com/cli/).
4. **SSH Key Pair**: An existing AWS key pair for accessing the EC2 instance.

## Resources Created

The following AWS resources will be created:
1. **VPC**: A custom VPC with a CIDR block of `10.0.0.0/16`.
2. **Internet Gateway**: Enables internet access for the VPC.
3. **Route Table**: Configured to route traffic to the internet gateway.
4. **Subnet**: A public subnet in `us-east-1a`.
5. **Security Group**: Allows inbound traffic on ports 22 (SSH), 80 (HTTP), and 443 (HTTPS).
6. **Elastic IP**: Assigned to the EC2 instance.
7. **Network Interface**: Attached to the EC2 instance.
8. **EC2 Instance**: An Ubuntu server with Apache installed and enabled.

## Usage

### 1. Clone the Repository
```bash
git clone https://github.com/Sudhansu-12/first-terraform.git
cd first-terraform
```

### 2. Update Variables
Replace the following placeholders in the `provider` block of the script:
- `access_key`: Your AWS access key.
- `secret_key`: Your AWS secret key.

Replace `main-key` in the `aws_instance` resource with your SSH key pair name.

### 3. Initialize Terraform
Run the following command to initialize Terraform:
```bash
terraform init
```

### 4. Plan the Infrastructure
Check the plan to verify what will be created:
```bash
terraform plan
```

### 5. Apply the Changes
Deploy the infrastructure:
```bash
terraform apply
```
Type `yes` when prompted.

### 6. Access the Web Server
After deployment, Terraform outputs the Elastic IP. Access the web server in your browser by navigating to `http://<Elastic-IP>`.

### 7. Destroy the Infrastructure
To clean up and delete all resources, run:
```bash
terraform destroy
```
Type `yes` when prompted.

## Notes
- Make sure to destroy the resources when not in use to avoid unnecessary AWS charges.
- The AMI ID in this script is for Ubuntu in the `us-east-1` region. Update it if using a different region or OS.
