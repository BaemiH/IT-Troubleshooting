\# Hyper-V & Virtualization Troubleshooting

\#\# Overview

This document outlines the troubleshooting process used to diagnose and resolve hardware virtualization issues preventing virtualization-based applications, including WSL2 and Docker Desktop, from functioning properly.

\---

\#\# Environment

\- Windows 11  
\- Intel Processor  
\- BIOS/UEFI Firmware  
\- Hyper-V  
\- Windows Subsystem for Linux (WSL2)  
\- Docker Desktop

\---

\#\# Problem

Virtualization-dependent applications failed to start due to hardware virtualization being disabled.

Error messages included:

\- HCS\_E\_HYPERV\_NOT\_INSTALLED  
\- Virtualization is not enabled  
\- WSL2 could not initialize

\---

\#\# Symptoms

\- Docker Desktop stuck on startup  
\- Ubuntu would not install through WSL  
\- WSL returned Hyper-V-related errors  
\- Virtual machines failed to initialize

\---

\#\# Root Cause

Hardware virtualization (Intel VT-x / AMD-V) was disabled within the computer's BIOS/UEFI firmware.

Additionally, required Windows virtualization features were not fully enabled.

\---

\#\# Resolution

\#\#\# Step 1

Verify virtualization status.

Open:

Task Manager

↓

Performance

↓

CPU

Check:

\`\`\`  
Virtualization: Enabled  
\`\`\`

\---

\#\#\# Step 2

If disabled:

Restart the computer.

Enter BIOS/UEFI.

Locate:

\- Intel Virtualization Technology (VT-x)  
or  
\- AMD SVM Mode

Enable the setting.

Save and exit.

\---

\#\#\# Step 3

Enable the required Windows Features.

Enable:

\- Hyper-V  
\- Virtual Machine Platform  
\- Windows Hypervisor Platform  
\- Windows Subsystem for Linux

Restart Windows.

\---

\#\#\# Step 4

Verify Hyper-V.

Run:

\`\`\`powershell  
systeminfo  
\`\`\`

Verify Hyper-V Requirements report "Yes".

\---

\#\#\# Step 5

Verify WSL.

\`\`\`powershell  
wsl \--status  
\`\`\`

Confirm Version 2 is active.

\---

\#\# Verification

Successfully launched:

\- Docker Desktop  
\- Ubuntu (WSL2)

Confirmed virtualization remained enabled after reboot.

\---

\#\# Lessons Learned

Many virtualization issues originate from BIOS configuration rather than Windows itself.

Verifying hardware virtualization early prevents unnecessary software troubleshooting.

\---

\#\# Skills Demonstrated

\- BIOS configuration  
\- Windows administration  
\- Hyper-V  
\- WSL2  
\- Virtualization troubleshooting  
\- Root cause analysis  
