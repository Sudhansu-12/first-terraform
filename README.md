# Terraform Script: AWS VPC and Web Server Deployment

This Terraform script automates the creation of an AWS Virtual Private Cloud (VPC) along with associated resources for deploying a simple web server running Apache on an Ubuntu instance.

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
