# Task 3 – IAM + RBAC + Least Privilege (AWS + Azure)

## Objective
Implement role-based access control with least privilege in AWS IAM and Azure Entra ID.

---

## AWS IAM

**User:** Developer  
**Permissions:**  
- AmazonEC2FullAccess → EC2 actions allowed  
- Custom policy `DenyS3Delete` → S3 delete blocked  

**Test:**  
- Launch/stop EC2 instance → works  
- Delete S3 bucket/object → denied  

---

## Azure Entra ID

**Steps:**  
1. Create Resource Group → `DevRG`  
2. Create user → Developer  
3. Assign roles:  
   - Reader on `DevRG` → view only  
   - Virtual Machine Contributor on `DevVM` → manage VM  

**Test:**  
- View RG → allowed  
- Start/stop `DevVM` → allowed  
- Delete RG or other resources → denied  

---

## Conclusion
Least privilege enforced: users can perform only necessary actions, restricted from dangerous operations.
