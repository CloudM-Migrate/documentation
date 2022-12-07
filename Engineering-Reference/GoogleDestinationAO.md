---
layout: default
title: Google
grand_parent: Engineering Reference
parent: Destination Advanced Options
nav_order: 2
---

## Google Destination Advanced Options
{: .no_toc }

---

This document will give an overview on all the Google Destination Advanced Options in CloudM Migrate. 

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

1. [Archive Inbox Email](#arcinboxe)
2. [Modify Sent Address](#modsentadd)
3. [Email Import Thread Count](#emailthread)
4. [Use Limited Scopes](#uselimsco)
5. [Create Sub Labels](#cresublab)
6. [Apply Inbox Label to Sub-Folders](#appinsubfol)
7. [Email Transfer Delay](#emailtransd)
8. [Maximum Batch Count](#maxbatc)
9. [Explode Message Labels](#explmeslab)

### Archive Inbox Email <a name="arcinboxe"></a>
{: .no_toc }
Default Value: Off

Migrated Inbox email directly into 'All Mail' within Google Workspace and not to the Inbox.

Change Conditions: ??

### Modify Sent Address <a name="modsentadd"></a>
{: .no_toc }
Default Value: On

Modify the 'From' header on sent emails to the email address of the destination account if required to enable correct display in Google Workspace.

Change Conditions: ??

### Email Import Thread Count <a name="emailthread"></a>
{: .no_toc }
Default Value: 50

Set the number of threads that will be used per-user to migrate email to Google Workspace.

Change Conditions: ??

### Use Limited Scopes <a name="uselimsco"></a>
{: .no_toc }
Default Value: Off

Use Limited Scopes requires the following scopes to be enabled: 'https://www.googleapis.com/auth/gmail.labels' and 'https://www.googleapis.com/auth/gmail.insert'

Change Conditions: ??

### Create Sub Labels <a name="cresublab"></a>
{: .no_toc }
Default Value: On

Create sub-labels when creating labels for messages.

Change Conditions: ??

### Apply Inbox Label to Sub-Folders <a name="appinsubfol"></a>
{: .no_toc }
Default Value: Off

When a message from the source system was in a folder in the inbox, create the message with both 'Inbox' and 'Folder Name' labels. Set to false to just create the folder label.

Change Conditions: ??

### Email Transfer Delay <a name="emailtransd"></a>
{: .no_toc }
Default Value: 0

Specify the time (in milliseconds) to wait between sending messages. Normally this can be left at zero (0), but may need to be adjusted in some circumstances.

Change Conditions: ??

### Maximum Batch Count <a name="maxbatc"></a>
{: .no_toc }
Default Value: 0

Specify the maximum number of messages in a single batch. Specify 0 to let CloudM Migrate automatically allocate batches. Only applicable for immediate migrations.

Change Conditions: ??

### Explode Message Labels <a name="explmeslab"></a>
{: .no_toc }
Default Value: Off

Instead of labels based on nested folder structure create one label per folder.

Change Conditions: ??

---
## Contact

1. [Archive Inbox Email](#migmycon)

### Migrate to 'My Contacts' <a name="migmycon"></a>
{: .no_toc }
Default Value: On

Migrate user contacts to 'My Contacts' instead of only to 'All Contacts'.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Force Appointment Acceptance](#forappacc)
2. [Appointment Privacy](#apppriv)
3. [Default Calendar Timezone](#defcaltime)
4. [Color Categorized Appointments](#colcatapp)
5. [Migrate Attachments](#migatta)
6. [Exclude Appointment Attachment Extensions](#exappattext)
7. [Force Busy Status](#forbusy)
8. [Maximum Attendees](#maxattend)
9. [Send Individual Events](#sendindeve)
10. [Appointment Attachment Document Sharing](#appattdocs)
11. [Migrate Attachments Folder ](#migattfol)

### Force Appointment Acceptance <a name="forappacc"></a>
{: .no_toc }
Default Value: Off

Force acceptance of all migrated appointments.

Change Conditions: ??

### Appointment Privacy <a name="apppriv"></a>
{: .no_toc }
Default Value: Original

Set the privacy of migrated appointments to the following setting.

Change Conditions: ??

### Default Calendar Timezone <a name="defcaltime"></a>
{: .no_toc }
Default Value: Europe/London

Specify the default calendar timezone to use where a timezone could not otherwise be obtained. This only applies to recurring items without a timezone and where the Google calendar timezone is UTC.

Change Conditions: ??

### Color Categorized Appointments <a name="colcatapp"></a>
{: .no_toc }
Default Value: On

Color appointments based on categories in the source system when the source system supports categories.

Change Conditions: ??

### Migrate Attachments <a name="migatta"></a>
{: .no_toc }
Default Value: Off

Migrate appointment attachments to Google Drive.

Change Conditions: ??

### Exclude Appointment Attachment Extensions <a name="exappattext"></a>
{: .no_toc }
Default Value: None

Specify the list of file extensions of attachments that will not be migrated, Leave empty to migrate all attachments.

Change Conditions: ??

### Force Busy Status <a name="forbusy"></a>
{: .no_toc }
Default Value: Off

Force busy status when appointments have been tentatively accepted.

Change Conditions: ??

### Maximum Attendees <a name="maxattend"></a>
{: .no_toc }
Default Value: 500

The maximum number of event attendees. When this number has been reached, no more will be added.

Change Conditions: ??

### Send Individual Events <a name="sendindeve"></a>
{: .no_toc }
Default Value: Off

Send individual appointment events rather than as a batch (recommended in some cases if rate limits are exceeded).

Change Conditions: ??

### Appointment Attachment Document Sharing <a name="appattdocs"></a>
{: .no_toc }
Default Value: On

When migrating appointment attachments to Drive, choose whether the attachment should be shared with the appointment attendees.

Change Conditions: ??

### Migrate Attachments Folder <a name="migattfol"></a>
{: .no_toc }
Default Value: None

Migrate appointment attachments to the specified folder when 'Migrate Attachments' is enabled.

Change Conditions: ??

---
## Document
[Back to Top](#top)

1. [Use Cached Items Mapping](#usecacitemap)
2. [Allow Non-Google Sharing](#allnogoosha)
3. [Maximum Results Per Request](#maxreperre)
4. [Notify Sharing Link Members](#notshlinmem)
5. [Replace Comment Mentions with Display Name](#recommendis)
6. [Preserve Modified Date](#persmodda)
7. [Allow Alternate Item Ownership](#allalitow)
8. [Batch Permissions](#dbatperm)
9. [Trash Duplicate Items](#trashdupes)
10. [Skip Post Processing of Existing Items ](#skippoproex)

### Use Cached Items Mapping <a name="usecacitemap"></a>
{: .no_toc }
Default Value: On

Force acceptance of all migrated appointments.

Change Conditions: ??

### Allow Non-Google Sharing <a name="allnogoosha"></a>
{: .no_toc }
Default Value: Off

Allow permissions to be added for users without Google accounts by sending notification emails to those users. Note this can result in many emails being sent to any non-Google addresses.

Change Conditions: ??

### Maximum Results Per Request <a name="maxreperre"></a>
{: .no_toc }
Default Value: 100

The maximum number of results to return for individual queries to the Drive API.

Change Conditions: ??

### Notify Sharing Link Members <a name="notshlinmem"></a>
{: .no_toc }
Default Value: Off

Send email notification containing Drive sharing link to SharePoint Sharing Link members.

Change Conditions: ??

### Replace Comment Mentions with Display Name <a name="recommendis"></a>
{: .no_toc }
Default Value: Off

Replace an email address mention in a comment with the associated user's display name.

Change Conditions: ??

### Preserve Modified Date <a name="persmodda"></a>
{: .no_toc }
Default Value: On

When migrating Google Drive items, attempt to preserve the last modified date in the destination domain.

Change Conditions: ??

### Allow Alternate Item Ownership <a name="allalitow"></a>
{: .no_toc }
Default Value: Off

When migrating items, allow the owner to be changed if the actual owner does not exist or is disabled in the destination Google Workspace domain. WARNING: setting this option can cause the ownership of items to change, use only in specialized scenarios.

Change Conditions: ??

### Batch Permissions <a name="dbatperm"></a>
{: .no_toc }
Default Value: Off

Use batching to provide faster, but more error prone, Google Drive migrations.

Change Conditions: ??

### Trash Duplicate Items <a name="trashdupes"></a>
{: .no_toc }
Default Value: On

Trash duplicate items when performing Delta migrations.

Change Conditions: ??

### Skip Post Processing of Existing Items <a name="skippoproex"></a>
{: .no_toc }
Default Value: Off

Skip permission and parent folder patching of existing Drive items. Items that have been explicitly updated will still be processed.

Change Conditions: ??

---
## Document Conversion
[Back to Top](#top)

1. [Convert Text](#dcontxt)
2. [Convert Presentations](#dconpre)
3. [Convert OCR](#conocr)
4. [Convert Spreadsheets](#conspread)
5. [Convert Drawings](#condraw)

### Convert Text <a name="dcontxt"></a>
{: .no_toc }
Default Value: Off

Where possible, convert Text (.doc, .txt, etc.) documents to Google Documents format.

Change Conditions: ??

### Convert Presentations <a name="dconpre"></a>
{: .no_toc }
Default Value: Off

Where possible, convert Presentations (.ppt, etc.) to Google Documents format.

Change Conditions: ??

### Convert OCR <a name="conocr"></a>
{: .no_toc }
Default Value: Off

Where possible, convert images (*.png, *.jpg, etc.) via OCR to Google Documents format.

Change Conditions: ??

### Convert Spreadsheets <a name="conspread"></a>
{: .no_toc }
Default Value: Off

Where possible, convert Spreadsheets (*.csv, *.xls, etc.) to Google Documents format.

Change Conditions: ??

### Convert Drawings <a name="condraw"></a>
{: .no_toc }
Default Value: Off

Where possible, convert Drawings (.wmf) to Google Documents format.

Change Conditions: ??

---
## Shared Drive
[Back to Top](#top)

1. [Shared Drive File Permissions](#shadrifiper)
2. [Shared Drive Same Domain Migration Type](#shasammigt)
3. [Shared Drive Default Managers](#shdrideman)
4. [Migrate External Shared Drive Members](#migexshdrmem)
5. [Shared Drive Folder Permissions](#shdrfolper)
6. [Migrate Shared Drive Members](#migshdmem)
7. [Remove Shared Drive Default Managers](#reshdrdman)

### Shared Drive File Permissions <a name="shadrifiper"></a>
{: .no_toc }
Default Value: File

Select how file permissions will be applied when migrating to Shared Drive.

Change Conditions: ??

### Shared Drive Same Domain Migration Type <a name="shasammigt"></a>
{: .no_toc }
Default Value: Move

When migrating a Google Drive to Shared Drive within the same domain, move or copy the files and folders.

Change Conditions: ??

### Shared Drive Default Managers <a name="shdrideman"></a>
{: .no_toc }
Default Value: None

Specify the list of managers email addresses. Should be valid user emails. Group emails are not allowed. These will be applied temporarily during migration of the Shared Drive, in order to improve performance, and removed upon completion if 'Remove Shared Drive Default Managers' is set to true.

Change Conditions: ??

### Migrate External Shared Drive Members <a name="migexshdrmem"></a>
{: .no_toc }
Default Value: Off

Migrate External Shared Drive members when migrating a Shared Drive to Shared Drive. Please note sharing with external users will also be migrated.

Change Conditions: ??

### Shared Drive Folder Permissions <a name="shdrfolper"></a>
{: .no_toc }
Default Value: None

Select how folder permissions will be applied when migrating to Shared Drive.

Change Conditions: ??

### Migrate Shared Drive Members <a name="migshdmem"></a>
{: .no_toc }
Default Value: Off

Migrate Shared Drive members when migrating a Shared Drive to Shared Drive.

Change Conditions: ??

### Remove Shared Drive Default Managers <a name="reshdrdman"></a>
{: .no_toc }
Default Value: Off

Remove the Shared Drive Default Managers specified in 'Shared Drive Default Managers' field.

Change Conditions: ??

---
## User
[Back to Top](#top)

1. [Check Users/Resources/Groups/Shared Drives Exist](#checrgsdex)
2. [Check Services Enabled](#cheseren)
3. [Create Users/Resources/Groups/Shared Drives](#crergsd)
4. [Change Password On Login](#chapasslog)

### Check Users/Resources/Groups/Shared Drives Exist <a name="checrgsdex"></a>
{: .no_toc }
Default Value: On

Check that users/resources/groups/shared drives exist within the destination system.

Change Conditions: ??

### Check Services Enabled <a name="cheseren"></a>
{: .no_toc }
Default Value: Off

When running the 'Check Users' action, also check if the selected Google services for that user are enabled.

Change Conditions: ??

### Create Users/Resources/Groups/Shared Drives <a name="crergsd"></a>
{: .no_toc }
Default Value: Off

Create any Users (Resources, Groups or Shared Drives) that do not exist within the Google Workspace domain.

Change Conditions: ??

### Change Password On Login <a name="chapasslog"></a>
{: .no_toc }
Default Value: Off

Set this to force the user to change their password on first login.

Change Conditions: ??

---
## Transfer and Performance
[Back to Top](#top)

1. [Timeout](#tptimeo)
2. [Retry Count](#tpretryc)
3. [Modify Request](#tmodreq)
4. [Drive Locks from Listed Users](#drilolisuse)
5. [Maximum Batch Count](#maxbatco)
6. [Lock Retry Count](#tplockretrco)
7. [Multi-Server Drive Migration](#muldmig)

### Timeout <a name="tptimeo"></a>
{: .no_toc }
Default Value: 3600000

The timeout (in milliseconds) that will be used for all calls to the Google Workspace services. This should be set to a high value to ensure large transfers can be made, unless there is a specific reason to change it, the default value should be retained.

Change Conditions: ??

### Retry Count <a name="tpretryc"></a>
{: .no_toc }
Default Value: 20

The number of times a failed transfer will be attempted before aborting.

Change Conditions: ??

### Modify Request <a name="tmodreq"></a>
{: .no_toc }
Default Value: Off

Remove the 'Expect-100' header from requests (required for use behind some proxies).

Change Conditions: ??

### Drive Locks from Listed Users <a name="drilolisuse"></a>
{: .no_toc }
Default Value: Off

Use only users from the user list to obtain locks for Drive files when migrating in multi-server configurations. WARNING: You must always perform migrations with the same user list at any one time to use this option or duplicate items will be migrated.

Change Conditions: ??

### Maximum Batch Count <a name="maxbatco"></a>
{: .no_toc }
Default Value: 10

The count of (non-mail) items that will be sent in a single request. Maximum 100.

Change Conditions: ??

### Lock Retry Count <a name="tplockretrco"></a>
{: .no_toc }
Default Value: 20

The number of times a failed distributed lock will be attempted before aborting.

Change Conditions: ??

### Multi-Server Drive Migration <a name="muldmig"></a>
{: .no_toc }
Default Value: On

Allow Google Drive migrations to be run on multiple servers (may slightly degrade performance on a single server).

Change Conditions: ??
