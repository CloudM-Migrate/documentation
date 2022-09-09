---
layout: default
title: O365
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 2
---

## O365 Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the O365 Source Advanced Options in CloudM Migrate. 

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
2. [SharePoint Admin Url](#sharepointadmin)
3. [Timeout](#sharepointtime)
4. [Include Classic Team Sites in User List](#includeclassicteam)
5. [Retry Count](#retrycount)
6. [Document Sharing/Permissions](#retrycount)
7. [Hybrid Environment](#hybridenv)


### SharePoint Migration API <a name="sharepointapi"></a>
{: .no_toc }
Default Value: Off

SharePoint Migration API is recommended for all migrations to SharePoint Online and OneDrive for Business. For more information see the article here.

Change Conditions: ??

### SharePoint Admin Url <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The Url for the SharePoint admin center e.g. https://tenant-admin.sharepoint.com

Change Conditions: ??

### Timeout <a name="sharepointtime"></a>
{: .no_toc }
Default Value: 1800000

The timeout that will apply to communications with the SharePoint server.

Change Conditions: ??

### Include Classic Team Sites in User List <a name="includeclassicteam"></a>
{: .no_toc }
Default Value: Off

Specifies whether Team Sites will be obtained when getting a user list.

Change Conditions: ??

### Retry Count <a name="retrycount"></a>
{: .no_toc }
Default Value: 10

The number of times an operation will be attempted before failing.

Change Conditions: ??

### Document Sharing/Permissions <a name="docsharingoperm"></a>
{: .no_toc }
Default Value: Share Documents

Choose whether the document should be shared as per the source file ACLs if they can be resolved to email addresses (see documentation).

Change Conditions: ??

### Hybrid Environment <a name="hybridenv"></a>
{: .no_toc }
Default Value: Share Documents

Allows a custom 'SharePoint Admin Url' and 'SharePoint My Sites Url' to be entered for hybrid migration.

Change Conditions: ??

---
## Email

