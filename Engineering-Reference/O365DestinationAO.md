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
2. [Retry Backoff](#retryback)
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

### Retry Backoff (seconds) <a name="retryback"></a>
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

Change Conditions: ??

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
## Microsoft Teams/Group 

1.

### Teams Direct Migration <a name="docsharperm"></a>
{: .no_toc }
Default Value: Off

This is the items I spoke with lloyd about, prestaging vs already exisiting destination team


Change Conditions: ??

### Retry Backoff (seconds) <a name="docsharperm"></a>
{: .no_toc }
Default Value: 3

SharePoint Migration API Retry Backoff in seconds.

Change Conditions: ??

### SharePoint Admin Url <a name="docsharperm"></a>
{: .no_toc }
Default Value: None

The Url for the SharePoint admin center e.g. https://tenant-admin.sharepoint.com

Change Conditions: ??

### Timeout <a name="docsharperm"></a>
{: .no_toc }
Default Value: 1800000

The timeout that will apply to communications with the SharePoint server.

Change Conditions: ??

### Preserve File Created and Modified Dates <a name="docsharperm"></a>
{: .no_toc }
Default Value: On

Preserve the Original File Created and Modified Dates.

Change Conditions: ??

### Provision Sites <a name="docsharperm"></a>
{: .no_toc }
Default Value: On

Provision any Sites that do not exist.

Change Conditions: ??

### Hybrid Environment <a name="docsharperm"></a>
{: .no_toc }
Default Value: On

Allows a custom 'SharePoint Admin Url' and 'SharePoint My Sites Url' to be entered for hybrid migration.

Change Conditions: ??

### SharePoint Storage <a name="docsharperm"></a>
{: .no_toc }
Default Value: Office 365

Choose whether the document should be shared as per the source file ACLs if they can be resolved to email addresses (see documentation).

Change Conditions: ??

