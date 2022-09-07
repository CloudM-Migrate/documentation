---
layout: default
title: Reporting
parent: Project Advanced Options
grand_parent: Engineering Reference 
nav_order: 9
---
## Project Advanced Options Reference

## Reporting Advanced Options

1. [Report Logo Image (.png, .jpeg, .gif, .jpg) ](#reportlogo)
2. [Create Migration Report](#createreport)
3. [Error Reason Modifications](#errormod)
4. [Include Document Mappings in Report](#includedocmap)
5. [Report Title](#reporttitle)
6. [Create User Reports](#userreport)
7. [Record Document Mappings](#docmap)
8. [In Progress CSV Reports](#inprogreport)

### Report Logo Image (.png, .jpeg, .gif, .jpg) <a name="reportlogo"></a>
Default Value: None

Specify the path to an image file which can optionally replace the default one in reports.

Change Conditions: 

### Create Migration Report <a name="createreport"></a>
Default Value: On

Create report(s) when the migration completes. This process can take some time.

Change Conditions: 

### Error Reason Modifications <a name="errormod"></a>
Default Value: ??

Specify replacement values for error messages in user reports.

Change Conditions: ??

### Include Document Mappings in Report <a name="includedocmap"></a>
Default Value: Off

If true, write a CSV file containing recorded document mappings for migrated Drive items.

Change Conditions: 

### Report Title <a name="reporttitle"></a>
Default Value: None

Specify a report title that can be used instead of the default.

Change Conditions: Specify a name for your migration report title. 

### Create User Reports <a name="userreport"></a>
Default Value: Off

Create individual reports for each migrated user. If false, user reports are created as part of the main migration report and if true, as individual documents.

Change Conditions: Turn on for a single file for each user, can be useful for regulatory purposes. 

### Record Document Mappings <a name="docmap"></a>
Default Value: Off

If true, record document mappings for migrated Drive items.

Change Conditions: Recommend to turn on for post migration document mapping report. 

### In Progress CSV Reports  <a name="inprogreport"></a>
Default Value: Off

Write CSV report files as each user migration completes rather than at the end of all migrations.

Change Conditions: ??
