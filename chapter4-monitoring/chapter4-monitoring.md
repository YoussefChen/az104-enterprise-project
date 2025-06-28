# Chapter 4 – Monitoring & RBAC

## 🧠 What Was Done

- Created Log Analytics Workspace (`law-belgium-monitoring`)
- Enabled diagnostics on VMs, VMSS, and Load Balancer
- Set up alerting rules (CPU, health probe, instance scaling)
- Implemented RBAC policies per group


### Sample Alert: CPU Over 70% on Web VMs

- Condition: CPU > 70%
- Email notification to owner


## 🔐 RBAC Overview

| Group           | Role                   | Scope                |
|-----------------|------------------------|----------------------|
| Cloud-Admins    | Owner                  | Subscription-wide    |
| DevOps-Engineers| Contributor            | Compute RG           |
| Support-Desk    | Reader + Monitoring    | Management RG        |
| Network Engineer| Network Contributor    | Networking RG        |


### Access Test

Logged in as `Monitoring Operator` → Read-only to VMs, full access to alerts.

