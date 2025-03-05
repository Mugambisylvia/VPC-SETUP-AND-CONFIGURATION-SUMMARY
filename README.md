# VPC-SETUP-AND-CONFIGURATION-SUMMARY
Objective: The goal of this task is to familiarize interns with creating and configuring a Virtual Private Cloud (VPC) in AWS, including key components such as subnets, route tables, and security groups.
# VPC Setup and Configuration Summary 

## Overview
This repository documents my **Virtual Private Cloud (VPC) setup and configuration** journey. It includes the **CIDR blocks, subnets, gateways, security configurations, and EC2 instance setup** that I implemented.

## VPC and Subnet Configuration
###  CIDR Blocks Used
```bash
VPC CIDR Block: 10.0.0.0/16  # Allows up to 65,536 IPs
Public Subnet CIDR: 10.1.0.0/24  # 256 IPs for public-facing resources
Private Subnet CIDR: 10.0.0.0/24  # 256 IPs for private resources
```

## Internet and NAT Gateway Setup
###  Internet Gateway
```bash
# Attached to the VPC to enable public subnet communication with the internet.
# Allows outbound and inbound traffic for resources like EC2 instances.
```

###  NAT Gateway
```bash
# Configured in the public subnet to allow private instances outbound internet access
# (e.g., software updates) without direct exposure to the internet.
```

## Security Group and Network ACL Configuration
###  Security Groups
```bash
# Public EC2 Instance SG: Allows SSH (22), HTTP (80), and HTTPS (443) traffic.
# Private EC2 Instance SG: No inbound traffic except from the public subnet; 
# outbound traffic allowed via NAT Gateway.
```

###  Network ACL (NACL)
```bash
# Public Subnet NACL: Inbound allows SSH, HTTP, and HTTPS; outbound allows all traffic.
# Private Subnet NACL: Restricts external internet access, allowing only internal traffic; 
# outbound enabled for NAT Gateway.
```

## EC2 Instances and Their Roles
### ☁️ Public EC2 Instance
```bash
Role: Web server
Subnet: Public
Access: SSH + HTTP/HTTPS
Purpose: Hosts web applications, accessible from the internet.
```

###  Private EC2 Instance
```bash
Role: Backend service
Subnet: Private
Access: No direct internet access, only outbound via NAT Gateway.
Purpose: Handles sensitive data and secure operations.
```

## Screenshots of the Setup
Below are some screenshots showing the **successful creation and configuration** of VPC and EC2 instances:

-  Public VPC
-  Private VPC
-  Public and Private Subnets
-  Route Table Configuration
-  Internet Gateway Setup
-  Successfully Launched EC2 Instances

---

