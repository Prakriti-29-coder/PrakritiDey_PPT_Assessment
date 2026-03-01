# Task 22: Azure Monitoring & Diagnostics (Easy)

## Objective
The goal of this task is to **enable monitoring and diagnostics for an Azure resource** using Azure Monitor. This allows tracking metrics and resource activity, all **without incurring any charges** by using free-tier resources.

---

## Prerequisites
- Azure account (Pay-As-You-Go or Free tier)
- Access to [Azure Portal](https://portal.azure.com)
- No prior resources required

---

## Steps Performed

### Step 1: Create a Free Resource for Monitoring
1. Go to **Azure Portal → Storage Accounts → + Create**  
2. Fill in the form:
   - **Resource Group:** `RG-Task22`  
   - **Storage Account Name:** `task22storage`  
   - **Region:** Any region  
   - **Performance:** Standard  
   - **Replication:** Locally Redundant (LRS)  
   - **Access tier:** Hot  
3. Click **Review + Create → Create**  

> Only a basic Storage Account is used, which is free.

---

### Step 2: Generate Activity
1. Go to **Storage Account → Containers → + Container**  
   - Name: `task22container`  
   - Click **Create**  
2. Open `task22container → Upload` a small text file (~1 KB)  
3. Click **Upload**  

> This generates activity (Requests / Ingress / Egress) so metrics appear in Azure Monitor.

---

### Step 3: View Metrics in Azure Monitor
1. Go to **Azure Monitor → Metrics → Select a resource**  
2. Filter by **Resource Type → Storage Accounts**  
3. Select your **Storage Account (`task22storage`)**  
4. Choose metrics such as:  
   - **Total Requests**  
   - **Ingress / Egress**  
   - **Blob Capacity**  
5. Adjust **time range** (1h, 24h, etc.) to view activity.

---

### Step 4: Enable Diagnostics 
1. Go to **Storage Account → Diagnostics settings → + Add diagnostic setting**  
2. Enable metrics/logs to **Log Analytics** or **Storage Account**  
3. Click **Save**  

> This shows the configuration of diagnostics without any cost.

## Outcome
- Successfully created a free Storage Account for monitoring  
- Generated activity to populate Azure Monitor metrics  
- Enabled optional diagnostics settings  
- Captured required screenshots as proof  


---

**Note:**  
- Avoid creating paid resources (VMs, premium storage, public IPs)  
- Only use small free-tier resources and delete everything after the lab
