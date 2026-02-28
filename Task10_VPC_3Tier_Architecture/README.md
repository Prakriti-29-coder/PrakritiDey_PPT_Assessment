# 3-Tier VPC Architecture – Single AZ

## VPC Details
- Name: My3TierVPC
- CIDR: 10.0.0.0/16

## Subnets
- Public: 10.0.1.0/24
- App: 10.0.2.0/24
- DB: 10.0.3.0/24

## Route Tables
- PublicRT: 0.0.0.0/0 → IGW
- PrivateRT: 0.0.0.0/0 → NAT Gateway

## IGW
- Name: MyIGW
- Attached to VPC

## NAT Gateway
- Name: MyNAT
- Public Subnet: PublicSubnet

## Access
- SSH into Web EC2, then tunnel to App/DB
