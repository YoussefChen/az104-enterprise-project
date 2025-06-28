# 📘 Chapter 6 – Application Gateway: Layer 7 Load Balancing with Web Application Firewall

## ✅ Chapter Summary

In this chapter, we deploy an **Azure Application Gateway** in front of our web server virtual machines (`web-vm1` and `web-vm2`) to handle:

- Layer 7 (HTTP) traffic management
- Smart routing using a listener and backend pool
- Public access via a single static IP
- Secure internal routing to private VM IPs
- Scalable frontend access point for the web tier

Instead of chaining through the Load Balancer, we configure the Application Gateway to directly communicate with the **private IPs of the VMs**, following Azure best practices.
Note: Although Azure Load Balancer was configured earlier, it's currently not in the request path because the Application Gateway routes traffic directly to the web VMs. It is retained for internal scaling scenarios in later chapters or as an architectural learning point.


---

## 🧱 Architecture Update

Internet 🌍
   │
   ▼
┌───────────────────────────────┐
│     Azure Application Gateway │
│   - Public IP: pip-appgateway │
│   - Listener: HTTP/80         │
└────────────┬──────────────────┘
             │
             ▼
    ┌────────────────────┐
    │ Backend Pool       │
    │ - web-vm1 (private)│
    │ - web-vm2 (private)│
    └────────────────────┘

---

## 🛠️ Deployment Steps

### Step 1: Create a Static Public IP
**Service**: `Public IP Address`  
**Name**: `pip-appgateway`  
**SKU**: Standard  
**Assignment**: Static  
**Resource Group**: `rg-belgium-hub`

📸 Screenshot: `appgateway-public-ip.png`

---

### Step 2: Create the Application Gateway
**Service**: `Application Gateway`  
**Name**: `agw-belgium-frontend`  
**Tier**: Standard V2 (or WAF V2 for extra security)  
**Frontend IP**: Use `pip-appgateway` (created above)  
**Autoscaling**: Enabled (Min 2, Max 10)

📸 Screenshot: `appgateway-create-overview.png`

---

### Step 3: Configure Backend Pool
**Backend Pool Name**: `pool-web-vms`  
**Target Type**: Virtual Machines  
**Select VMs**: `web-vm1`, `web-vm2`  
**NIC/Private IP**: Use the defaults

📸 Screenshot: `appgateway-backend-pool.png`

---

### Step 4: Configure HTTP Settings
**HTTP Setting Name**: `http-settings`  
**Protocol**: HTTP  
**Port**: 80  
**Timeout**: 20s (default)

📸 Screenshot: `appgateway-http-settings.png`

---

### Step 5: Add Routing Rule
**Rule Name**: `rule-http-to-vms`  
**Listener Name**: `listener-http`  
**Frontend IP**: `pip-appgateway`  
**Protocol**: HTTP  
**Port**: 80  
**Listener Type**: Basic  
**Backend Target**: `pool-web-vms`  
**Backend Setting**: `http-settings`

📸 Screenshot: `appgateway-routing-rule.png`

---

### Step 6: Test Access
Visit:

You should see the HTML content from either `web-vm1` or `web-vm2`.

📸 Screenshot: `appgateway-browser-test.png`

---

## 🧠 Key Learnings

- Azure Application Gateway is a Layer 7 (HTTP/HTTPS) load balancer with intelligent routing capabilities.
- App Gateway can’t use public IPs (like Load Balancer IPs) as backend targets — it must use private resources.
- Routing directly to the VMs ' private IPs is secure, fast, and recommended by Microsoft.
- You now have a clean frontend entry point for future scaling, WAF integration, and SSL termination.

---

## 📁 Screenshot Summary (for GitHub)

| Filename                        | Description                                     |
|---------------------------------|-------------------------------------------------|
| `appgateway-public-ip.png`      | Public IP creation for the Application Gateway  |
| `appgateway-create-overview.png`| Final review of the gateway deployment          |
| `appgateway-backend-pool.png`   | Backend pool with `web-vm1` and `web-vm2`       |
| `appgateway-http-settings.png`  | HTTP settings: port 80                          |
| `appgateway-routing-rule.png`   | Full routing rule configuration                 |
| `appgateway-browser-test.png`   | Browser access test using App Gateway IP        |
