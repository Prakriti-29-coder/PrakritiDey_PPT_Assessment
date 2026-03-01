# Task 21: Azure Entra ID (Users, Roles, Basic Identity Management)

## Objective
The goal of this task is to **understand identity and access management in Azure** by creating users and assigning roles in Azure Entra ID (formerly Azure Active Directory). This task is completed **without using any paid features**, so it incurs **no charges**.

---

## Prerequisites
- Azure account (Pay-As-You-Go or Free account)
- Access to [Azure Portal](https://portal.azure.com)
- Basic understanding of users and roles in Azure

---

## Steps Performed

### Step 1: Create Users
1. Go to **Azure Entra ID → Users → + New user → Create user**.  
2. Fill in the details:
   - **User principal name:** `alice@prakritidey2004outlook.onmicrosoft.com`  
   - **Display name:** `Alice Example`  
   - **Mail nickname:** `alice`  
   - **Password:** Auto-generate or set a temporary password  
3. Click **Create**.  

> Repeat for multiple users if needed.  

---

### Step 2: Assign Roles
1. Open the user profile (e.g., `Alice Example`).  
2. Click **Roles** (or **Directory roles / Assigned roles**) → **+ Add assignment**.  
3. Select a **built-in role** (free):
   - **Reader** → can view resources  
   - **Contributor** → can manage resources (without billing access)  
4. Click **Add** to assign the role.  

> Repeat for all users created.

## Outcome
- Successfully created users in Azure Entra ID.  
- Assigned built-in roles to users.  
- Verified setup via screenshots.  


---

