# Task 9: Access S3 from Ubuntu using IAM Roles & Policies

## Objective
Learn how to securely access AWS S3 from an EC2 instance using **IAM Roles**, avoiding the use of hardcoded access keys.

---

## Prerequisites
- AWS account with permissions to create **IAM roles** and **EC2 instances**.
- An **Ubuntu EC2 instance** running.
- S3 bucket already created for testing.

---

## Steps

### 1. Create IAM Role
1. Go to the **IAM Console** → Roles → Create Role.
2. Select **AWS service** → EC2 → Next: Permissions.
3. Attach policy **AmazonS3ReadOnlyAccess** (or a custom policy if needed).
4. Name the role, e.g., `EC2S3AccessRole`.
5. Note the Role ARN for reference.

---

### 2. Attach IAM Role to EC2
1. Open **EC2 Console** → Instances → Select your Ubuntu instance.
2. **Actions** → Security → Modify IAM Role → Select `EC2S3AccessRole`.
3. Save the changes.

---

### 3. Verify IAM Role Access on Ubuntu
1. SSH into your Ubuntu EC2 instance:
ssh -i your-key.pem ubuntu@<EC2_PUBLIC_IP>
### Verify IAM Role Access on Ubuntu
2. Check if the IAM role is attached:
curl http://169.254.169.254/latest/meta-data/iam/info
3.List S3 buckets using AWS CLI:
aws s3 ls
