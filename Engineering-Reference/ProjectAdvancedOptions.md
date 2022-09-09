---
layout: default
title: Project Advanced Options
parent: Engineering Reference
has_children: true
nav_order: 4
---
## Project Advanced Options Overview 
{: .no_toc }
This document will give an overview on all the project advanced options in CloudM Migrate. The project advanced options allow CloudM to have it's unique flexibility to fit a wide range of requirements. This guide will provide an explination for each so you can decide if it's relavent to your requirements. 

We recommend reviewing these options as they can have a fundamental impact on the success of your project. 

---
<a name="top"></a>
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## System

### Auto Cancel Period 
{: .no_toc }
Default Value: Never

Select a time period after which the migration will be automatically be stopped. 

Change Conditions: You want the migration to end in a specified period of time. 

### Validate SSL Certificates <a name="validatessl"></a>
{: .no_toc }
Default Value: On

SSL certificates must keep valid while migrating. Recommended to leave on but can be disabled for testing if needed. 

Change Conditions: SSL Certification checking disabled to test a migration. It's not recommended to disable. 

### Migration Performance Interval <a name="migrateperf"></a>
{: .no_toc }
Default Value: 600

Set the interval used for calculating migration performance metrics in seconds.

Change Conditions: Increase or decrease the performance data fidelity.

### Memory Usage Minimum Available Memory <a name="memoryusemin"></a>
{: .no_toc }
Default Value: 250

Specify the minimum available system memory in MB required to prevent rate limiting.

Change Conditions: ??

### Item Export Delay <a name="itemexportdelay"></a>
{: .no_toc }
Default Value: 0

Delay for the specified number of milliseconds after exporting a single item from any source system. Can be used to prevent resource overload on source systems if required.

Change Conditions: Ease performance of source server. 

### Auto Restart Crashed Users <a name="autorestart"></a>
{: .no_toc }
Default Value: Off

If a user migration fails due to a crash, restart the migration. Failures due to none-crash conditions will not be auto-restarted.

Change Conditions: ??

### Trace Level <a name="tracelevel"></a>
{: .no_toc }
Default Value: Debug

Specify the trace level of the debug output (from 0 (off) to 5 (debug)).

Change Condition: Recommend to keep at 5 for troubleshooting and required for regulatory compliance.

### Migration History Interval <a name="migratehistory"></a>
{: .no_toc }
Default Value: 30000

Set the interval between aggregating migration history records in milliseconds.

Change Conditions: ??

### Memory Usage Check <a name="memuse"></a>
{: .no_toc }
Default Value: Off

Rate limit the migration using available system memory.

Change Conditions: ??

### Simultaneous Migrations per Configuration Limit <a name="simmigateper"></a>
{: .no_toc }
Default Value: 0

The number of migrations to run per configuration. Zero turns the setting off. Service level configuration 'Maximum User Migrations' per server will always override this setting.

Change Conditions: ??

### Drive Thread Count <a name="drivethread"></a>
{: .no_toc }
Default Value: 3

The number of simultaneous per-user threads when migrating documents. 

Change Conditions: Decrease or Increase depending of source server load. This normally should not be changed.

### Allow Multiple Sources <a name="allowmultiple"></a>
{: .no_toc }
Default Value: Off

Allow the migration of multiple source items, of the same type, to a single destination item.

Change Conditions: ??

---
## Email <a name="email"></a> 
[Back to Top](#top)

### Migration Folders <a name="migratefolder"></a>
{: .no_toc }
Default Value: All Folders
 
Select the folders to migrate. 

Change Conditions: You want to select specific folders to migrate. 

### Excluded Folders <a name="excludefolder"></a>
{: .no_toc }
Default Value: None

Specify a list of folder names that will be excluded from the migration.

Change Conditions: Some folders are not needed on the destination.

### Exclude Attachment Extensions <a name="excludeattachexe"></a>
{: .no_toc }
Default Value: None

Specify the list of file extensions of attachments that will not be migrated, Leave empty to migrate all attachments.

Change Conditions: Certain file types are not needed on the destination such as a .pdf. 

###  Modified Messages Label <a name="modifiedlabel"></a>
{: .no_toc }
Default Value: Modified

The label/category to use when labeling modified messages if the 'Label Modified Messages' option has been set.

Change Conditions: ??

### Message Labels <a name="messagelabel"></a>
{: .no_toc }
Default Value: None

Apply the specified label or category to all messages. To specify multiple labels, provide a semi-colon delimited list.

Change Conditions: You only want to migration email that contain a specified label. 

### Archive Folder Structure <a name="archivefolderstruc"></a>
{: .no_toc }
Default Value: Off

Archive the entire message folder structure under the folder specified by 'Archive Folder Structure Name'.

Change Conditions: You wish to store all source email into a specific folder on the destination.

### Private Chat Top Level Folder Name <a name="privatechattop"></a>
{: .no_toc }
Default Value: Private Chats

If migrating Teams Private Chats, places all conversations within a folder of the specified name.

Change Conditions: Change the folder name where MS Teams private chats older then 7 days are stored in Outlook. 

### Included Folders <a name="includefolders"></a>
{: .no_toc }
Default Value: None

Specify a list of folder names that will be included with the migration when Migration Folders is set to Specified Only.

Change Conditions: When specifcing to only migrate certain folders, this setting will require the folder you wish to migrate. 

### Migrate Attachments <a name="migrateattach"></a>
{: .no_toc }
Default Value: On

Migrate email attachments to GMail. Note that any email message attachments will always be processed.

Change Conditions: You wish to not migrate email attachments. 

### Modify Invalid Messages <a name="modifyinvalid"></a>
{: .no_toc }
Default Value: On

Attempt to modify messages if they are oversized or have bad attachments before importing to the destination system.

Change Conditions: ??

### Label Modified Messages <a name="labelmodified"></a>
{: .no_toc }
Default Value: Off

Apply a label or category to messages that have been modified as part of the migration process (such as having an oversized attachment removed).

Change Conditions: You want a message labeled if it was modified during migration. 

### Migrate Headers Only <a name="migrateheader"></a>
{: .no_toc }
Default Value: Off

Migrate only message headers from supported systems.

Change Conditions: You only want a retroactive record of sent and received email, all message content is stripped. 

### Archive Folder Structure Name <a name="archivefolderstruc"></a>
{: .no_toc }
Default Value: None

The name of the base folder when using 'Archive Folder Structure'.

Change Conditions: ??
