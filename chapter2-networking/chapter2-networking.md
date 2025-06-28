# Chapter 2 – Advanced Networking & Security

## Objective
Create a tiered virtual network with secure subnet segmentation, internal access controls using ASGs, and deploy Azure Bastion for private access.

## Subnet Structure

| Subnet Name         | Address Range   | Purpose       |
|---------------------|-----------------|---------------|
| web-subnet          | 10.10.1.0/24    | Frontend VMs  |
| app-subnet          | 10.10.2.0/24    | Backend VMs   |
| db-subnet           | 10.10.3.0/24    | SQL, storage  |
| mgmt-subnet         | 10.10.4.0/24    | Secure access |
| AzureBastionSubnet  | 10.10.5.0/24    | Secure access |

## NSGs and ASGs

| NSG           | Applied To     | Rules Summary                  |
|---------------|----------------|--------------------------------|
| nsg-web-subnet| web-subnet     | Allow HTTP/HTTPS               |
| nsg-app-subnet| app-subnet     | Allow traffic from web-subnet  |
| nsg-db-subnet | db-subnet      | Allow traffic from app-subnet  |

## Azure Bastion

- Name: `bastion-belgium`
- Region: `West Europe`
- Subnet: `AzureBastionSubnet`
- Public IP: `pip-bastion-belgium`
