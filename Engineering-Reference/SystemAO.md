---
layout: default
title: Advanced Option Reference 
parent: Engineering Reference
nav_order: 1
---

## Advanced Options Reference

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


## System Advanced Settings

### Auto Cancel Period <a name="autocancel"></a>
Default Value: Never
Change Requirements:

Select a time period after which the migration will be automatically be stopped. 

### Validate SSL Certificates <a name="validatessl"></a>
Default Value: On

SSL certificates must keep valid while migrating. Recommended to leave on but can be disabled for testing if needed. 

### Migration Performance Interval <a name="migrateperf"></a>
Defualt Vale: 600

Set the interval used for calculating migration performance metrics in seconds.

### Memory Usage Minimum Available Memory <a name="memoryusemin"></a>
Default Value: 250

Specify the minimum available system memory in MB required to prevent rate limiting.

### Item Export Delay <a name="itemexportdelay"></a>
Default Value: 0

Delay for the specified number of milliseconds after exporting a single item from any source system. Can be used to prevent resource overload on source systems if required.

### Auto Restart Crashed Users <a name="autorestart"></a>
Default Value: Off

If a user migration fails due to a crash, restart the migration. Failures due to none-crash conditions will not be auto-restarted.

### Trace Level <a name="tracelevel"></a>
Default Value: Debug

Specify the trace level of the debug output (from 0 (off) to 5 (debug)).

### Migration History Interval <a name="migratehistory"></a>
Default Value: 30000

Set the interval between aggregating migration history records (milliseconds).

### Memory Usage Check <a name="memuse"></a>
Default Value: Off

Rate limit the migration using available system memory.

### Simultaneous Migrations per Configuration Limit <a name="simmigateper"></a>
Default Value: 0

The number of migrations to run per configuration. Zero turns the setting off. Service level configuration 'Maximum User Migrations' per server will always override this setting.

### Drive Thread Count <a name="drivethread"></a>
Default Value: 3

The number of simultaneous per-user threads when migrating documents. This should not normally be changed.

### Allow Multiple Sources <a name="allowmultiple"></a>
Default Value: Off

Allow the migration of multiple source items, of the same type, to a single destination item.
