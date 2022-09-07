---
layout: default
title: Document
parent: Project Advanced Options
grand_parent: Engineering Reference 
nav_order: 5
---

## Project Advanced Options Reference

## Document Aadvanced Options

1. [Top Level Folder](#topfolder)
2. [File Extensions/MIME Type Exclude](#fileexeexclude)
3. [File Names Exclude](#filenameexclude)
4. [Filter Date Type](#filterdate)
5. [File Extensions/MIME Type Include](#fileexeinclude)
6. [File Names Include](#filenameinclude)
7. [Overwrite Updated Documents](#overwritedoc)

### Top Level Folder <a name="topfolder"></a>
Default Value: None

Optionally place all folders and files in the specified top level folder. Leave empty to not create an extra top level folder.

Change Conditions: Change to a folder name to migrate all document to that folder on the destination. 

### File Extensions/MIME Type Exclude <a name="fileexeexclude"></a>
Default Value: None

Specify the list of file extensions, one per line in the format '*.ext', that will not be migrated. (*.* for all) or MIME types in the format of 'image/jpeg'

Change Conditions: Set document types not to migated to the destination. 

### File Names Exclude <a name="filenameexclude"></a>
Default Value: None

Specify the list of wildcard patterns for file names, one per line, that will not be migrated.

Change Conditions: Can be used to exclude specific file names to not be migrated. 

### Filter Date Type <a name="filterdate"></a>
Default Value: File Created Date

When 'Migrate Files From' - 'Migrate Files To' ranges are set, filter files based on this selection.

Change Conditions: ??

### File Extensions/MIME Type Include <a name="fileexeinclude"></a>
Default Value: *.*

Specify the list of file extensions, one per line in the format '*.ext', that will be migrated. (*.* for all) or MIME types in the format of 'image/jpeg'.

Change Conditions: Set document types to migated to the destination, those not specified are excluded. 

### File Names Include <a name="filenameinclude"></a>
Default Value: *.*

Specify the list of wildcard patterns for file names, one per line, that will be migrated (*.* for all).

Change Conditions: Specify the file types to migrate, others are excluded. 

### Overwrite Updated Documents <a name="overwritedoc"></a>
Default Value: On

Enable delta migrations, where a re-migration will cause any items that have been modified in the source since the last migration to be re-migrated and updated in the destination.

Change Conditions: Turn off you not migrate document with a newer modified date. 

