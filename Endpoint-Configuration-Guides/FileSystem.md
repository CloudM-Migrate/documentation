---
layout: default
title: File System
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 4

---

## File System Endpoint Configuration
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

File stored in a local network file share can be migrated to Google Drive, Microsoft OneDrive or a SharePoint Teams Site. CloudM Migrate will need to be <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/SelfHostedGuides.html">installed</a> on a server in the network. Once completed the server will need to have the desired shares <a href="https://support.microsoft.com/en-us/windows/map-a-network-drive-in-windows-29ce55d1-34e3-a7e2-4801-131475f9557d"> mapped</a> to the CloudM Migrate server. If using a <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/SelfHostedGuides.html#clustering">Cluster</a>, each Secondary server will need the drive mappings done the same as the Primary server. 

### Authentication Method

Once all the file shares are mapped as drives the account used to logon to the server(s) will need to have READ access to all files in scope for a migration. 

### Active Directory Access

The server and account used to access the CloudM Migrate server will need access to Active Directory (AD) to look up the users SMTP address to apply on the destination. If AD access is not available to the account or server then uncheck the option **Resolve Email Addresses** in CloudM Migrate. 

With no AD access a <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#address-replacement">address replacement</a> file will need to be used where column A is domain/username and column B is SMTP address. 

### Document Options

By default CloudM Migrate will have **Migrate Top Level Folder** enabled which will collapse the source folder structure into one top level folder that can be specified under the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#top-level-folder-">Project Advanced Options</a>. Uncheck **Migrate Top Level Folder** to preserve the existing folder structure. 

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


