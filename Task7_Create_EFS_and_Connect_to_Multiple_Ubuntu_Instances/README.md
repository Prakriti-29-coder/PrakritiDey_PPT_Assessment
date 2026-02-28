# Task 7: Create EFS and Connect to Multiple Ubuntu Instances

## Objective
Mount shared storage across multiple EC2 instances using Amazon EFS (Elastic File System). This allows multiple instances to read/write to the same storage simultaneously.

## Steps Performed

1. **Created an Amazon EFS**
   - File system name: `prakriti-efs`
   - Performance mode: General Purpose
   - Throughput mode: Elastic
   - Lifecycle management: IA after 30 days, Archive after 90 days
   - Encryption: Enabled

2. **Created Mount Targets**
   - Subnets: us-east-1a, us-east-1b, us-east-1c, us-east-1d, us-east-1f
   - Security group: `sg-00efdcfb57286aa36` (EFS)

3. **Security Groups Configuration**
   - EC2 instances security group: `sg-0ee479089bf45db07` (launch-wizard-11)
   - EFS security group allowed **inbound NFS (TCP 2049)** from EC2 SG.

4. **Launched 2 Ubuntu EC2 Instances**
   - Ubuntu-Instance-1: `i-07214b1cc17e12072` 
   - Ubuntu-Instance-2: `i-0e8fdeed5403d7149` 

5. **Mounted EFS on Both Instances**
   - Installed NFS client (`nfs-common`)
   - Created mount point: `/mnt/efs`
   - Mounted using:
     sudo mount -t nfs4 -o nfsvers=4.1 fs-05774154e87c8d2ca.efs.us-east-1.amazonaws.com:/ /mnt/efs
   - Verified mount with `df -h` and `ls /mnt/efs`

6. **Tested Shared Access**
   - Created a test file on Instance 1:
     echo "Hello from Instance 1" | sudo tee /mnt/efs/test.txt
   - Verified on Instance 2:
     cat /mnt/efs/test.txt
   - Confirmed shared storage works.

7. **Configured Auto-Mount**
   - Added the following line to `/etc/fstab` on both instances:
     fs-05774154e87c8d2ca.efs.us-east-1.amazonaws.com:/ /mnt/efs nfs4 defaults,_netdev 0 0


