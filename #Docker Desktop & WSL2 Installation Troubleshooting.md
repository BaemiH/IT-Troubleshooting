\# Docker Desktop & WSL2 Installation Troubleshooting

\#\# Overview

This document outlines the troubleshooting process used to install and configure Docker Desktop on Windows after encountering virtualization and Windows Subsystem for Linux (WSL2) issues.

\---

\#\# Environment

\- Operating System: Windows 11  
\- Docker Desktop  
\- WSL2  
\- Ubuntu  
\- PowerShell  
\- Hyper-V  
\- Virtual Machine Platform

\---

\#\# Problem

Docker Desktop would not start after installation.

Error messages included:

\- WSL2 installation failed  
\- Virtualization not enabled  
\- Docker Desktop failed to initialize

\---

\#\# Symptoms

\- Docker Desktop is continuously loading  
\- Unable to start Linux containers  
\- Ubuntu distribution would not install correctly  
\- WSL command returned virtualization errors

Example error:

\`\`\`

WSL2 is unable to start since virtualization is not enabled on this machine.

\`\`\`

\---

\#\# Root Cause

The computer was missing one or more required virtualization components.

Primary causes included:

\- Hardware virtualization disabled in BIOS  
\- Virtual Machine Platform not enabled  
\- Hyper-V components unavailable  
\- WSL2 not properly configured

\---

\#\# Resolution

\#\#\# Step 1

Verify Windows Features.

Enable:

\- Windows Subsystem for Linux  
\- Virtual Machine Platform  
\- Hyper-V (if available)

Restart the computer.

\---

\#\#\# Step 2

Verify virtualization is enabled.

Open Task Manager.

Performance → CPU

Confirm:

\`\`\`

Virtualization: Enabled

\`\`\`

If disabled:

\- Restart computer  
\- Enter BIOS  
\- Enable Intel VT-x / AMD-V

\---

\#\#\# Step 3

Install WSL

Run:

\`\`\`powershell  
wsl \--install  
\`\`\`

Restart Windows.

\---

\#\#\# Step 4

Install Ubuntu

\`\`\`powershell  
wsl \--install \-d Ubuntu  
\`\`\`

Create a Linux username and password.

\---

\#\#\# Step 5

Verify WSL

\`\`\`powershell  
wsl \--status  
\`\`\`

Expected:

\`\`\`

Default Version: 2

\`\`\`

\---

\#\#\# Step 6

Restart Docker Desktop

Docker should now detect the WSL installation automatically.

\---

\#\# Verification

Confirm:

\- Docker Desktop opens successfully  
\- Ubuntu launches correctly  
\- Command executes successfully:

\`\`\`powershell  
docker run hello-world  
\`\`\`

Expected output:

\`\`\`

Hello from Docker\!

\`\`\`

\---

\#\# Lessons Learned

Docker Desktop depends heavily on Windows virtualization.

Before troubleshooting Docker itself, verify:

\- BIOS virtualization  
\- WSL2  
\- Windows Features  
\- Hyper-V configuration

Checking these prerequisites first significantly reduces troubleshooting time.

\---

\#\# Skills Demonstrated

\- Windows administration  
\- Docker installation  
\- WSL2 configuration  
\- Virtualization troubleshooting  
\- Command-line troubleshooting  
\- Root cause analysis  
