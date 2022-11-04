---
layout: default
title: O365
grand_parent: Engineering Reference
parent: Destination Advanced Options
nav_order: 1
---

## O365 Destination Advanced Options
{: .no_toc }

---

This document will give an overview on all the Office 365 Destination Advanced Options in CloudM Migrate. 

---
<a name="top"></a>
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---
## SharePoint Online

1. [SharePoint Migration API](#sharepointapi)
2. [Retry Backoff](#sretryback)
3. [SharePoint Admin Url](#shareadurl)
4. [Timeout](#stimeout)
5. [Preserve File Created and Modified Dates](#persfilemoddate)
6. [Provision Sites](#provsites)
7. [Hybrid Environment](#hybridenv)
8. [SharePoint Storage](#sharstor)
9. [Retry Count](#sretry)
10. [Retry Count](#sfretry)
11. [Truncate Folders and Files](#trunfoldfil)
12. [Orphaned Items Folder](#orphfold)
13. [Provision Sites Timeout Check](#provsitetime)
14. [Patch Permissions](#patchperm)

### SharePoint Migration API <a name="docsharperm"></a>
{: .no_toc }
Default Value: On

SharePoint Migration API is recommended for all migrations to SharePoint Online and OneDrive for Business. For more information see the article here

https://support.cloudm.io/hc/en-us/articles/360021044840

Change Conditions: ??

### Retry Backoff (seconds) <a name="sretryback"></a>
{: .no_toc }
Default Value: 3

SharePoint Migration API Retry Backoff in seconds.

Change Conditions: ??

### SharePoint Admin Url <a name="shareadurl"></a>
{: .no_toc }
Default Value: None

The Url for the SharePoint admin center e.g. https://tenant-admin.sharepoint.com

Change Conditions: ??

### Timeout <a name="stimeout"></a>
{: .no_toc }
Default Value: 1800000

The timeout that will apply to communications with the SharePoint server.

Change Conditions: ??

### Preserve File Created and Modified Dates <a name="persfilemoddate"></a>
{: .no_toc }
Default Value: On

Preserve the Original File Created and Modified Dates.

Change Conditions: ??

### Provision Sites <a name="provsites"></a>
{: .no_toc }
Default Value: On

Provision any Sites that do not exist.

Change Conditions: ??

### Hybrid Environment <a name="hybridenv"></a>
{: .no_toc }
Default Value: On

Allows a custom 'SharePoint Admin Url' and 'SharePoint My Sites Url' to be entered for hybrid migration.

Change Conditions: ??

### SharePoint Storage <a name="sharstor"></a>
{: .no_toc }
Default Value: Office 365

Choose whether the document should be shared as per the source file ACLs if they can be resolved to email addresses (see documentation).

Change Conditions: ??

### Retry Count <a name="sretry"></a>
{: .no_toc }
Default Value: 20

SharePoint Migration API Retry Count

Change Conditions: ??

### Retry Count <a name="sfretry"></a>
{: .no_toc }
Default Value: 10

The number of times an operation will be attempted before failing.

Change Conditions: ??

### Truncate Folders and Files <a name="trunfoldfil"></a>
{: .no_toc }
Default Value: On

Attempt to truncate folders and files to fall within the 400 characters limit.

Change Conditions: ??

### Orphaned Items Folder <a name="orphfold"></a>
{: .no_toc }
Default Value: None

Optionally place all failed truncated folders in the specified 'Orphan Items Folder'. Leave empty to fail migration if folders can not be truncated.

Change Conditions: This option much be set to a foldername in order to relocate files with paths longer then 400 characters. If not set, this will be an error item during the migration. 

### Provision Sites Timeout Check <a name="provsitetime"></a>
{: .no_toc }
Default Value: 180000

The maximum period of time used to check if a OneDrive site has been provisioned.

Change Conditions: ??

### Patch Permissions <a name="patchperm"></a>
{: .no_toc }
Default Value: None

Add/Update/Delete permissions for existing items. If disabled, only new permissions will be applied to existing items (see documentation).

Change Conditions: ??

---
## Email
[Back to Top](#top)

1. [Max Message Size](#maxmess)
2. [Use Chunked HTTP Web Requests](#usehttpweb)
3. [Strip Received Headers](#striprechead)
4. [Recoverable Items Destination](#recovitemdes)

### Max Message Size <a name="maxmess"></a>
{: .no_toc }
Default Value: 52428800

The maximum message size (in bytes) that will be migrated.

Change Conditions: ??

### Use Chunked HTTP Web Requests <a name="usehttpweb"></a>
{: .no_toc }
Default Value: Off

When creating Mail items in Exchange, use HTTP web request chunking to increase performance. WARNING: some hosted Exchange environments do not support this method of communication.

Change Conditions: ??

### Strip Received Headers <a name="striprechead"></a>
{: .no_toc }
Default Value: Off

Strip any 'Received' headers and add a single 'Received' header with a value the same as the 'Date' header.

Change Conditions: ??

### Recoverable Items Destination <a name="recovitemdes"></a>
{: .no_toc }
Default Value: Recoverable Items

When migrating items from the recoverable items folders, choose whether to place them in Recoverable Items or in the Mailbox.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Exchange 2007 Calendar Timezone](#exc2007cal)
2. [Exchange 2010/Office 365 Calendar Timezone](#exc2010cal)

### Exchange 2007 Calendar Timezone <a name="exc2007cal"></a>
{: .no_toc }
Default Value: Gmt

The default timezone to use with appointments when migrating to Exchange 2007 when the timezone is not identified by other means.

Change Conditions: ??

### Exchange 2010/Office 365 Calendar Timezone <a name="exc2010cal"></a>
{: .no_toc }
Default Value: GMT Stadard Time

The default timezone to use with appointments when migrating to Exchange 2010/Office 365 when the timezone is not identified by other means.

Change Conditions: ??

---
## Calendar Appointments
[Back to Top](#top)

1. [Appointment Body Type](#appbodtyp)

### Appointment Body Type <a name="appbodtyp"></a>
{: .no_toc }
Default Value: Undefined

Identifies how the appointment body content is formatted. If left undefined it will be assigned based on appointment HtmlContent or TextContent properties. If set to 'Best' the body will be formatted based on the richest available content.

Change Conditions: ??

---
## Microsoft Teams/Group 
[Back to Top](#top)

1. [Timeout](#ttimeout)
2. [Maximum Results Per Request](#maxresreq)
3. [Provision Office 365 Group Timeout Check](#prov365time)
4. [Default Document Library Name](#defdoclib)
5. [Teams Direct Migration](#teamdirmig)
6. [Migrate Team Channel Tabs](#migteamtab)
7. [Retry Count](#tretryc)
8. [Create Office 365 Group](#crea365grou)
9. [Test Office 365 Group Email](#test365gemail)
10. [Chat Message Library Name](#chatmeslib)
11. [Finalize Teams Direct Migration](#finteamdir)
12. [Rehydrate Teams Private Chat](#rehydpichat)

### Timeout <a name="ttimeout"></a>
{: .no_toc }
Default Value: 1800000

The timeout for operations with the server.

Change Conditions: ??

### Maximum Results Per Request <a name="maxresreq"></a>
{: .no_toc }
Default Value: 999

The maximum number of results to return for individual queries.

Change Conditions: ??

### Provision Office 365 Group Timeout Check <a name="prov365time"></a>
{: .no_toc }
Default Value: 600000

The maximum period of time used to check if an Office 365 Group has been created.

Change Conditions: ??

### Default Document Library Name <a name="defdoclib"></a>
{: .no_toc }
Default Value: Documents

The default timezone to use with appointments when migrating to Exchange 2007 when the timezone is not identified by other means.

Change Conditions: ??

### Teams Direct Migration <a name="teamdirmig"></a>
{: .no_toc }
Default Value: Off

If the Teams site does not exist in the destination, keep this off so the migration uses a Prestage Teams location. This is a faster migration and more user friendly. If the destination Team site already exists, turn this on to prevent an error from occuring.

Change Conditions: ??

### Migrate Team Channel Tabs <a name="migteamtab"></a>
{: .no_toc }
Default Value: Off

Migrate Team channel tabs such as: Web, Document (Word, Excel, PDF, Powerpoint). For more information, see article 'Team Channel Tabs'

Change Conditions: ??

### Retry Count <a name="tretryc"></a>
{: .no_toc }
Default Value: Gmt

The number of times an operation will be attempted before failing.

Change Conditions: ??

### Create Office 365 Group <a name="crea365grou"></a>
{: .no_toc }
Default Value: Gmt

Create Office 365 Group if it does not exist.

Change Conditions: ??

### Test Office 365 Group Email <a name="test365gemail"></a>
{: .no_toc }
Default Value: Gmt

The email address of an Office 365 Group that already exists.

Change Conditions: ??

### Chat Message Library Name <a name="chatmeslib"></a>
{: .no_toc }
Default Value: Gmt

When migrating 'Microsoft Teams' and 'Export Chat Message Type' is set to 'Document' or 'Email and Document', the channel conversation history document will be migrated to this library.

Change Conditions: ??

### Finalize Teams Direct Migration <a name="finteamdir"></a>
{: .no_toc }
Default Value: Gmt

Mark Teams Direct Migration as completed. Migrating Teams data with this option enabled will take Team out of the migration mode. This option opens the team and channel resources for general use by team members. No further migrations can be performed against finalized team.

Change Conditions: ??

### Rehydrate Teams Private Chats <a name="rehydpichat"></a>
{: .no_toc }
Default: On

??

Change Conditions: ??

---
## Public Folders
[Back to Top](#top)

1. [Nest Public Folders](#nestpubfol)
2. [Nested Public Folder Name](#nestpubfolna)

### Nest Public Folders <a name="nestpubfol"></a>
{: .no_toc }
Default Value: On

Nest Public Folders under a specific top-level Public Folder.

Change Conditions: ??

### Nested Public Folder Name <a name="nestpubfolna"></a>
{: .no_toc }
Default Value: Top Level Folder

The name of the top-level Public Folder under which other Public Folders will be nested if 'Nest Public Folders' is true.

Change Conditions: ??

---
## Authentication
[Back to Top](#top)

1. [Exchange Version](#exchvers)
2. [Use Workstation Credentials](#useworkcred)

### Exchange Version <a name="exchvers"></a>
{: .no_toc }
Default Value: Microsoft Exchange 2019

The version of the Exchange destination platform.

Change Conditions: ??

### Use Workstation Credentials <a name="useworkcred"></a>
{: .no_toc }
Default Value: Off

Use the credentials of the logged in user of the workstation to perform migrations rather than the provided username and password. The admin username and password is still required for auto-discovery.

Change Conditions: ??

---
## Transfer and Performance
[Back to Top](#top)

1. [Retry Count](#tpretry)
2. [Timeout](#tptimeout)
3. [Max Wait Time](#maxwaitt)
4. [Use X-AnchorMailbox Header](#uxauthhead)

### Retry Count <a name="tpretry"></a>
{: .no_toc }
Default Value: 10

The version of the Exchange destination platform.

Change Conditions: ??

### Timeout <a name="tptimeout"></a>
{: .no_toc }
Default Value: 1200000

The timeout that will apply to communications with the Exchange server.

Change Conditions: ??

### Max Wait Time <a name="maxwaitt"></a>
{: .no_toc }
Default Value: 120000

Specify the maximum time that a wait operation can wait between exponential backoff retry attempts.

Change Conditions: ??

### Use X-AnchorMailbox Header <a name="uxauthhead"></a>
{: .no_toc }
Default Value: On

When using application impersonation, use the X-AnchorMailbox header to improve performance.

Change Conditions: ??

---
## PowerShell
[Back to Top](#top)

1. [PowerShell Variables](#psvar)
2. [PowerShell Init Script](#psinits)
3. [PowerShell Before Script](#psbefore)
4. [PowerShell After Script](#psafter)
5. [PowerShell Finalize Script](#psfinal)
6. [Run PowerShell Init Script](#runpsinit)
7. [Run PowerShell Before Script](#runpsbefore)
8. [Run PowerShell After Script](#runpsafter)
9. [Run PowerShell Finalize Script](#runpsfin)

### PowerShell Variables <a name="psvar"></a>
{: .no_toc }
Default Value: [!ps-url]:https://ps.outlook.com/PowerShell-LiveID;[!o365-location]:GB;[!o365-subscription-sku]:ENTERPRISEPACK;

The collection of user-defined substitution variables that can be used in PowerShell scripts.

Change Conditions: ??

### PowerShell Init Script <a name="psinits"></a>
{: .no_toc }
Default Value: # Set this so that errors are thrown from Cmdlets

The PowerShell script that will be run once at the start of a migration.

Change Conditions: ??

### PowerShell Before Script <a name="psbefore"></a>
{: .no_toc }
Default Value: # Set this so that errors are thrown from Cmdlets

The PowerShell script that will be run at the beginning of every user migration.

Change Conditions: ??

### PowerShell After Script <a name="psafter"></a>
{: .no_toc }
Default Value: None

The PowerShell script that will be run at the end of every user migration.

Change Conditions: ??

### PowerShell Finalize Script <a name="psfinal"></a>
{: .no_toc }
Default Value: try{Get-PSSession | Remove-PSSession}catch

The PowerShell script that will be run when all migrations have been completed.

Change Conditions: ??

### Run PowerShell Init Script <a name="runpsinit"></a>
{: .no_toc }
Default Value: Never

Choose whether to run the PowerShell initialisation script. This script will be run once only per migration (not once per user).

Change Conditions: ??

### Run PowerShell Before Script <a name="runpsbefore"></a>
{: .no_toc }
Default Value: Never

Choose whether to run the PowerShell before script. This script will be run at the start of every user migration.

Change Conditions: ??

### Run PowerShell After Script <a name="runpsafter"></a>
{: .no_toc }
Default Value: Never

Choose whether to run the PowerShell after script. This script will be run at the end of every user migration.

Change Conditions: ??

### Run PowerShell Finalize Script <a name="runpsfin"></a>
{: .no_toc }
Default Value: Always

Choose whether to run the PowerShell finalize script. This script will be run when all migrations have completed.

Change Conditions: ??

