<img width="900" src="https://github.com/user-attachments/assets/b3baff31-9e90-4cde-95ab-7968aeb06134" />

# DISA STIGs (Defense Information Systems Agency Security Technical Implementation Guides)

**Windows 11 STIG Remediation Scripts:**
- [WN11-AC-000040](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-AC-000040.ps1)
- [WN11-AU-000510](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-AU-000510.ps1)
- [WN11-CC-000005](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000005.ps1)
- [WN11-CC-000110](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000110.ps1)
- [WN11-CC-000310](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000310.ps1)
- [WN11-CC-000350](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000350.ps1)
- [WN11-CC-000370](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000370.ps1)
- [WN11-EP-000310](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-EP-000310.ps1)
- [WN11-SO-000070](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-SO-000070.ps1)
- [WN11-SO-000255](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-SO-000255.ps1)

## Purpose
To harden a Windows 11 system by identifying and remediating security misconfigurations in accordance with DISA STIG cybersecurity compliance requirements.

## Platforms and Languages Leveraged
- Windows 11 Virtual Machines (Microsoft Azure)
- Tenable
- PowerShell 


## Workflow

1. Create a Windows 11 virtual machine
2. Disable the Windows Firewall
3. In Tenable, create a new **Advanced Network Scan**
   - Select the appropriate scanner
   - Set the target as the virtual machine's private IP address
   - Add the virtual machine's Windows credentials
   - Add Compliance Checks for **DISA Microsoft Windows 11 STIG v2r7**
   - Disable all plugins except **Policy Compliance**
   - Within Policy Compliance, enable only **Windows Compliance Checks**
   - Save the scan

4. Launch the Tenable scan
5. Once the scan completes, navigate to the **Audits** tab
6. Select any failed STIG 
7. Research the failed STIG and find out how to remediate it
   - [Windows 11 STIG List (Guide)](https://stigaview.com/products/win11/latest/)

8. Create a PowerShell script to automate the STIG remediation
9. Execute the PowerShell remediation script
10. If the script executes successfully, restart the virtual machine
11. Wait for the virtual machine to come back online
12. Re-launch the Tenable scan
13. After the scan completes, verify that the previously failed STIG now shows as **Passed**
14. Repeat steps 6 through 13 to remediate more failed STIGs

---

# Example Remediation

## STIG ID: WN11-CC-000005
Camera access from the lock screen must be disabled.

<br>

### 🔴 BEFORE REMEDIATION — Tenable Scan Results

<img width="1495" height="397" alt="failed2" src="https://github.com/user-attachments/assets/8d517ba1-a526-47d1-8b6d-fe501f4afea2" />

<br>

### PowerShell Remediation Script Used
[WN11-CC-000005](https://github.com/MattStefano/Project-Files/blob/main/STIGS/WN11-CC-000005.ps1)

<br>

### 🟢 AFTER REMEDIATION — Tenable Scan Results

<img width="1499" height="399" alt="pass2" src="https://github.com/user-attachments/assets/e2356d93-51f6-4872-878d-b6b05fe320a5" />

<br>
<br>

| Status Before | Status After |
|---|---|
| Failed | Passed |
