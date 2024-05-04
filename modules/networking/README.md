# Terraform Configuration for AWS VPC, Subnets, and NAT Gateway

This repository contains Terraform configuration files for creating an AWS VPC (Virtual Private Cloud) with public and private subnets, and setting up a NAT Gateway for private subnet internet access.

## Prerequisites

Before using this Terraform configuration, ensure you have the following prerequisites:

- [Terraform](https://www.terraform.io/downloads.html) installed on your machine.
- AWS credentials configured either using environment variables, shared credentials file, or IAM role.

## Usage

Follow these steps to deploy the infrastructure:

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/example/terraform-aws-vpc-nat.git
    ```

2. Navigate to the directory containing the Terraform configuration files:

    ```bash
    cd terraform-aws-vpc-nat
    ```

3. Initialize Terraform by running:

    ```bash
    terraform init
    ```

4. Review and customize the variables in `terraform.tfvars` file according to your requirements.

5. Execute Terraform plan to preview the changes:

    ```bash
    terraform plan
    ```

6. If the plan looks good, apply the changes to create the VPC, subnets, and NAT Gateway:

    ```bash
    terraform apply
    ```

7. After Terraform applies the changes successfully, it will output the IDs of the public and private subnets, as well as the ID and Elastic IP of the NAT Gateway.

8. When you're done, you can destroy the infrastructure by running:

    ```bash
    terraform destroy
    ```

## Configuration Details

### Resources

#### VPC

- **CIDR Block**: The CIDR block for the VPC.

#### Public Subnet

- **CIDR Blocks**: CIDR blocks for public subnets.
- **Map Public IP on Launch**: Indicates whether instances launched in this subnet should be assigned a public IP address.

#### Private Subnet

- **CIDR Blocks**: CIDR blocks for private subnets.

#### NAT Gateway

- **Allocation ID**: The allocation ID of the Elastic IP for the NAT Gateway.
- **Subnet ID**: The subnet ID of the public subnet where the NAT Gateway will be placed.

### Outputs

- **Public Subnet IDs**: IDs of the public subnets.
- **Private Subnet IDs**: IDs of the private subnets.
- **NAT Gateway ID**: ID of the NAT Gateway.
- **NAT Gateway Elastic IP**: Elastic IP of the NAT Gateway.

## Variables

The following variables can be customized to tailor the infrastructure to your needs:

- `region`: AWS region where the infrastructure will be deployed.
- `vpc_cidr`: CIDR block for the VPC.
- `public_subnet_cidr_blocks`: CIDR blocks for public subnets.
- `private_subnet_cidr_blocks`: CIDR blocks for private subnets.

