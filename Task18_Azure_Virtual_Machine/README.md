# Task 18: Azure Virtual Machine (Easy Task)

## Objective
Launch and configure a basic Azure Virtual Machine (VM) to understand Azure compute fundamentals.

---

## Task Overview
- **Task Name:** Launch and Configure an Azure VM  
- **Difficulty Level:** Easy  
- **Goal:** Create a VM and access it via RDP (Windows) or SSH (Linux).

---

## Steps Performed

### 1. Login to Azure Portal
- Navigate to [Azure Portal](https://portal.azure.com/) and log in with your credentials.

### 2. Create a Virtual Machine
- Go to **Azure Virtual Machines** → **Create VM**.  
- Fill in the details:  
  - **Subscription & Resource Group:** Select existing or create new  
  - **VM Name:** e.g., `MyFirstVM`  
  - **Region:** Choose a region closest to you  
  - **Image:** Windows Server 2019 / Ubuntu 20.04 LTS  
  - **Size:** Select a size (B1s for basic task)  
  - **Authentication:**  
    - Windows → Password  
    - Linux → SSH Key  
  - **Inbound Ports:** Enable RDP (3389) for Windows / SSH (22) for Linux

### 3. Review & Create
- Review the configuration and click **Create**.  
- Wait for deployment to complete.

### 4. Access the VM
- **Windows VM:** Use Remote Desktop Protocol (RDP)  
  - Open `mstsc`, enter the public IP, and connect with username & password.  
- **Linux VM:** Use SSH  
  ```bash
  ssh username@PublicIP
