# Chapter 7: VMSS Setup with Custom Script Extension and Networking Fixes

## Overview

In this chapter, we enhanced our Virtual Machine Scale Set (VMSS) by deploying a custom script extension to install and configure NGINX on each instance. We also ensured the VMSS is correctly placed in the `app-subnet` for proper networking and Application Gateway integration.

## Steps

1. Verified and corrected the VMSS subnet to `app-subnet`.
2. Created a custom Bash script to install NGINX and serve a simple HTML page.
3. Uploaded the script to GitHub and applied it as a Custom Script Extension.
4. Linked the VMSS backend pool with the Application Gateway and configured HTTP settings.
5. Verified NGINX service is running on all instances and accessible via the Application Gateway.
6. Confirmed networking security group (NSG) rules allow proper traffic flow.

## Screenshots

| Screenshot Name                     | Description                                     |
|-------------------------------------|-------------------------------------------------|
| chapter7-vmss-instance-status.png   | VMSS instances showing running status           |
| chapter7-extension-success.png      | Custom Script Extension installed successfully  |
| chapter7-nginx-curl-test.png        | Curl command output from VMSS instance          |
| chapter7-appgw-backend-pools.png    | Application Gateway backend pool with VMSS      |
| chapter7-browser-nginx-page.png     | NGINX welcome page visible in browser           |
| chapter7-app-nsg-rules.png          | NSG rules for app-subnet allowing HTTP & SSH    |

## Notes

- This setup ensures scalable web tier instances managed by VMSS.
- Proper subnet placement and NSG configuration are crucial for traffic flow.
- Using a Custom Script Extension automates software deployment across all VMSS instances.

