# Task 23: Azure Resource Manager & Cost Management (Easy)

## Objective
The goal of this task is to **understand Azure Resource Manager (ARM), resource groups, and cost tracking**. This is done safely using an empty resource group and viewing its cost, all **without incurring any charges**.

---

## Prerequisites
- Azure account (Pay-As-You-Go or Free tier)
- Access to [Azure Portal](https://portal.azure.com)
- No prior resources required

---

## Steps Performed

### Step 1: Create a Resource Group 
1. Go to **Azure Portal → Resource Groups → + Create**  
2. Fill in the form:
   - **Resource Group Name:** `RG-Task23`  
   - **Region:** Any region  
3. Click **Review + Create → Create**  

---

### Step 2: Explore Resource Visualizer / ARM
1. Open the resource group `RG-Task23`  
2. Click **Resource Visualizer**  
   - Since the group is empty, no resources or diagram appear (this is normal)  
3. Click **Export template** (if available) to view the **ARM template** of the resource group  

> This demonstrates understanding of **Azure Resource Manager (ARM)**.

---

### Step 3: View Cost Analysis
1. Go to **Cost Management + Billing → Cost Management → Cost analysis**  
2. Set **Scope → Resource Group → RG-Task23**  
3. Set **Time range** → Last 7 days or Current month  
4. The page should show **“No cost reported during this period”** since no paid resources were created  

> This demonstrates cost tracking without any charges.


## Outcome
- Created a resource group  
- Explored Resource Visualizer / ARM template  
- Viewed Cost Analysis for the group → $0 cost
- Took required screenshots as proof  
