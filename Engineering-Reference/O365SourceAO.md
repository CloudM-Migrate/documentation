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

1. [Excluded Item Classes](#excludeitem)
2. [Log Excluded Items](#logexcludeitem)
3. [Recoverable Mail Items](#recovermailitem)
4. [Extended MAPI Properties](#extendmapiprop)
5. [Included Item Classes](#includeitemclass)
6. [Migrate SMIME Signed Messages Without Modification ](#migratesmime)
7. [Recoverable Mail Items Label/Category](#recovermailitemlabel)

### Excluded Item Classes <a name="excludeitem"></a>
{: .no_toc }
Default Value: None

Specify the list of item classes that will not be processed as part of a migration. Exact matches are made on the value specified here.

Change Conditions: ??

### Log Excluded Items <a name="logexcludeitem"></a>
{: .no_toc }
Default Value: Off

Include excluded mail items in the migration reports. May produce large reports where many items are not migrated due to matching rules.

Change Conditions: ??

### Recoverable Mail Items <a name="recovermailitem"></a>
{: .no_toc }
Default Value: None

Select how to include recoverable mail items when migrating from Exchange and Office 365.

Change Conditions: ??

### Extended MAPI Properties <a name="extendmapiprop"></a>
{: .no_toc }
Default Value: Archive ID:String;Saveset ID:String;ExMD5:String;ExShortcut:Integer;PR_MSGID2:String;

Specify the list of custom MAPI properties to migrate (valid when migrating to Exchange/Office 365 only).

Change Conditions: ??

### Included Item Classes <a name="includeitemclass"></a>
{: .no_toc }
Default Value: IPM.Note;IPM.Note.*

Specify the list of item classes that will be processed as part of a migration. Wildcard matches can be used.

Change Conditions: ??

### Migrate SMIME Signed Messages Without Modification <a name="migratesmime"></a>
{: .no_toc }
Default Value: On

When migrating SMIME signed messages, perform no modification of the messages. This could mean some other features of CloudM Migrate may not be executed, such as moving attachments to Drive or ensuring the sent address is correct. It will ensure however that the digital signature verifies.

Change Conditions: ??

### Recoverable Mail Items Label/Category <a name="recovermailitemlabel"></a>
{: .no_toc }
Default Value: Recoverable Items

Apply the specified label/category to items migrated from within the Recoverable Items folder. Leave empty to not apply a label/category.

Change Conditions: ??
