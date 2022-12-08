---
layout: default
title: File System
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 3

---

## File Share Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure File System as a source endpoint. 

For File System this is defined by the following requirements:

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

### Migrating to Google or M365

File stored in a local network file share can be migrated to Google Drive, Microsoft OneDrive or a SharePoint Teams Site. CloudM Migrate will need to be <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/SelfHostedGuides.html">installed</a> on a server in the network. Once completed the server will need to have the desired shares <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/FileSystem.html#mapping-file-shares"> mapped</a> to the CloudM Migrate server. If using a <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/SelfHostedGuides.html#clustering">Cluster</a>, each Secondary server will need the drive mappings done the same as the Primary server. 

### Authentication Method

Once all the file shares are mapped as drives the account used to logon to the server(s) will need to have READ access to all files in scope for a migration. 

### Active Directory Access

The server and account used to access the CloudM Migrate server will need access to Active Directory (AD) to look up the users SMTP address to apply on the destination. If AD access is not available to the account or server then uncheck the option **Resolve Email Addresses** in CloudM Migrate. 

With no AD access a <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#address-replacement">address replacement</a> file will need to be used where column A is domain/username and column B is UPN address. 

### Document Options

By default CloudM Migrate will have **Migrate Top Level Folder** enabled which will collapse the source folder structure into one top level folder that can be specified under the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#top-level-folder-">Project Advanced Options</a>. Uncheck **Migrate Top Level Folder** to preserve the existing folder structure. 

### Migrating File ACL's

To migrate permissions select either **Shared Documents** or **Shared Documents and Send Notification Email** under the **File System Document Sharing** dropdown. 

### Mapping File Shares 

All source file shares need to be mapped as network drives to the CloudM Migrate server. If using a cluster all Secondary nodes will also need the same drives mapped. 

The file share mappings will need to done using the server/node System account and made persistant. 

Use the following steps to map the drives: 

1. Download the SysInternals tool <a href="https://learn.microsoft.com/en-gb/sysinternals/downloads/psexec">PsExec</a> to the server/node. Extract the zip file to a working directory such as Temp. 
2. Open a Command Prompt as Administrator. 
3. Navigate to the working directory and enter `psexec -i -s cmd.exe`
4. In the new command prompt from PsExec enter `net use e: \\servername\sharedfolder /persistent:yes`
5. Each file share will need to be mapped in turn with the same drive letters used on any additional nodes.

> **Note**: The mapped drives will appears as disconnected when viewed from File Explorer. 

### Supported Features by Destination

| Feature | Google Drive | Microsoft OneDrive / SharePoint Team Sites |
| --- | --- | --- |
| Folder Hierarchies and Files | Yes| Yes |        
| Truncate Oversize Paths | No | Yes |         
| Rename Illegal File Names | No | Yes |       
| Preserve File Dates | Yes | Yes | 
| Folder and File ACLs | Yes | Yes | 
| Active Directory Permissions | Yes | Yes | 
| File Type Filters | Yes | Yes |
| Copy Empty Folders | Yes | Yes |
| Simultaneous Migrations | Yes | Yes | 
| Provision Destination Account | Yes | Yes|
| Warn on Size Limits | No | Yes | 
| Full Reporting | Yes | Yes | 


