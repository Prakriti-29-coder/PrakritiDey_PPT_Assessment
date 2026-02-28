# Task 4: ASG and ELB in EC2

## Objective
Configure an Auto Scaling Group (ASG) with an Elastic Load Balancer (ELB) in EC2 to achieve high availability and automatic scaling.

## Steps Performed

### 1. Launch Template
- Created a Launch Template for EC2 instances
- AMI: Amazon Linux 2 / Ubuntu
- Instance Type: t3.micro
- Security Group: HTTP (80) and SSH (22)
- Key pair configured

---

### 2. Load Balancer (ELB)
- Created an Application Load Balancer with an HTTP listener
- Configured target group for instances
- Selected at least 2 Availability Zones for high availability

---

### 3. Auto Scaling Group (ASG)
- Created ASG using the Launch Template
- Attached it to the ALB target group
- Configured scaling policy:
  - Minimum instances: 1
  - Desired instances: 2
  - Maximum instances: 3
- Verified instances launched successfully

---

### 4. Testing
- Accessed the ALB DNS to check instance availability
- Stopped one instance to confirm traffic routing to remaining instances
- Verified high availability and automatic scaling

---

### Notes
- Ensure security groups allow HTTP (80) and SSH (22)
- Use at least 2 Availability Zones for high availability
- Test scaling by changing instance count in ASG
