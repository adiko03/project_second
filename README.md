# Terraform Infrastructure as Code (IaC) Project

This project aims to create modular and scalable infrastructure using Terraform, facilitating the provisioning of networking resources, autoscaling configurations, and deployment environments. The infrastructure is organized into child modules, each serving specific functionalities.

## Project Structure:

### 1. Networking Module:

- **Objective:** Create networking resources including public and private subnets.
- **Features:**
  - **Public Subnets:** Allow dynamic creation based on specified CIDR blocks.
  - **Private Subnets:** Include a single NAT gateway, also dynamically configured based on provided CIDR blocks.
- **README:** Provides detailed instructions for configuring networking resources and specifying CIDR blocks.

### 2. Autoscaling Module:

- **Objective:** Implement autoscaling functionalities for application scalability.
- **Features:**
  - **Launch Template:** Configurable with default AMI and user-specified AMI.
  - **Security Groups:** Include dynamic ingress and egress rules attached to the launch template. Additional input variable for supplementary security groups.
- **README:** Offers clear guidelines for setting up autoscaling capabilities and defining security group rules.

### 3. Environments:

#### - Dev Environment:

- **Networking:**
  - Utilize the networking module to create public and private subnets.
  - Configure with three CIDR blocks for each subnet type.
- **Autoscaling:**
  - Use the autoscaling module to deploy an Apache web server with a user data script to private subnets.
- **Public module ALB:**
  - Implement an Application Load Balancer (ALB) to route incoming traffic to the autoscaling group.
- **Outputs:** Upon creation, the CLI should display the DNS name of the ALB for accessing the Apache web page.

#### - Prod Environment:

- **Static Website Hosting:**
  - Configure an S3 bucket and another resource to host the static website.
- **Outputs:** After creation, the CLI should provide the DNS name of the static website for access through the browser.

## Usage:

- Ensure you have Terraform installed locally.
- Clone this repository to your local machine.
- Navigate to the desired environment directory (e.g., `dev` or `prod`).
- Initialize Terraform by running `terraform init`.
- Review and adjust the variables in the `variables.tf` file as needed.
- Apply the configuration changes by running `terraform apply`.
- Follow the prompts to confirm and apply the changes.
- Once completed, Terraform will display the outputs containing relevant information about the created infrastructure.

## Notes:

- Feel free to customize the configurations according to your specific requirements.
- Refer to the official Terraform documentation for detailed information on Terraform commands and best practices.

# project_2
