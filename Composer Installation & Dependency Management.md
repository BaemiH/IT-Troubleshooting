\# Composer Installation & Dependency Management

\#\# Overview

This document outlines the installation and troubleshooting process for Composer, the dependency manager used by PHP applications. During setup, several issues were encountered related to PHP extensions, archive extraction, and dependency installation.

\---

\#\# Environment

\- Windows 11  
\- PHP  
\- Composer  
\- Laravel  
\- PowerShell  
\- Command Prompt

\---

\#\# Problem

Composer was unable to install project dependencies successfully.

Errors included:

\- Missing PHP extensions  
\- Unable to extract archives  
\- Dependency installation failures

\---

\#\# Symptoms

Examples included:

\- Composer install terminated unexpectedly  
\- Missing extension warnings  
\- Package extraction failures  
\- Laravel project setup could not be completed

\---

\#\# Root Cause

The PHP installation was incomplete, and the required extensions were disabled.

Additionally:

\- Archive extraction utilities were unavailable  
\- PHP executable location requires verification  
\- Composer depended on extensions that were not enabled

\---

\#\# Resolution

\#\#\# Step 1

Verify PHP installation.

\`\`\`powershell  
php \-v  
\`\`\`

\---

\#\#\# Step 2

Verify Composer installation.

\`\`\`powershell  
composer \--version  
\`\`\`

\---

\#\#\# Step 3

Locate php.ini.

Confirm the correct configuration file is being loaded.

\`\`\`powershell  
php \--ini  
\`\`\`

\---

\#\#\# Step 4

Enable required PHP extensions.

Examples:

\`\`\`  
extension=fileinfo  
extension=zip  
\`\`\`

\---

\#\#\# Step 5

Restart the terminal.

\---

\#\#\# Step 6

Retry installation.

\`\`\`powershell  
composer install  
\`\`\`

\---

\#\# Verification

Successful dependency installation.

Laravel project generated the vendor directory correctly.

Composer completed without errors.

\---

\#\# Lessons Learned

Composer depends heavily on a properly configured PHP environment.

Verifying PHP extensions before troubleshooting Composer significantly reduces setup time.

\---

\#\# Skills Demonstrated

\- Composer  
\- PHP  
\- Laravel  
\- Dependency management  
\- Windows configuration  
\- Command-line troubleshooting  
