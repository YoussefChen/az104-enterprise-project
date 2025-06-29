# Chapter 8: Monitoring & Alerts Setup

## Overview

This chapter implements monitoring and alerting for our Azure infrastructure using Azure Monitor and Log Analytics. We configure diagnostic settings to send logs and metrics from VMSS, Application Gateway, and NSG to a centralized Log Analytics Workspace. We then create queries to analyze performance and health and set alerts to notify us of critical issues. Finally, we build a dashboard for real-time visibility.

## Steps Summary

- Created Log Analytics Workspace `law-az104-project` in West Europe.
- Enabled diagnostics on VMSS, Application Gateway, and NSG, sending data to the workspace.
- Built queries to track VMSS CPU, Application Gateway backend health, and NSG denied flows.
- Configured alert rules for high CPU, unhealthy backends, and network denials.
- Created a consolidated Azure Dashboard with metrics and logs.

## Screenshots

| Screenshot Name               | Description                                |
|-------------------------------|--------------------------------------------|
| chapter8-law-create.png       | Log Analytics workspace creation           |
| chapter8-diagnostics-vmss.png | Diagnostics setup on VMSS                  |
| chapter8-diagnostics-appgw.png| Diagnostics setup on Application Gateway   |
| chapter8-diagnostics-nsg.png  | Diagnostics setup on Network Security Group|
| chapter8-log-queries.png      | Custom queries in Log Analytics            |
| chapter8-alert-rule.png       | Alert rule creation page                   |
| chapter8-dashboard.png        | Azure Dashboard with monitoring widgets    |

## Notes

- Centralized log collection allows deep analysis of system health.
- Alerts automate issue detection and notification.
- Dashboards provide visual monitoring aiding quick troubleshooting.
