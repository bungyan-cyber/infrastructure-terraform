# Infrastructure as Code with Terraform

This project sets up a basic infrastructure on AWS using Terraform.

## Requirements

- Terraform
- AWS Account

## Infrastructure Components

- A VPC
- One public subnet
- An EC2 instance running Ubuntu
- An S3 bucket

## Steps to Deploy the Infrastructure

1. **Clone the Repository**:
   ```bash
   git clone git@github.com:yourusername/infrastructure-terraform.git
   cd infrastructure-terraform
   ```

2. **Configure AWS Credentials**:
   Ensure your AWS credentials are configured. You can use the `aws configure` command or set environment variables.

3. **Edit Variables**:
   Edit the `variables.tf` file to include your SSH key name:
   ```hcl
   variable "key_name" {
     description = "The name of the SSH key pair"
     type        = string
     default     = "your-key-name"
   }
   ```

4. **Initialize Terraform**:
   ```bash
   terraform init
   ```

5. **Plan the Infrastructure**:
   ```bash
   terraform plan
   ```

6. **Apply the Configuration**:
   ```bash
   terraform apply
   ```

## Accessing the EC2 Instance

After deployment, you can access the EC2 instance using the public IP address provided in the output:
```bash
ssh -i path-to-your-key.pem ubuntu@<instance_public_ip>
