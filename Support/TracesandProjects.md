---
layout: default
title: Traces and Projects
parent: Support
has_children: false
nav_order: 1
---

## Traces and Proejcts
{: .no_toc }

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

### Sending Traces and Projects to Support

Answers to commons errors, if it's uncommon <a href="https://support.cloudm.io/hc/en-us/requests/new">Contact our 24/7 support team.</a>

To expedite the request please fill out the support ticket with the relevent information about the issue that is occuring. Providing screenshots, trace logs, and configuration files can assist us with providing answers faster. There is not an option to export the configuration from the hosted version of the tool, Support already has access to this information.

**NOTE:**  If using CloudM Migrate SAAS, please open a support ticket via our Help Center and inform support of the destination migration domain.

#### How to Export Configuration File 

To export your Logging and Trace Files:

- Go to the Projects page with in CloudM Migrate. 
- Click the Gear Cog icon in the upper right. 
- Select the Export Configuration icon.


#### How to Locate Traces 

When running a self hosted migration the locatation of a trace logs is the C:\ProgramData\Cloud Technology Solutions folder on the primary server.

### Exceptions 

If migrating from Lotus Notes, GroupWise, Zimbra, Box, Dropbox, PST and Windows File System, select General Migration Settings > Advanced Settings > System > Trace Level to TRACE instead, this will gather additional tracing for those platforms.

### Generating a Debug Level Trace

In order to generate a trace file with full visibility on how the tool is handling data another pass is required please follow the steps on how to set the tool to debug level.  Select Step 4 - **Config Settings** > **Advanced Settings** > **System** and set **Trace Level** to **Debug**  within CloudM Migrate.

### Cluster Logs 

When running CloudM Migrate in a Cluster, different log files are written to a few different locations. The configurable storage location does not apply to clustered migrations, and logs are always written to the following locations:

Migration logs are written to the secondary node on which the migration occurred. To determine which secondary node performed a migration for a user, refer to the progress tab or the CSV report files generated at the end of a migration.

### Primary Node

- User interface logs - C:\ProgramData\Cloud Technology Solutions\CloudMigrator\CloudMigrator.UI.Trace.txt
- User interface logs store information about the user interface and can be used to help troubleshoot any issues with it
- User interface logs are kept on a rolling basis, the latest has no number
- Migration logs - C:\ProgramData\Cloud Technology Solutions\CloudMigrator\CloudMigrator.Trace.txt
- Migration logs contain detailed information about what happened during a migration and can be used to help diagnose issues with user migrations.
- The 10 most recent migration logs are kept, the latest log file is always that without a number
- Service logs - C:\ProgramData\Cloud Technology Solutions\CloudMigrator.Service.Trace.txt
- Service logs provide information about the management of migrations and communication between system components
- Service logs are kept on a rolling basis, the latest has no number.

### Secondary Node 

- Migration logs - C:\ProgramData\Cloud Technology Solutions\CloudMigrator\CloudMigrator.Trace.txt
- Migration logs contain detailed information about what happened during a migration and can be used to help diagnose issues with user migrations.
- The 10 most recent migration logs are kept, the latest log file is always that without a number.
- Service logs - C:\ProgramData\Cloud Technology Solutions\CloudMigrator.Service.Trace.txt.
- Service logs provide information about the management of migrations and communication between system components.
- Service logs are kept on a rolling basis, the latest has no number.
 
