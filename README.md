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

## Create A VPC
- Go to VPC → Your VPCs → Create VPC
    - Name: Lab-VPC
    - IPv4 CIDR: 10.0.0.0/16
    - Tenancy: Defualt

![Successfully created VPC](./images/created_vpc.png)

## Create Subnets
- Subnets → Create subnet
    - Select `Lab-VPC`, AZ `(select favorite location)`
    - CIDR block `10.0.1.0/24`, Name tag = `Public-Subnet`
    - Repeat for CIDR `10.0.2.0/24`, Name = `Private-Subnet`

![Successfully created Subnets](./images/created_subnets.png)

## Questions to Answer At The End of The Lab
- What is a VPC?
- What is a CIDR block?
- What is a Subnet?
- Difference Between a VPC & a Subnet?
- IPv4 and IPv6 CIDR block?
- While creating a Subnet, what is the importance of choosing an Availability Zone?
- When choosing a Subnet's IPv4 CIDR, why must it lie within the VPC's IPv4 CIDR block?