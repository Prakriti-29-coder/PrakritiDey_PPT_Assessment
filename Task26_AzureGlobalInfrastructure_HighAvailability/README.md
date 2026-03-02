# Task 2: Azure Global Infrastructure + High Availability

## Objective
Deploy highly available VM infrastructure using Availability Sets, Availability Zones, Load Balancer, Azure Monitor, and diagnostic logging.

---

## Steps Completed

1. **Resource Group & VNet**
   - Created Resource Group: `RG-HA-Lab`  
   - Created Virtual Network and subnets.

2. **VM Deployment**
   - Deployed 2 VMs in an Availability Set.  
   - Deployed 2 VMs in a different Availability Zone.

3. **Load Balancer**
   - Created Public Azure Load Balancer.  
   - Added all 4 VMs to the Backend Pool.  
   - Configured Health Probe and Load Balancing Rule.

4. **Azure Monitor & Alerts**
   - Created Action Group: `NewAction`  
   - Alert Rule: `NewAlert` monitoring `Percentage CPU` > 80%  
   - Evaluation: 1-minute interval, 5-minute lookback, Severity: Informational  
   - Email notifications via `EmailAlert`.

5. **Diagnostic Logs**
   - Created Storage Account: `halabdiagnostics`  
   - Enabled VM diagnostics and boot diagnostics → logs sent to storage account.

6. **High Availability Test**
   - Connected to VMs via RDP/SSH.  
   - Simulated VM shutdown → other VMs remained accessible.  
   - Verified alert triggered and logs recorded.  
   - Restarted VM → confirmed logs updated.

7. **Clean-Up**
   - Deleted Resource Group `RG-HA-Lab` to remove all resources.

---

**Outcome:**  
- VMs deployed across Availability Sets and Zones  
- Load Balancer distributing traffic and monitoring health  
- Alerts and diagnostic logs configured  
- High availability successfully demonstrated
