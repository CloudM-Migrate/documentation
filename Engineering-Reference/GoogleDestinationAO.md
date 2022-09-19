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

When migrating appointment attachments to Drive, choose whether the attachment should be shared with the appointment attendees.

Change Conditions: ??
