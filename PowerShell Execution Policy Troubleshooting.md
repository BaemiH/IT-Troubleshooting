\# PowerShell Execution Policy Troubleshooting

\#\# Overview

This document describes resolving PowerShell execution policy restrictions that prevented scripts from running during software installation and development environment setup.

\---

\#\# Environment

\- Windows 11  
\- PowerShell  
\- Node.js  
\- npm  
\- Git  
\- Laravel Development Environment

\---

\#\# Problem

PowerShell blocked execution of local scripts.

Example:

\`\`\`  
npm.ps1 cannot be loaded because running scripts is disabled on this system.  
\`\`\`

\---

\#\# Symptoms

Commands such as:

\`\`\`powershell  
npm install  
npm run dev  
\`\`\`

Failed immediately.

PowerShell displayed execution policy errors before running any script.

\---

\#\# Root Cause

PowerShell execution policy was configured to restrict unsigned scripts.

This is a default Windows security feature.

\---

\#\# Resolution

\#\#\# Step 1

View current execution policy.

\`\`\`powershell  
Get-ExecutionPolicy  
\`\`\`

\---

\#\#\# Step 2

Temporarily allow locally created scripts.

\`\`\`powershell  
Set-ExecutionPolicy RemoteSigned \-Scope CurrentUser  
\`\`\`

\---

\#\#\# Step 3

Accept confirmation prompt.

\---

\#\#\# Step 4

Restart PowerShell.

\---

\#\#\# Step 5

Retry command.

\`\`\`powershell  
npm install  
\`\`\`

or

\`\`\`powershell  
npm run dev  
\`\`\`

\---

\#\# Verification

Commands completed successfully.

No additional execution policy errors occurred.

The development environment functioned normally.

\---

\#\# Lessons Learned

Execution Policy is designed to protect Windows from malicious scripts.

Changing only the CurrentUser scope minimizes security impact while allowing legitimate development work.

\---

\#\# Skills Demonstrated

\- Windows administration  
\- PowerShell  
\- Windows security  
\- Development environment configuration  
\- Command-line troubleshooting  
