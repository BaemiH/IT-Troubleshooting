\# Valorant Uninstallation Troubleshooting

\#\# Overview

This document outlines the troubleshooting process used to remove Riot Games' Valorant after standard Windows uninstallation methods failed.

\---

\#\# Environment

\- Windows 11  
\- Riot Client  
\- Riot Vanguard  
\- Windows Settings  
\- Services  
\- PowerShell

\---

\#\# Problem

Valorant could not be removed through Windows Settings.

Windows reported:

\`\`\`  
The product is currently running.  
\`\`\`

Even though the game was closed.

\---

\#\# Symptoms

\- Uninstall button failed  
\- Riot Client appeared closed  
\- Vanguard was removed successfully  
\- Windows continued reporting the application as running

\---

\#\# Root Cause

Background services and installer information prevented Windows Installer from completing the removal process.

The uninstall process required verification that Riot services were fully removed before attempting additional troubleshooting.

\---

\#\# Resolution

\#\#\# Step 1

Close all Riot applications.

Verify within Task Manager.

\---

\#\#\# Step 2

Uninstall Riot Vanguard.

Restart Windows.

\---

\#\#\# Step 3

Verify Riot services.

\`\`\`powershell  
sc query RiotClientServices  
\`\`\`

\---

\#\#\# Step 4

If services remain:

Stop service.

Disable service.

Restart Windows.

\---

\#\#\# Step 5

Attempt to uninstall again.

Settings

↓

Apps

↓

Installed Apps

↓

Valorant

↓

Uninstall

\---

\#\#\# Step 6

If the uninstall continues to fail:

Use Microsoft's Program Install and Uninstall Troubleshooter to remove damaged installer information.

\---

\#\# Verification

Confirm:

\- Valorant removed  
\- Riot Client removed  
\- Vanguard removed  
\- No Riot services remain  
\- Installation directories deleted

\---

\#\# Lessons Learned

Applications that install kernel-level services may require additional cleanup beyond normal Windows uninstall procedures.

Checking services before reinstalling or manually deleting files helps prevent incomplete removals.

\---

\#\# Skills Demonstrated

\- Windows troubleshooting  
\- Software installation/removal  
\- Service management  
\- PowerShell  
\- Windows Installer  
\- Root cause analysis  
