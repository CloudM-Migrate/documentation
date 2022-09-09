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
1. TOC
{:toc}
</details>

---

## System

1. [Auto Cancel Period](#autocancel)
2. [Validate SSL Certificates](#validatessl)
3. [Migration Performance Interval](#migrateperf)
4. [Memory Usage Minimum Available Memory](#memoryusemin)
5. [Item Export Delay](#itemexportdelay)
6. [Auto Restart Crashed Users](#autorestart)
7. [Trace Level](#tracelevel)
8. [Migration History Interval](#migratehistory)
9. [Memory Usage Check](#memuse)
10. [Simultaneous Migrations per Configuration Limit](#simmigateper)
11. [Drive Thread Count](#drivethread)
12. [Allow Multiple Sources](#allowmultiple)

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

1. [Migration Folders](#migratefolder)
2. [Excluded Folders](#excludefolder)
3. [Exclude Attachment Extensions](#excludeattachexe)
4. [Modified Messages Label](#modifiedlabel)
5. [Message Labels](#messagelabel)
6. [Archive Folder Structure](#archivefolderstruc)
7. [Private Chat Top Level Folder Name](#privatechattop)
8. [Included Folders](#includefolders)
9. [Migrate Attachments](#migrateattach)
10. [Modify Invalid Messages](#modifyinvalid)
11. [Label Modified Messages](#labelmodified)
12. [Migrate Headers Only](#migrateheader)
13. [Archive Folder Structure Name](#archivefolderstruc)

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

---
## Contact
[Back to Top](#top)

1. [Address Book Groups](#addressbook)
2. [Skip Quest Migration Manager System Contacts](#skipquestcontacts)

### Address Book Groups <a name="addressbook"></a>
{: .no_toc }
Default Value: Off

Create contact groups based on Address Book names when migrating from GroupWise, Exchange/Office 365 or Oracle Communications.

Change Conditions: You want to migrate current contacts in the Global Address Book. 

### Skip Quest Migration Manager System Contacts <a name="skipquestcontacts"></a>
{: .no_toc }
Default Value: Off

Do not process contacts that may have been created with Quest Migration Manager.

Change Conditions: ??

---

## Calendar
[Back to Top](#top)

1. [All Calendars](#allcalendar)
2. [Appointment Subject Tag](#appointmentsubject)
3. [Common ID Prefix Value ](#commonidpre)
4. [Shared Calendar Information](#sharedcalendarinfo)
5. [Prefix Common ID](#prefixcommon)
6. [Send Calendar Sharing Notifications](#sendcalendarsharing)

### All Calendars <a name="allcalendar"></a>
{: .no_toc }
Default Value: On

Migrate all calendars and not just the primary calendar. Additional calendars are created as secondary calendars within the destination system.

Change Conditions: Disable if additional calendars are not desired on the destination. 

### Appointment Subject Tag <a name="appointmentsubject"></a>
{: .no_toc }
Default Value: None

Tag all migrated appointment subjects with this text (leave blank for no extra tag).

Change Conditions: Add a value to all migrated appointments. 

### Common ID Prefix Value <a name="commonidpre"></a>
{: .no_toc }
Default Value: 

The prefix ID to apply to appointment Common IDs.

Change Conditions: ??

### Shared Calendar Information <a name="sharedcalendarinfo"></a>
{: .no_toc }
Default Value: On

Migrate all sharing settings for calendars.

Change Conditions: Disable to unshare calendar items on the destination. 

### Prefix Common ID <a name="prefixcommon"></a>
{: .no_toc }
Default Value: Off

Prefix the common appointment ID (ICAL UID) to prevent ID clashes between systems. Turn off when performing calendar co-existence.

Change Conditions: ??

### Send Calendar Sharing Notifications <a name="sendcalendarsharing"></a>
{: .no_toc }
Default Value: Off

Send notifications on calendar sharing change.

Change Conditions: ??

---

## Document
[Back to Top](#top)

1. [Top Level Folder](#topfolder)
2. [File Extensions/MIME Type Exclude](#fileexeexclude)
3. [File Names Exclude](#filenameexclude)
4. [Filter Date Type](#filterdate)
5. [File Extensions/MIME Type Include](#fileexeinclude)
6. [File Names Include](#filenameinclude)
7. [Overwrite Updated Documents](#overwritedoc)

### Top Level Folder <a name="topfolder"></a>
{: .no_toc }
Default Value: None

Optionally place all folders and files in the specified top level folder. Leave empty to not create an extra top level folder.

Change Conditions: Change to a folder name to migrate all document to that folder on the destination. 

### File Extensions/MIME Type Exclude <a name="fileexeexclude"></a>
{: .no_toc }
Default Value: None

Specify the list of file extensions, one per line in the format '*.ext', that will not be migrated. (*.* for all) or MIME types in the format of 'image/jpeg'

Change Conditions: Set document types not to migated to the destination. 

### File Names Exclude <a name="filenameexclude"></a>
{: .no_toc }
Default Value: None

Specify the list of wildcard patterns for file names, one per line, that will not be migrated.

Change Conditions: Can be used to exclude specific file names to not be migrated. 

### Filter Date Type <a name="filterdate"></a>
{: .no_toc }
Default Value: File Created Date

When 'Migrate Files From' - 'Migrate Files To' ranges are set, filter files based on this selection.

Change Conditions: ??

### File Extensions/MIME Type Include <a name="fileexeinclude"></a>
{: .no_toc }
Default Value: All

Specify the list of file extensions, one per line in the format '*.ext', that will be migrated. (*.* for all) or MIME types in the format of 'image/jpeg'.

Change Conditions: Set document types to migated to the destination, those not specified are excluded. 

### File Names Include <a name="filenameinclude"></a>
{: .no_toc }
Default Value: All

Specify the list of wildcard patterns for file names, one per line, that will be migrated (*.* for all).

Change Conditions: Specify the file types to migrate, others are excluded. 

### Overwrite Updated Documents <a name="overwritedoc"></a>
{: .no_toc }
Default Value: On

Enable delta migrations, where a re-migration will cause any items that have been modified in the source since the last migration to be re-migrated and updated in the destination.

Change Conditions: Turn off you not migrate document with a newer modified date. 

## Email Attachment to Drive

1. [Email Attachment Document Migration](#emailattachdoc)
2. [File Extensions](#fileextens)
3. [Drop Migrated Attachments](#dropmigrateattach)
4. [Oversized Attachments Folder/Label](#oversizeattachfolder)
5. [Email Attachment Document Sharing](#emailattachdocshare)
6. [Add Document Links](#adddoclink)
7. [Minimum Email Attachment Size](#minemailsize)
8. [Migrate all Attachments for Oversized Messages](#migalloversize)

### Email Attachment Document Migration <a name="emailattachdoc"></a>
{: .no_toc }
Default Value: None

Choose to migrate email attachments to Drive.

Change Conditions: Change to migrate email attachments.

### File Extensions <a name="fileextens"></a>
{: .no_toc }
Default Value: All

Specify the list of file extensions, one per line in the format '*.ext', that will be migrated from email attachments (*.* for all).

Change Conditions: ??

### Drop Migrated Attachments <a name="dropmigrateattach"></a>
{: .no_toc }
Default Value: On

If documents are uploaded to Drive for an email message, remove the attachments from the original message.

Change Conditions: Enable to move attachments to a users Drive.

### Oversized Attachments Folder/Label <a name="oversizeattachfolder"></a>
{: .no_toc }
Default Value: None

Specify the name of a folder in which to store oversized email attachments when migrating to Drive.

Change Conditions: Input the name of the folder to be placed on a users Drive and store oversized attachments. 

### Email Attachment Document Sharing <a name="emailattachdocshare"></a>
{: .no_toc }
Default Value: No Sharing

When migrating email attachments or file system files, choose whether the document should be shared with recipients of the original email.

Change Conditions: Set to Share Documents to enable sharing on attachment moved to Drive. Set to Share Documents and Send Notification Email to also send an email to notify sharing was enabled. 

### Add Document Links <a name="adddoclink"></a>
{: .no_toc }
Default Value: On

If documents are uploaded to Drive for an email message, modify that message to include links to the documents.

Change Conditions: Disable to still move attachments to Drive, but not replace with a link. 

### Minimum Email Attachment Size <a name="minemailsize"></a>
{: .no_toc }
Default Value: 20971520

When migrating email attachments to Drive only migrate those greater than the specified size (in bytes) to Drive. Specify 0 to migrate all attachments to Drive.

Change Conditions: Change to O to move all attachment to Drive. 

### Migrate all Attachments for Oversized Messages <a name="migalloversize"></a>
{: .no_toc }
Default Value: Off

When a message is greater than the permitted size, move all attachments to Drive.

Change Conditions: Turn on to move attachments of a greater size speicifed in Minimum Email Attachment Size to Drive. 

## Address Replacement

1. [Replace Usernames](#replaceuser)
2. [Address Replacements (.csv)](#addreplacecsv)
3. [Non-Matched Address Replacement Behaviour <](#nonmatchreplace)
4. [Replace CSV Addresses Only](#replacecsvonly)

### Replace Usernames <a name="replaceuser"></a>
Default Value: On

Replace any remapped usernames from the users page, when migrating the items specified in 'Domain Replacement Types' tab. If this option is disabled and replacements are required, explicit mappings for email addresses and domain names should be provided.

Change Conditions: 

### Address Replacements (.csv) <a name="addreplacecsv"></a>
Default Value: None

Specify a path to a CSV file containing replacement values to modify email addresses for appointments and contacts during migration. To perform no replacements, do not specify a file.

Change Conditions: 

### Non-Matched Address Replacement Behaviour <a name="nonmatchreplace"></a>
Default Value: Retain Original Address

When 'Replace Usernames' is enabled, and a CSV has been provided for address replacement, set the behaviour when an address has not been matched. Either replace the domain name of the address, or leave the original address.

Change Conditions: ??

### Replace CSV Addresses Only <a name="replacecsvonly"></a>
Default Value: Off

Perform email addresses and domain replacements from the CSV file specified in 'Address Replacements' and do not attempt to perform replacements using any other method.

Change Conditions: Turn on to only change address of users specified in the CSV under Address Replacements (.csv)
