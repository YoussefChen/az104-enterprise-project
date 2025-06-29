# AZ-104 Enterprise Cloud Portfolio (Advanced)

This project simulates a real-world Azure environment for a global company using best practices in RBAC, networking, scaling, and governance.

Each chapter builds on the previous one — all components are interdependent and demonstrate real-world scenarios aligned with AZ-104 certification skills.

---

## 🔖 Chapters

- [Chapter 1 – Tenant Setup & RBAC](./chapter1-setup/chapter1-setup.md)  
  Azure AD setup with users and groups (Cloud-Admins, DevOps-Engineers, etc.), and directory-level RBAC preparation.

- [Chapter 2 – Core Networking](./chapter2-networking/chapter2-networking.md)  
  Created hub VNet with multiple subnets (Web, App, DB, Bastion), NSGs, ASGs, and subnet IP planning.

- [Chapter 3 – Azure Bastion Deployment](./chapter3-bastion/chapter3-bastion.md)  
  Secured VM access through Bastion inside `bastionSubnet`. Ensured no public IPs on compute resources.

- [Chapter 4 – Virtual Machine Scale Set (VMSS)](./chapter4-vmss/chapter4-vmss.md)  
  Deployed scalable backend using VMSS with a custom cloud-init NGINX script in the app subnet.

- [Chapter 5 – Application Gateway](./chapter5-appgw/chapter5-appgw.md)  
  Configured HTTP routing to VMSS backend pool using App Gateway with frontend listener and probe.

- [Chapter 6 – Routing Rules & Health Probe Fixes](./chapter6-routing/chapter6-routing.md)  
  Fixed `502 Bad Gateway` error by reconfiguring the health probe and backend target settings correctly.

- [Chapter 7 – VMSS Network Fixes + GitHub Integration](./chapter7-vmss-fix/chapter7-vmss-fix.md)  
  Recreated VMSS in the correct subnet (`app-subnet`), updated custom script, attached it to App Gateway, and documented all changes to GitHub.

- [Chapter 8 – IAM & RBAC Assignments](./chapter8-iam/chapter8-iam.md)  
  Assigned scoped roles to users and groups using built-in RBAC roles like Reader and Contributor at RG level.

- [Chapter 9 – Azure Governance](./chapter9-governance/chapter9-governance.md)  
  Applied locks, tags, and created Azure Policy to enforce tag rules across selected resource groups.

---

## 🧠 Key Skills Demonstrated

- VNet design and NSG/ASG segmentation
- Azure Bastion for secure access
- VMSS deployment with automation
- App Gateway routing and backend probe troubleshooting
- Role-Based Access Control (RBAC)
- Resource Locks and Azure Policy enforcement
- Organized GitHub documentation

---

## 📁 Structure

Each chapter folder contains:

- `README.md` with a detailed explanation
- Screenshots documenting portal steps
- Markdown-friendly architecture diagrams

---

## 👨‍💻 Author

**Youssef Chennoufi** – Azure Administrator & Cloud Enthusiast from Belgium 🇧🇪  
*Certified in Microsoft AZ-104: Azure Administrator*  
Focus: Enterprise cloud environments, automation, and clean architecture.

---

## 🧭 What's Next

> A second portfolio project will simulate a hybrid Azure/AD DS setup with Azure Files, custom domain-joined VM deployment, Azure Backup, and alerting using Log Analytics.

Stay tuned — or [contact me] if you're a recruiter, employer, or fellow Azure learner!

---

*This project follows the AZ-104 objectives but takes them deeper to simulate production-grade architecture.*
