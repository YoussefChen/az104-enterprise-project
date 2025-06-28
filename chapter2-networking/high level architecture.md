Virtual Network: vnet-belgium-hub

┌──────────────────────────────────────────────────────┐
│                                                      │
│              Virtual Network (vnet-belgium-hub)      │
│                                                      │
│  ┌─────────────┐ ┌─────────────┐ ┌──────────────┐    │
│  │ Web Subnet  │ │ App Subnet  │ │ DB Subnet    │    │
│  │ (web-subnet)│ │ (app-subnet)│ │ (db-subnet)  │    │
│  └────┬────────┘ └────┬────────┘ └────┬─────────┘    │
│       │               │               │              │
│   NSG: Allow HTTP/SSH │  NSG: Allow   │ NSG: Allow   │
│   ASG: Frontend Devs  │  Backend VMs  │ Only App → DB│
│                                                      │
│       Azure Bastion (deployed in mgmt subnet)        │
│                                                      │
└──────────────────────────────────────────────────────┘

