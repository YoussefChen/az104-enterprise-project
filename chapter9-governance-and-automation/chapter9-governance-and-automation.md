# Chapter 9: Azure Governance – Locks, Tags, and Policy

## Overview

To protect and structure resources in a production environment, this chapter applies governance tools such as:

- **Resource Locks** to prevent accidental deletion
- **Tags** for classification and billing
- **Azure Policies** to enforce standards across deployments

## Key Actions

- Locked down `rg-az104-project` from deletion
- Applied tags like `Environment`, `Project`, and `Owner` to major resources
- Created a policy to require the `Environment` tag on new resource groups
- Validated enforcement and did a tag audit using PowerShell

## Screenshots

| Filename                      | Description                                 |
|-------------------------------|---------------------------------------------|
| chapter9-lock-rg.png          | Delete lock applied to resource group       |
| chapter9-lock-appgw.png       | Lock on Application Gateway                 |
| chapter9-policy-assign.png    | Policy assignment to enforce Environment tag|
| chapter9-powershell-tags.png  | PowerShell tag audit output                 |
