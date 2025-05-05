# Building a Custom VPC with Public & Private Subnets

## Objective: Stand up a secure AWS network that has:
- A public subnet for internet-facing resources
- A private subnet for backend resources
- An Internet Gateway (IGW) and NAT Gateway for controlled traffic

## Prerequisites
- An AWS account with Admin or VPC privileges
- AWS CLI configured
- A laptop with 3 hours set aside

## Architecture Overview
```vbnet
Internet  
   ↓  
[IGW]  
   ↓  
Public Route Table ── Public Subnet ── EC2 (Bastion/Web)  
   ↓ NAT Gateway  
Private Route Table ─ Private Subnet ─ EC2 (App/DB)
```

## Creating A VPC
- Go to VPC → Your VPCs → Create VPC
    Name: Lab-VPC
    IPv4 CIDR: 10.0.0.0/16
    Tenancy: Defualt

