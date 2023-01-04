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

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/GoogleSource.html">Google Source Options</a>

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

Change Conditions: When enabled, only the Gmail API scopes will be used. For email only migrations.

### Enable Gmail Discovery throttle <a name="gmaildiscoverythrottle"></a>
{: .no_toc }
Default Value: Off

Enable request per second/minute limits for Gmail Discovery Service.

Change Conditions: When enabled, the below per second and per 100 second max request limits will be used. Can be used to lessen throttling.

### Gmail Discovery request per 100 seconds limit <a name="gmaildiscoveryper100"></a>
{: .no_toc }
Default Value: 1000

Gmail Discovery maximum requests per 100 seconds before throttling.

### Gmail Discovery request per second limit <a name="gmailrequestper"></a>
{: .no_toc }
Default Value: 10

Gmail Discovery maximum requests per second before throttling

### Gmail API Filter Override <a name="gmailapifilter"></a>
{: .no_toc }
Default Value: None

When using the Gmail API to export email, use the provided filter to override other tool settings. Leave empty to auto generate the filter. Note: this will override the following settings: Date Ranges, Folders and Excluded Folders.

Change Conditions: A customer Gmail filter can be entered, this will filter the email migration export to the filter entered.

---
## Calendar
[Back to Top](#top)

1. [Migrate Meeting Links](#migratemeetinglink)

### Migrate Meeting Links <a name="migratemeetinglink"></a>
{: .no_toc }
Default Value: On

Migrate meeting links within appointments.

Change Conditions: Enabling will prevent Meet links being migrated with calendar events.

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

Change Conditions: Disabling will migrate only owned items for users. Only change if recommended by CloudM.

### Check External Drive Sharing <a name="checkexternaldrive"></a>
{: .no_toc }
Default Value: On

Check if external domain sharing is enabled when migrating from Google Drive to Drive. This can be disabled if Drive sharing is disabled and you have whitelisted the destination domain in the source domain.

Change Conditions: The external sharing check will not be performed when disabled.

### Migrate Contents of Non-Owned Folders <a name="migratecontentnonown"></a>
{: .no_toc }
Default Value: Off

Migrate contents of folders not owned by the migrating user. This usually only needs enabling when some users are not migrated to the destination.

Change Conditions: Will migrate files in non-owned folders when enabled. 

### Preserve Modified Date <a name="perservemoddate"></a>
{: .no_toc }
Default Value: On

When migrating Google Drive items, attempt to preserve the last modified date in the source domain.

Change Conditions: The last modified date will be the migration date if disabled.

### Ignore Shared Drive file and folder ACLs <a name="ignoresharedriveacl"></a>
{: .no_toc }
Default Value: Off

Whether to ignore ACLs for individual files and folders contained within Shared Drives.

Change Conditions: Explicit permissions of Shared Drive items will not be migrated if enabled.

### Migrate File Comments <a name="migratefilecom"></a>
{: .no_toc }
Default Value: Off

Migrate file comments from Google Drive to Google Drive.

Change Conditions: File comments will be migrated if enabled.

### Allow Migration of Suspicious Files <a name="allowmigsusfiles"></a>
{: .no_toc }
Default Value: Off

Allow migration of suspicious files from Google Drive to other platforms.

Change Conditions: When enabled, this setting will allow you to migrate any suspicious files with an "acknowledgeAbuse" flag, so that the process does not fail. When set to false (disabled), suspicious files will not be migrated and the process will fail quicker. Please note that migrating suspicious files carries a risk to your domain. This setting will not be visible for Google Workspace to Google Workspace migrations

### Exclude External Permissions <a name="excludeexternalperms"></a>
{: .no_toc }
Default Value: Off

Only migrate permissions from users/groups that are members of the migrating domain.

Change Conditions: Non-domain (external) will not be migrated when enabled.

### Migrate Items Only From Listed Users <a name="migrateitemslistuser"></a>
{: .no_toc }
Default Value: Off

Migrate only Drive items from those users listed on the users page. 'Migrate All Drive Items' should also be true for this setting to apply. If you want to migrate items from users other than those being migrated, be sure to include them on the users page but do not select them for migration.

Change Conditions: Only items from the users listed on the users page will be migrated when enabled.

### Migrate Orphaned Folders <a name="migrateorphanedfold"></a>
{: .no_toc }
Default Value: On

The maximum number of results to return for individual queries to the Drive API.

Change Conditions: Oprhaned folders will not be migrated when disabled. This can result in missing items.

### Maximum Results Per Request (Drive API) <a name="maxresultper"></a>
{: .no_toc }
Default Value: 100

The maximum number of results to return for individual queries to the Drive API.

Change Conditions: The max number of results can be increased or decreased. Not recommended to change, can result in performance isues.

### Export Documents Path Folder <a name="migrateorphanedfold"></a>
{: .no_toc }
Default Value: Off

Setting 'Export Documents Path Folder' to true will export the folder specified in 'Documents Path' on the users page.

Change Conditions: ??

### Maximum Results Per Request (Comments API) <a name="maxresultpercom"></a>
{: .no_toc }
Default Value: 100

The maximum number of results to return for individual queries to the Comments API.

Change Conditions: The max number of results can be increased or decreased. Not recommended to change, can result in performance isues.


---
## Chat
[Back to Top](#top)

1. [Migrate Chat History](#migratechathis)
2. [Migrated Chat Label](#migratechatlabel)

### Migrate Chat History <a name="migratechathis"></a>
{: .no_toc }
Default Value: Off

Migrate chat history.

Change Conditions: Enabling will migrate Google Chat history as emails, into the below specified label. 1 item per chat line, which can result high volumes of items to migrate.

### Migrated Chat Label <a name="migratechatlabel"></a>
{: .no_toc }
Default Value: Migrated Chats

The label that will be applied to migrated chats.

---
## Migration
[Back to Top](#top)

1. [Allow Missing Special Folders](#allowspecfolder)
2. [Strip Google Test Domain](#stripgoogletestdom)

### Allow Missing Special Folders <a name="allowspecfolder"></a>
{: .no_toc }
Default Value: Off

Permit migrations when some special folders do not exist. WARNING: this can result in missing messages if users have hidden IMAP folders.

Change Conditions: Enabling will allow migrations of mailboxes where special folders (Inbox, Sent etc.) are not present. Only required in speciall scenario, do not enable otherwise.

### Strip Google Test Domain <a name="stripgoogletestdom"></a>
{: .no_toc }
Default Value: Off

Removes the Google test domain (test-google-a.com) suffix from source email addresses, e.g. when applying address replacements to file ACLs.

Change Conditions: Will remove the test-google-a.com domain from source addresses, only recommended in specific scenario where test domain is present for bulk migration period.

---
## User
[Back to Top](#top)

1. [Migrate Account Delegates](#migrateaccountdel)
2. [Migrate Forwarding Settings](#migrateforwordset)
3. [Migrate POP Settings](#migratepopset)
4. [Migrate Out Of Office](#migrateooo)
5. [Migrate Signature](#migratesig)
6. [Migrate Signature](#migrateforwordset)
7. [Migrate IMAP Settings](#migrateimap)

### Migrate Account Delegates <a name="migrateaccountdel"></a>
{: .no_toc }
Default Value: On

Migrate user account delegation.

Change Conditions: Disabling will prevent migration of account delegation settings.

### Migrate Forwarding Settings <a name="migrateforwordset"></a>
{: .no_toc }
Default Value: On

Migrate user forwarding settings.

Change Conditions: Disabling will prevent migration of forwarding settings.

### Migrate POP Settings <a name="migratepopset"></a>
{: .no_toc }
Default Value: On

Migrate user POP email settings.

Change Conditions: Disabling will prevent migration of POP settings (Google to Google only).

### Migrate Out Of Office <a name="migrateooo"></a>
{: .no_toc }
Default Value: On

Migrate user Out Of Office settings.

Change Conditions: Disabling will prevent migration of Out of Office settings (Google to Google only).

### Migrate Signature <a name="migratesig"></a>
{: .no_toc }
Default Value: On

Migrate user signature settings.

Change Conditions: Disabling will prevent migration of signature (Google to Google only).

### Migrate Aliases<a name="migratealias"></a>
{: .no_toc }
Default Value: On

Migrate account aliases.

Change Conditions: Disabling will prevent migration of alias addresses.

### Migrate IMAP Settings <a name="migrateimap"></a>
{: .no_toc }
Default Value: On

Migrate user IMAP settings.

Change Conditions: Disabling will prevent migration of IMAP settings (Google to Google only).
