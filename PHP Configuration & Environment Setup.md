\# PHP Configuration & Environment Setup

\#\# Overview

This document describes the process of configuring PHP for local web development and ensuring compatibility with Laravel and Composer.

\---

\#\# Environment

\- Windows 11  
\- PHP  
\- Laravel  
\- Composer  
\- PowerShell

\---

\#\# Problem

PHP was installed, but development tools were unable to locate or properly utilize the installation.

\---

\#\# Symptoms

Examples included:

\- PHP command unavailable  
\- Composer dependency errors  
\- Laravel setup failures  
\- Incorrect php.ini configuration

\---

\#\# Root Cause

PHP required additional configuration after installation.

Issues included:

\- PATH variable missing PHP directory  
\- php.ini configuration incomplete  
\- Required extensions disabled

\---

\#\# Resolution

\#\#\# Step 1

Verify installation.

\`\`\`powershell  
php \-v  
\`\`\`

\---

\#\#\# Step 2

Locate the PHP installation directory.

Example:

\`\`\`  
C:\\Users\\\<Username\>\\php  
\`\`\`

\---

\#\#\# Step 3

Add the PHP directory to the Windows PATH.

System Properties

↓

Environment Variables

↓

PATH

↓

Add the PHP directory

\---

\#\#\# Step 4

Locate php.ini.

\`\`\`powershell  
php \--ini  
\`\`\`

\---

\#\#\# Step 5

Enable required extensions.

Examples:

\`\`\`  
fileinfo  
zip  
openssl  
pdo\_mysql  
mbstring  
\`\`\`

\---

\#\#\# Step 6

Restart the terminal.

\---

\#\# Verification

Commands executed successfully.

\`\`\`powershell  
php \-v

php \--ini

composer install  
\`\`\`

Laravel recognized the PHP installation correctly.

\---

\#\# Lessons Learned

A successful PHP installation requires more than copying executable files.

Proper PATH configuration and extension management are essential for modern PHP development.

\---

\#\# Skills Demonstrated

\- PHP  
\- Windows administration  
\- Environment variables  
\- Laravel  
\- Composer  
\- Configuration management  
