# Task 18: Azure Virtual Machine (Easy Task)

**Objective:** Launch and configure a basic Azure VM and verify access via SSH.

---

## Step 1: Create Resource Group
- Login to Azure Portal → Search **Resource Groups** → Create
- **Name:** ppt-rg, **Region:** East Asia

---

## Step 2: Create Virtual Machine
- Search **Virtual Machines** → Create → Azure Virtual Machine
- **VM Name:** ppt-vm
- **Resource Group:** ppt-rg
- **Region:** East Asia (Zone 3)
- **OS:** Ubuntu 24.04 LTS
- **Size:** Standard D2s v3 (2 vCPU, 8 GiB)
- **Authentication:** SSH key, **Username:** azureuser

---

## Step 3: VM Overview
- **Status:** Running, **Public IP:** 52.184.86.255

---

## Step 4: Connect via SSH
```bash
ssh -i "C:\Users\Dell\Downloads\ppt-vm_key.pem" azureuser@52.184.86.255
