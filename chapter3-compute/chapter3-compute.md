# Chapter 3 – Deploy VMs, Load Balancer & VM Scale Sets

## Overview
This chapter sets up compute resources for the Web and App tiers, with an internal Load Balancer, autoscaling VMSS, and Bastion access for secure debugging.

## Resources Created

| Resource Type       | Name              | Notes                     |
|---------------------|-------------------|---------------------------|
| VM                  | web-vm1 / web-vm2 | NGINX preinstalled        |
| Load Balancer       | lb-web-tier       | Internal only, port 80    |
| VMSS                | vmss-app-tier     | Apache + autoscaling      |
| Health Probe        | http-probe        | Checks port 80            |

## Load Balancer Setup

- Internal-only for private traffic
- Health probes use port 80
- Backend pool targets `web-vm1`, `web-vm2`

## Autoscaling Rules (VMSS)

- Scale out at 75% CPU
- Scale in below 25% CPU
- Starts with 2 instances

## Custom Script Extension

```bash
sudo apt update && sudo apt install -y nginx
echo "Web VM 1" > /var/www/html/index.html
