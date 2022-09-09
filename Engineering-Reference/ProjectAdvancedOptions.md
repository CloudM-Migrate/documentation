---
layout: default
title: Project Advanced Options
parent: Engineering Reference
has_children: true
nav_order: 4
---
## Overview 

This document will give an overview on all the project advanced options in CloudM Migrate. The project advanced options allow CloudM to have it's unique flexibility to fit a wide range of requirements. This guide will provide an explination for each so you can decide if it's relavent to your requirements. 

We recommend reviewing these options as they can have a fundamental impact on the success of your project. 

## Project Advanced Options 

1. [System](#system)
2. [email](#email)
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

## System Advanced Settings <a name="system"></a>

### Auto Cancel Period 
Default Value: Never

Select a time period after which the migration will be automatically be stopped. 

Change Conditions: You want the migration to end in a specified period of time. 

### Validate SSL Certificates <a name="validatessl"></a>
Default Value: On

SSL certificates must keep valid while migrating. Recommended to leave on but can be disabled for testing if needed. 

Change Conditions: SSL Certification checking disabled to test a migration. It's not recommended to disable. 

### Migration Performance Interval <a name="migrateperf"></a>
Default Value: 600

Set the interval used for calculating migration performance metrics in seconds.

Change Conditions: Increase or decrease the performance data fidelity.

### Memory Usage Minimum Available Memory <a name="memoryusemin"></a>
Default Value: 250

Specify the minimum available system memory in MB required to prevent rate limiting.

Change Conditions: ??

### Item Export Delay <a name="itemexportdelay"></a>
Default Value: 0

Delay for the specified number of milliseconds after exporting a single item from any source system. Can be used to prevent resource overload on source systems if required.

Change Conditions: Ease performance of source server. 

### Auto Restart Crashed Users <a name="autorestart"></a>
Default Value: Off

If a user migration fails due to a crash, restart the migration. Failures due to none-crash conditions will not be auto-restarted.

Change Conditions: ??

### Trace Level <a name="tracelevel"></a>
Default Value: Debug

Specify the trace level of the debug output (from 0 (off) to 5 (debug)).

Change Condition: Recommend to keep at 5 for troubleshooting and required for regulatory compliance.

### Migration History Interval <a name="migratehistory"></a>
Default Value: 30000

Set the interval between aggregating migration history records in milliseconds.

Change Conditions: ??

### Memory Usage Check <a name="memuse"></a>
Default Value: Off

Rate limit the migration using available system memory.

Change Conditions: ??

### Simultaneous Migrations per Configuration Limit <a name="simmigateper"></a>
Default Value: 0

The number of migrations to run per configuration. Zero turns the setting off. Service level configuration 'Maximum User Migrations' per server will always override this setting.

Change Conditions: ??

### Drive Thread Count <a name="drivethread"></a>
Default Value: 3

The number of simultaneous per-user threads when migrating documents. 

Change Conditions: Decrease or Increase depending of source server load. This normally should not be changed.

### Allow Multiple Sources <a name="allowmultiple"></a>
Default Value: Off

Allow the migration of multiple source items, of the same type, to a single destination item.

Change Conditions: ??

## Email <a name="email"></a>
