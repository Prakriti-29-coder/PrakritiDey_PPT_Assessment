# Task 20: Azure VNet (Basic Networking Practical)

## Objective
The goal of this task is to **understand basic cloud networking in Azure** by creating a Virtual Network (VNet), configuring subnets, and applying Network Security Group (NSG) rules. This task is completed **without deploying any VMs or paid resources**, so it incurs **no charges**.

---

## Prerequisites
- Azure account (Free account or any account without trial credits)
- Access to [Azure Portal](https://portal.azure.com)
- Basic understanding of networking concepts (VNet, subnet, NSG)

---

## Steps Performed

### Step 1: Create Resource Group
1. Navigate to **Resource Groups → + Create**.
2. Fill in:
   - **Resource Group Name**: `RG-VNet-Task20`
   - **Region**: East US (or any region)
3. Click **Review + Create → Create**.

---

### Step 2: Create Virtual Network (VNet)
1. Go to **Virtual Networks → + Create**.
2. Fill in the Basics tab:
   - **Resource Group**: `RG-VNet-Task20`
   - **Name**: `MyVNet`
   - **Region**: Same as Resource Group
3. Click **Next: IP Addresses**.
4. Configure IP Address Space:
   - **Address space**: `10.0.0.0/16`
5. Add Subnet1:
   - **Name**: `Subnet1`
   - **Address range**: `10.0.1.0/24`
6. (Optional) Add Subnet2:
   - **Name**: `Subnet2`
   - **Address range**: `10.0.2.0/24`
7. Click **Review + Create → Create**.

---

### Step 3: Create Network Security Group (NSG)
1. Search for **Network Security Groups → + Create**.
2. Fill in:
   - **Resource Group**: `RG-VNet-Task20`
   - **Name**: `MyNSG`
   - **Region**: Same as VNet
3. Click **Review + Create → Create**.

---

### Step 4: Configure NSG Rules
1. Open **MyNSG → Inbound Security Rules → + Add**.
2. Add a rule:
   - **Source**: Any
   - **Source Port Range**: *
   - **Destination**: Any
   - **Destination Port Range**: 22 (for Linux) or 3389 (for Windows)
   - **Protocol**: TCP
   - **Action**: Allow
   - **Priority**: 100
   - **Name**: `AllowSSH` (or `AllowRDP`)
3. Click **Add**.

---

### Step 5: Associate NSG with Subnet
1. Go to **MyNSG → Subnets → + Associate**.
2. Select:
   - **Virtual Network**: `MyVNet`
   - **Subnet**: `Subnet1`
3. Click **OK**.

---

## Outcome
- Successfully created **Azure Virtual Network (`MyVNet`)** with subnets.  
- Created **Network Security Group (`MyNSG`)** with inbound rules.  
- Associated NSG with subnet.  
- Verified configuration with screenshots.  

---

**Note:** Do **not create VMs, public IPs, or other paid services**, as these will incur charges. This task focuses on free resources only.
