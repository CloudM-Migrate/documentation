---
layout: default
title: Email Attachment to Drive
parent: Project Advanced Options
grand_parent: Engineering Reference 
nav_order: 6
---

## Project Advanced Options Reference

## Email Attachment to Drive Advanced Options

1. [Email Attachment Document Migration](#emailattachdoc)
2. [File Extensions ](#fileextens)
3. [Drop Migrated Attachments](#dropmigrateattach)
4. [Oversized Attachments Folder/Label](#oversizeattachfolder)
5. [Email Attachment Document Sharing](#emailattachdocshare)
6. [Add Document Links](#adddoclink)
7. [Minimum Email Attachment Size](#minemailsize)
8. [Migrate all Attachments for Oversized Messages](#migalloversize)

### Email Attachment Document Migration <a name="emailattachdoc"></a>
Default Value: None

Choose to migrate email attachments to Drive.

Change Conditions: Change to migrate email attachments.

### File Extensions <a name="fileextens"></a>
Default Value: All

Specify the list of file extensions, one per line in the format '*.ext', that will be migrated from email attachments (*.* for all).

Change Conditions: 

### Drop Migrated Attachments <a name="dropmigrateattach"></a>
Default Value: On

If documents are uploaded to Drive for an email message, remove the attachments from the original message.

Change Conditions: Enable to move attachments to a users Drive.

The email will be modified to include a link to the former attachments location in Drive.

### Oversized Attachments Folder/Label <a name="oversizeattachfolder"></a>
Default Value: None

Specify the name of a folder in which to store oversized email attachments when migrating to Drive.

Change Conditions: Input the name of the folder to be placed on a users Drive and store oversized attachments. 

### Email Attachment Document Sharing <a name="emailattachdocshare"></a>
Default Value: No Sharing

When migrating email attachments or file system files, choose whether the document should be shared with recipients of the original email.

Change Conditions: Set to Share Documents to enable sharing on attachment moved to OneDrive. Set to Share Documents and Send Notification Email to also send an email to notify sharing was enabled. 

### Add Document Links <a name="adddoclink"></a>
Default Value: On

If documents are uploaded to Drive for an email message, modify that message to include links to the documents.

Change Conditions: Disable to still move attachments to Onedrive, but not replace with a link. 

### Minimum Email Attachment Size <a name="minemailsize"></a>
Default Value: 20971520

When migrating email attachments to Drive only migrate those greater than the specified size (in bytes) to Drive. Specify 0 to migrate all attachments to Drive.

Change Conditions: Change to O to move all attachment to Drive. 

### Migrate all Attachments for Oversized Messages <a name="migalloversize"></a>
Default Value: Off

When a message is greater than the permitted size, move all attachments to Drive.

Change Conditions: Turn on to move attachments of a greater size speicifed in Minimum Email Attachment Size to Drive. 
