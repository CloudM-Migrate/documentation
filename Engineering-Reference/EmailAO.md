---
layout: default
title: Email
parent: Project Advanced Options
grand_parent: Engineering Reference
nav_order: 2
---

## Project Advanced Options Reference

## Email Aadvanced Options

1. [Migration Folders](#migratefolder)
2. [Excluded Folders](#excludefolder)
3. [Exclude Attachment Extensions](#excludeattachexe)
4. [Modified Messages Label](#modifiedlabel)
5. [Message Labels](#messagelabel)
6. [Archive Folder Structure](#archivefolderstruc)
7. [Private Chat Top Level Folder Name](#privatechattop)
8. [Included Folders](#includefolders)
9. [Migrate Attachments](#migrateattach")
10. [Modify Invalid Messages](#modifyinvalid)
11. [Label Modified Messages](#labelmodified)
12. [Migrate Headers Only](#migrateheader)
13. [Archive Folder Structure Name](#archivefolderstruc)


### Migration Folders <a name="migratefolder"></a>
Default Value: All Folders
 
Select the folders to migrate. 

Change Conditions: You want to select specific folders to migrate. 

### Excluded Folders <a name="excludefolder"></a>
Default Value: None

Specify a list of folder names that will be excluded from the migration.

Change Conditions: Some folders are not needed on the destination.

### Exclude Attachment Extensions <a name="excludeattachexe"></a>
Default Value: None

Specify the list of file extensions of attachments that will not be migrated, Leave empty to migrate all attachments.

Change Conditions: Certain file types are not needed on the destination such as a .pdf. 

###  Modified Messages Label <a name="modifiedlabel"></a>
Default Value: Modified

The label/category to use when labeling modified messages if the 'Label Modified Messages' option has been set.

Change Conditions: ??

### Message Labels <a name="messagelabel"></a>
Default Value: None

Apply the specified label or category to all messages. To specify multiple labels, provide a semi-colon delimited list.

Change Conditions: You only want to migration email that contain a specified label. 

### Archive Folder Structure <a name="archivefolderstruc"></a>
Default Value: Off

Archive the entire message folder structure under the folder specified by 'Archive Folder Structure Name'.

Change Conditions: You wish to store all source email into a specific folder on the destination.

### Private Chat Top Level Folder Name <a name="privatechattop"></a>
Default Value: Private Chats

If migrating Teams Private Chats, places all conversations within a folder of the specified name.

Change Conditions: Change the folder name where MS Teams private chats older then 7 days are stored in Outlook. 

### Included Folders <a name="includefolders"></a>
Default Value: None

Specify a list of folder names that will be included with the migration when Migration Folders is set to Specified Only.

Change Conditions: When specifcing to only migrate certain folders, this setting will require the folder you wish to migrate. 

### Migrate Attachments <a name="migrateattach"></a>
Default Value: On

Migrate email attachments to GMail. Note that any email message attachments will always be processed.

Change Conditions: You wish to not migrate email attachments. 

### Modify Invalid Messages <a name="modifyinvalid"></a>
Default Value: On

Attempt to modify messages if they are oversized or have bad attachments before importing to the destination system.

Change Conditions: ??

### Label Modified Messages <a name="labelmodified"></a>
Default Value: Off

Apply a label or category to messages that have been modified as part of the migration process (such as having an oversized attachment removed).

Change Conditions: You want a message labeled if it was modified during migration. 

### Migrate Headers Only <a name="migrateheader"></a>
Default Value: Off

Migrate only message headers from supported systems.

Change Conditions: You only want a retroactive record of sent and received email, all message content is stripped. 

### Archive Folder Structure Name <a name="archivefolderstruc"></a>
Default Value: None

The name of the base folder when using 'Archive Folder Structure'.

Change Conditions: ??


