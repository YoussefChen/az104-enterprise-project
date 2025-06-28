# Chapter 1 – Core Setup: Resource Groups, AAD, RBAC

## 🔍 Objective
Setup a foundational enterprise-like structure in Azure using:
- 4 Resource Groups
- Simulated AAD Groups and Users
- Role-Based Access Control (RBAC)
- Resource Locks

---

## 🏗️ Resource Group Architecture

| Name                  | Purpose                       | Region      |
|-----------------------|-------------------------------|-------------|
| rg-management-belgium | Monitoring, logging, policies | West Europe |
| rg-networking-belgium | Virtual Networks, NSGs        | West Europe |
| rg-compute-belgium    | VMs, VMSS | West Europe       |             |
| rg-storage-belgium    | Blobs, queues, backup         | West Europe |


---

## 👥 Azure AD Groups and Users

| Group Name        | Role                          |
|-------------------|-------------------------------|
| Cloud-Admins      | Full access to all infra      |
| DevOps-Engineers  | Scoped compute/network access |
| Support-Desk      | Read-only monitoring          |

| Username            | Assigned Group    |
|---------------------|-------------------|
| Youssef Chennoufi   | Cloud-Admins      |
| Backend Developer   | DevOps-Engineers  |
| Devops Specialist   | DevOps-Engineers  |
| Frontend Developer  | DevOps-Engineers  |
| Network Engineer    | DevOps-Engineer   |
| Monitoring Operator | Support-Desk      |


---

## 🔐 Locks

Applied a **Delete lock** on `rg-management-belgium` to prevent accidental removal of monitoring/logging.

---

## ✅ Key Learnings

- Logical separation of resources improves security and cost tracking.
- RBAC is essential for managing access at scale.
- Locking critical resources is a best practice in production environments.

---


