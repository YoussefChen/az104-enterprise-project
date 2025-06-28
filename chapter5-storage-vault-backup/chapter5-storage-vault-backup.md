# Chapter 5 – Storage, Key Vault, Backups

## ✅ Key Concepts Implemented

- 🔐 Private Storage Access via Private Endpoint
- 🔒 Key Vault storing VM passwords & secrets
- 🛡️ VM Backup using Recovery Services Vault
- 🔑 RBAC controlled Key Vault access

## 🏗️ Resources Created

| Resource                | Purpose                           |
|-------------------------|-----------------------------------|
| `stbelgiumprod`         | Secure blob/file storage          |
| `pe-storage-web-subnet` | Internal-only storage access      |
| `kv-belgium-secure`     | Stores secrets (VM passwords)     |
| `rsv-belgium-backup`    | Backup vault for VMs              |

## 📸 Screenshots

### Storage Overview with Private Endpoint Setup

![Storage](./screenshots/storage-created.png)


### Key Vault Secrets

![Secrets](./screenshots/keyvault-secrets.png)

### Recovery Vault

![Vault](./screenshots/recovery-vault-created.png)
