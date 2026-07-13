\# Git Installation & PATH Configuration

\#\# Overview

This document describes troubleshooting performed after Git commands were unavailable in Windows despite Git being installed.

\---

\#\# Environment

\- Windows 11  
\- Git for Windows  
\- GitHub Desktop  
\- PowerShell  
\- Command Prompt

\---

\#\# Problem

Git commands failed from both PowerShell and Command Prompt.

Example:

\`\`\`

git is not recognized as an internal or external command

\`\`\`

\---

\#\# Symptoms

Running:

\`\`\`powershell  
git \--version  
\`\`\`

returned:

\`\`\`

'git' is not recognized...

\`\`\`

GitHub Desktop functioned normally while command-line Git remained unavailable.

\---

\#\# Root Cause

Git executable was not included in the Windows PATH environment variable.

Windows could not locate:

\`\`\`

git.exe

\`\`\`

\---

\#\# Resolution

\#\#\# Step 1

Locate the Git installation.

Typical location:

\`\`\`

C:\\Program Files\\Git\\cmd

\`\`\`

\---

\#\#\# Step 2

Open:

System Properties

↓

Advanced

↓

Environment Variables

\---

\#\#\# Step 3

Edit the PATH variable.

Add:

\`\`\`

C:\\Program Files\\Git\\cmd

\`\`\`

\---

\#\#\# Step 4

Restart:

\- PowerShell  
\- Command Prompt  
\- IDE

\---

\#\#\# Step 5

Verify installation.

Run:

\`\`\`powershell  
git \--version  
\`\`\`

Expected:

\`\`\`

git version 2.xx.x.windows.x

\`\`\`

\---

\#\# Verification

Additional commands:

\`\`\`powershell  
git config \--global user.name

git config \--global user.email

git status  
\`\`\`

All commands executed successfully.

\---

\#\# Lessons Learned

Many Windows applications install correctly but do not become available in the command line until PATH is configured.

Whenever a command is "not recognized":

\- Verify installation  
\- Locate executable  
\- Check PATH  
\- Restart terminal

\---

\#\# Skills Demonstrated

\- Windows environment variables  
\- Command-line troubleshooting  
\- Git installation  
\- Software configuration  
\- Windows administration  
