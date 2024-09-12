# Terraform Setup for Flask, Nginx, and MySQL on AWS

This repository contains Terraform configuration files to deploy a simple web application setup on AWS. It includes:

- A **VPC** with a **public subnet**.
- EC2 instances for **Flask** (application), **Nginx** (web server), and **MySQL** (database).
- Security groups to manage network access.
- An **Internet Gateway** for public access.

## Prerequisites

- Terraform installed on your local machine.
- AWS CLI configured with appropriate permissions.
- AWS account with access to create EC2 instances and other resources.

## Configuration

1. **Provider Configuration:**
   - AWS region is set to `us-east-1`.

2. **VPC Setup:**
   - A VPC is created with CIDR block `10.0.0.0/16`.

3. **Subnet and Internet Gateway:**
   - A public subnet with CIDR block `10.0.1.0/24` is created.
   - An Internet Gateway is attached to the VPC for public internet access.

4. **EC2 Instances:**
   - **Flask Instance**: Runs the Flask application.
   - **Nginx Instance**: Serves as the web server.
   - **MySQL Instance**: Hosts the MySQL database.
   - All instances use a security group to control access.

5. **Security Groups:**
   - **Flask Security Group**: Allows traffic on port 5000.
   - **Nginx Security Group**: Allows HTTP traffic on port 80.
   - **MySQL Security Group**: Allows traffic on port 3306 from within the VPC.

## Usage

1. **Initialize Terraform:**
   ```bash
   terraform init

