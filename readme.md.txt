# Azure Help Desk Simulation Lab

## Overview
This project simulates real-world IT support scenarios in **Azure** and **Microsoft 365**, demonstrating troubleshooting steps and resolutions.  
The lab covers common issues such as VM connection failures, storage access permissions, and Microsoft Teams licensing problems.  

## Tools Used
- Azure Portal
- Azure Resource Manager (ARM)
- Network Security Groups (NSG)
- Azure Storage Accounts
- Microsoft 365 Admin Center
- PowerShell (for RDP connectivity test)

## Scenarios Simulated

### 0. Setup Azure Environment
- Create **2 Virtual Machines (Windows/Linux)**.  
- Create **1 Storage Account**.  

**Screenshots:**  
- Azure VMs created  
  ![VMs Created](screenshots/1vms-created.png)  
- Storage Account created  
  ![Storage Account](screenshots/2storage-created.png)  

---

### 1. RDP/SSH Connection Fails
- Blocked RDP (3389) or SSH (22) in **NSG inbound rules**.
- Verified failure using RDP client / SSH and PowerShell command.
- Fixed by adding inbound rule to allow RDP/SSH.

**Screenshots:**  
- Connection failure  
  ![RDP/SSH Connection Failure](screenshots/3rdp-fail.png)  
- NSG rule update  
  ![NSG Rule Updated](screenshots/4nsg-update.png)  
  ![NSG Rule Updated](screenshots/4.1nsg-update.png)  
- Successful login  
  ![RDP/SSH Successful Login](screenshots/5rdp-success.png)  

---

### 2. Storage Account Access Denied
- Created a test user with no assigned Azure role.
- User attempted to access Blob storage → received **access denied**.
- Fixed by assigning **Storage Blob Data Contributor** role.

**Screenshots:**  
- Created new User
  ![create new user](screenshots/created_new_user.png) 
- Access denied error  
  ![Storage Access Denied](screenshots/6storage-denied.png)  
- IAM role assignment  
  ![IAM Role Assigned](screenshots/7storage-role.png)  
  ![IAM Role Assigned](screenshots/7.1added_user.png)  
- Successful file upload/download  
  ![Storage Access Success](screenshots/8storage-success.png)  

---

### 3. Microsoft Teams Not Working
- Created a test user in Microsoft 365 with **no license assigned**.
- Tried logging in → received **license error**.
- Fixed by assigning **Microsoft 365 E3 license** in Admin Center.

**Screenshots:**  
- Created Test User
  ![create new user](screenshots/created_test_user.png) 
- Teams login failure  
  ![Teams Login Failure](screenshots/9teams-fail.png)  
- Admin license assignment  
  ![Teams License Assigned](screenshots/10.1teams-license.png) 
  ![Teams License Assigned](screenshots/10teams-license.png)  
- Teams working after fix  
  ![Teams Login Success](screenshots/11teams-success.png)  

---

## Lessons Learned
- Importance of NSG inbound rules for connectivity.
- Role-Based Access Control (RBAC) is crucial for resource access.
- Microsoft 365 licenses directly affect app availability.
- Real-world troubleshooting requires both **diagnostics** and **permissions management**.

## Author
**Clane Cyril Rumao**  
Master’s in Computer Science | Cloud & IT Support Enthusiast  
