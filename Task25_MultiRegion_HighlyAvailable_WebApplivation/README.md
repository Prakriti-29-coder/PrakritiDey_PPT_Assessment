# High Availability Architecture using Application Load Balancer (AWS)

## Project Overview

In this project, I created a High Availability web architecture using Application Load Balancer and two EC2 instances in AWS.

The load balancer distributes incoming traffic between multiple servers placed in different Availability Zones to ensure better performance and reliability.

---

## Objective

- Deploy two EC2 instances
- Configure Application Load Balancer
- Set up Target Group with health checks
- Implement High Availability across two Availability Zones
- Monitor EC2 using CloudWatch

---

## AWS Services Used

- Amazon EC2
- Application Load Balancer (ALB)
- Target Group
- Security Groups
- CloudWatch

All resources were created using the AWS Management Console.

---

## Architecture Flow

User → Application Load Balancer → Target Group → EC2 Instances

Traffic is distributed between Instance 1 and Instance 2.

---

## Step-by-Step Implementation

### Step 1: Created VPC and Subnets

- Created a custom VPC
- Created two public subnets in different Availability Zones
- Attached an Internet Gateway
- Updated route table with:

```
0.0.0.0/0 → Internet Gateway
```

---

### Step 2: Launched EC2 Instances

- AMI: Amazon Linux
- Instance Type: t2.micro
- Network: Custom VPC
- Subnets: Public Subnet 1 and Public Subnet 2
- Auto-assign Public IP: Enabled

Two instances were launched in different Availability Zones for High Availability.

---

### Step 3: Configured Security Groups

**Load Balancer Security Group:**
- Allowed HTTP (Port 80) from 0.0.0.0/0

**EC2 Security Group:**
- Allowed HTTP (Port 80) from Load Balancer Security Group
- Allowed SSH (Port 22) from my IP

---

### Step 4: Installed Web Server on EC2

Connected to both instances via SSH and installed Apache:

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

Created test web pages:

Instance 1:
```bash
echo "Hello from Instance 1" > /var/www/html/index.html
```

Instance 2:
```bash
echo "Hello from Instance 2" > /var/www/html/index.html
```

---

### Step 5: Created Target Group

- Target Type: Instance
- Protocol: HTTP
- Port: 80
- Health Check Path: /

Both EC2 instances were registered and verified as Healthy.

---

### Step 6: Created Application Load Balancer

- Type: Internet-facing
- Listener: HTTP (Port 80)
- Subnets: Both public subnets
- Default action: Forward to Target Group

---

### Step 7: Testing

Used the Load Balancer DNS name in browser.

On refreshing multiple times, the response alternates between:

- Hello from Instance 1
- Hello from Instance 2

This confirms that load balancing and high availability are working successfully.

---

## Monitoring

Configured a CloudWatch alarm for EC2 CPU utilization to monitor performance.

---

## Final Outcome

Successfully deployed a High Availability web architecture in AWS.

The Application Load Balancer distributes traffic across multiple EC2 instances in different Availability Zones, ensuring reliability and scalability.
