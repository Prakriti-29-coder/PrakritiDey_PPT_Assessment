# Task 3 – EBS Snapshot and Restore

## Objective
The objective of this task was to create a snapshot of an existing EBS volume and restore it to verify backup and recovery functionality.

---

## Steps Performed

1. Created a snapshot of the existing 2GB EBS volume attached to the Ubuntu EC2 instance.
2. Waited until the snapshot status became "Completed".
3. Created a new volume from the snapshot in Availability Zone.
4. Attached the restored volume to the EC2 instance.
5. Verified the new disk using the `lsblk` command.
6. Mounted the restored partition to a new directory.
7. Verified that the data from the original disk was successfully restored.

---

## Result

Successfully demonstrated AWS backup and recovery using EBS Snapshots.

This confirms:
- Data persistence
- Volume restoration
- Disaster recovery capability in AWS
