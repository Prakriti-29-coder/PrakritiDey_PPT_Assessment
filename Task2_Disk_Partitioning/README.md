# Task 2 – Disk Partitioning (MBR & GPT)

## Objective
The objective of this task was to understand disk partitioning by performing MBR partitioning in Ubuntu Linux and GPT partitioning in Windows.

---

## Part A – Ubuntu (MBR)

A new EBS volume was created and attached to the Ubuntu EC2 instance.

Steps performed:
- Verified new disk using `lsblk`
- Created partition using `fdisk`
- Formatted partition using `mkfs.ext4`
- Mounted disk to `/mnt/mydisk`
- Verified mount using `df -h`

This demonstrated traditional MBR-based partitioning in Linux.

---

## Part B – Windows (GPT)

A new EBS volume was attached to a Windows EC2 instance.

Steps performed:
- Opened Disk Management
- Initialized disk as GPT (GUID Partition Table)
- Created new simple volume
- Formatted using NTFS
- Verified partition style as GPT

This demonstrated modern GPT partitioning used in Windows systems.

---

## Result
Successfully performed disk partitioning using:
- MBR in Ubuntu
- GPT in Windows

This task improved understanding of storage management and partition structures.
