# AWS VPC Peering Between Production VPC and Test VPC

## Project Overview

This project demonstrates how to establish secure private communication between two Amazon Virtual Private Clouds (VPCs) using **VPC Peering**.

Two separate VPCs, **Production VPC** and **Test VPC**, were created with public and private subnets. Internet Gateways, NAT Gateways, Route Tables, Security Groups, and EC2 instances were configured in both VPCs. A VPC Peering connection was then established to enable secure communication between the EC2 instances using their private IP addresses.

---

# Architecture

![Architecture](screenshots/Architecture.png)

## Architecture Overview

The architecture consists of two isolated VPCs connected through a VPC Peering connection.

### Production VPC (10.0.0.0/24)

- Public Subnet
- Private Subnet
- Internet Gateway
- NAT Gateway
- EC2 Instance

### Test VPC (10.1.0.0/24)

- Public Subnet
- Private Subnet
- Internet Gateway
- NAT Gateway
- EC2 Instance

### VPC Peering Connection

- Connects the Production VPC and Test VPC.
- Enables secure communication using private IP addresses.
- Route Tables forward traffic through the peering connection.
- Security Groups allow SSH and ICMP (Ping) traffic.

---

# AWS Services Used

- Amazon VPC
- Amazon EC2
- VPC Peering
- Public Subnets
- Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups

---

# Project Workflow

1. Created the Production VPC.
2. Created the Test VPC.
3. Created Public and Private Subnets in both VPCs.
4. Attached Internet Gateways.
5. Created NAT Gateways.
6. Configured Route Tables.
7. Launched EC2 instances.
8. Configured Security Groups.
9. Created a VPC Peering Request.
10. Accepted the VPC Peering Request.
11. Updated Route Tables with VPC Peering routes.
12. Verified connectivity using Ping.

---

# Project Structure

AWS-VPC-and-VPC-Peering/
│
├── README.md
│
└── screenshots/
    ├── Architecture.png
    ├── EC2-Instances.png
    ├── NATGateway.png
    ├── Ping-Prod.png
    ├── Ping-Test.png
    ├── RouteTables.png
    ├── SecurityGroups.png
    ├── Subnets.png
    ├── VPCs.png
    ├── vpc-peering-created.png
    └── vpc-peering-accepted.png
---

# Screenshots

## 1. VPCs

![VPCs](screenshots/VPCs.png)

Two separate VPCs were created with different CIDR blocks to isolate network resources.

- **Production VPC:** 10.0.0.0/24
- **Test VPC:** 10.1.0.0/24

---

## 2. Subnets

![Subnets](screenshots/Subnets.png)

Public and Private Subnets were created in both VPCs.

- Public Subnets host internet-facing resources.
- Private Subnets host internal resources.

---

## 3. Route Tables

![Route Tables](screenshots/RouteTables.png)

Route Tables were configured to:

- Provide internet connectivity.
- Route traffic between both VPCs through the VPC Peering connection.

---

## 4. NAT Gateway

![NAT Gateway](screenshots/NATGateway.png)

A NAT Gateway was deployed in the public subnet of each VPC to provide outbound internet access for EC2 instances located in the private subnets.

---

## 5. EC2 Instances

![EC2 Instances](screenshots/EC2-Instances.png)

Amazon EC2 instances were launched in both the Production VPC and Test VPC.

These instances were used to verify connectivity over the VPC Peering connection using their private IP addresses.

---

## 6. Security Groups

![Security Groups](screenshots/SecurityGroups.png)

Security Groups were configured to allow the required inbound traffic.

- SSH (Port 22) for secure remote access.
- ICMP (Ping) for connectivity testing.

---

## 7. VPC Peering Request Created

![VPC Peering Created](screenshots/vpc-peering-created.png)

A VPC Peering connection request was created between the Production VPC and Test VPC.

---

## 8. VPC Peering Request Accepted

![VPC Peering Accepted](screenshots/vpc-peering-accepted.png)

The VPC Peering request was accepted successfully, and the connection status changed to **Active**.

---

## 9. Ping Test (Production → Test)

![Ping Production](screenshots/Ping-Prod.png)

The EC2 instance in the Production VPC successfully communicated with the EC2 instance in the Test VPC using its private IP address.

---

## 10. Ping Test (Test → Production)

![Ping Test](screenshots/Ping-Test.png)

The EC2 instance in the Test VPC successfully communicated with the EC2 instance in the Production VPC using its private IP address, confirming bidirectional communication through the VPC Peering connection.

---

# Result

Successfully completed the following tasks:

- Created two isolated Amazon VPCs.
- Configured Public and Private Subnets.
- Attached Internet Gateways.
- Created NAT Gateways.
- Configured Route Tables.
- Launched EC2 instances.
- Configured Security Groups.
- Established a VPC Peering connection.
- Updated Route Tables for VPC Peering.
- Verified private communication between EC2 instances using their private IP addresses.

---

# Author

**Manya Gupta**
