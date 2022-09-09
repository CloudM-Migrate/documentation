---
layout: default
title: Google
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 1
---

## Google Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Google Source Advanced Options in CloudM Migrate. 

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
## Email

1. [Use Limited Scopes](#limitedscope)
2. [Enable Gmail Discovery throttle](#gmaildiscoverythrottle)
3. [Gmail Discovery request per 100 seconds limit](#gmaildiscoveryper100)
4. [Gmail API Filter Override](#gmailapifilter)
5. [Gmail Discovery request per second limit](#gmailrequestper)

### Use Limited Scopes <a name="limitedscope"></a>
{: .no_toc }
Default Value: Off

Use Limited Scopes requires the following scopes to be enabled: 'https://www.googleapis.com/auth/gmail.labels' and 'https://www.googleapis.com/auth/gmail.readonly'.

Change Conditions: ??

### Enable Gmail Discovery throttle <a name="gmaildiscoverythrottle"></a>
{: .no_toc }
Default Value: Off

Enable request per second/minute limits for Gmail Discovery Service.

Change Conditions: ??

### Gmail Discovery request per 100 seconds limit <a name="gmaildiscoveryper100"></a>
{: .no_toc }
Default Value: 1000

Gmail Discovery maximum requests per 100 seconds before throttling.

Change Conditions: ??

### Gmail API Filter Override <a name="gmailapifilter"></a>
{: .no_toc }
Default Value: None

When using the Gmail API to export email, use the provided filter to override other tool settings. Leave empty to auto generate the filter. Note: this will override the following settings: Date Ranges, Folders and Excluded Folders.

Change Conditions: ??

### Gmail Discovery request per second limit <a name="gmailrequestper"></a>
{: .no_toc }
Default Value: 10

Gmail Discovery maximum requests per second before throttling

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Migrate Meeting Links](#migratemeetinglin)

### Migrate Meeting Links <a name="migratemeetinglink"></a>
{: .no_toc }
Default Value: On

Migrate meeting links within appointments.

Change Conditions: ??

---
## Document
[Back to Top](#top)

1. [Migrate All Drive Items](#migratealldrive)
2. [Check External Drive Sharing](#checkexternaldrive)
3. [Migrate Contents of Non-Owned Folders](#migratecontentnonown)
4. [Preserve Modified Date](#perservemoddate)
5. [Ignore Shared Drive file and folder ACLs](#ignoresharedriveacl)
6. [Migrate File Comments](#migratefilecom)
7. [Allow Migration of Suspicious Files](#allowmigsusfiles)
8. [Exclude External Permissions](#excludeexternalperms)
9. [Migrate Items Only From Listed Users](#migrateitemslistuser)
10. [Migrate Orphaned Folders](#migrateorphanedfold)
11. [Maximum Results Per Request (Drive API)](#maxresultper)
12. [Migrate Orphaned Folders](#migrateorphanedfold)
13. [Maximum Results Per Request (Comments API)](#maxresultpercom)

### Migrate All Drive Items <a name="migratealldrive"></a>
{: .no_toc }
Default Value: On

Migrate all Drive items necessary for full-fidelity migration. Setting this to false may result in folder layout discrepancies and sharing issues.

Change Conditions: ??

### Check External Drive Sharing <a name="checkexternaldrive"></a>
{: .no_toc }
Default Value: On

Check if external domain sharing is enabled when migrating from Google Drive to Drive. This can be disabled if Drive sharing is disabled and you have whitelisted the destination domain in the source domain.

Change Conditions: ??

### Migrate Contents of Non-Owned Folders <a name="migratecontentnonown"></a>
{: .no_toc }
Default Value: Off

Migrate contents of folders not owned by the migrating user. This usually only needs enabling when some users are not migrated to the destination.

Change Conditions: ??

### Preserve Modified Date <a name="perservemoddate"></a>
{: .no_toc }
Default Value: On

When migrating Google Drive items, attempt to preserve the last modified date in the source domain.

Change Conditions: ??

### Ignore Shared Drive file and folder ACLs <a name="ignoresharedriveacl"></a>
{: .no_toc }
Default Value: Off

Whether to ignore ACLs for individual files and folders contained within Shared Drives.

Change Conditions: ??

### Migrate File Comments <a name="migratefilecom"></a>
{: .no_toc }
Default Value: Off

Migrate file comments from Google Drive to Google Drive.

Change Conditions: ??

### Allow Migration of Suspicious Files <a name="allowmigsusfiles"></a>
{: .no_toc }
Default Value: Off

Allow migration of suspicious files from Google Drive to other platforms.

Change Conditions: ??

### Exclude External Permissions <a name="excludeexternalperms"></a>
{: .no_toc }
Default Value: Off

Only migrate permissions from users/groups that are members of the migrating domain.

Change Conditions: ??

### Migrate Items Only From Listed Users <a name="migrateitemslistuser"></a>
{: .no_toc }
Default Value: Off

Migrate only Drive items from those users listed on the users page. 'Migrate All Drive Items' should also be true for this setting to apply. If you want to migrate items from users other than those being migrated, be sure to include them on the users page but do not select them for migration.

Change Conditions: ??

### Migrate Orphaned Folders <a name="migrateorphanedfold"></a>
{: .no_toc }
Default Value: On

The maximum number of results to return for individual queries to the Drive API.

Change Conditions: ??

### Maximum Results Per Request (Drive API) <a name="maxresultper"></a>
{: .no_toc }
Default Value: On

The maximum number of results to return for individual queries to the Drive API.

Change Conditions: ??

### Export Documents Path Folder <a name="migrateorphanedfold"></a>
{: .no_toc }
Default Value: Off

Setting 'Export Documents Path Folder' to true will export the folder specified in 'Documents Path' on the users page.

Change Conditions: ??

### Maximum Results Per Request (Comments API) <a name="maxresultpercom"></a>
{: .no_toc }
Default Value: 100

The maximum number of results to return for individual queries to the Comments API.

Change Conditions: ??

