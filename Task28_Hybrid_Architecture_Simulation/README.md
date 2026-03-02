# Task 4 — Hybrid Architecture Simulation (Azure)

## Objective
Secure Private VM access via Bastion Host with subnet isolation and controlled SSH.

---

## Architecture

User (Local Machine)
│
Direct SSH blocked
│
Azure Portal → Bastion Host (HybridBastion, PublicSubnet)
│
SSH allowed
Private VM (NewVM, PrivateSubnet)


---

## Steps

1. **VNet & Subnets**
- VNet: `HybridVNet`
- PublicSubnet: 10.0.1.0/24 → Bastion
- PrivateSubnet: 10.0.2.0/24 → Private VM
- AzureBastionSubnet: 10.0.3.0/26 → Bastion

2. **Bastion Host**
- Name: `HybridBastion`, Tier: Standard, Public IP: `HybridVNetIPv4330`

3. **Private VM**
- Name: `NewVM`, Subnet: `PrivateSubnet`, OS: Ubuntu 24.04 LTS, SSH key: `NewVM_key.pem`, No public IP

4. **NSG Rule**
- Allow SSH (22) only from `AzureBastionSubnet` (10.0.3.0/26), Priority 100

5. **Route Table**
- PrivateSubnet: 10.0.0.0/16 → VirtualNetwork, 0.0.0.0/0 → NAT 

6. **Connect via Bastion**

Verify

whoami
hostname
ip a
