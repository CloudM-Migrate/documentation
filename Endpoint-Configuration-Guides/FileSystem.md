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

File stored in a local network file share can be migrated to either Google Drive, Microsoft OneDrive or a SharePoint Teams Site. CloudM Migrate will need to be <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/SelfHostedGuides.html">installed</a> on a server in the network. Once completed the server will need to have the desired shares <a href="https://support.microsoft.com/en-us/windows/map-a-network-drive-in-windows-29ce55d1-34e3-a7e2-4801-131475f9557d"> mapped</a> to the CloudM Migrate server. If using a Cluster, each Secondary server will need the drive mappings done the same as the Primary server. 

### Authentication Method

Once all the file shares are mapped as drives the account used to logon to the server(s) will need to have READ access to all files in scope for a migration. 

### Document Options

### Active Directory Options

### Supported Features by Destination

| Feature | Google Drive |	Microsoft OneDrive / SharePoint Team Sites |
| --- | --- | --- |
| Folder Hierarchies and Files | Yes| Yes | 	  	 
| Truncate Oversize Paths | No | Yes |  	  	 
| Rename Illegal File Names | No | Yes | 	  	 
| Preserve File Dates | Yes | Yes | 
| Folder and File ACLs | Yes | Yes | 
| Active Directory Permissions | Yes | Yes | 
| File Type Filters | Yes | Yes |
| Copy Empty Folders 	| Yes | Yes |
| Simultaneous Migrations | Yes | Yes | 
| Provision Destination Account | Yes | Yes|
| Warn on Size Limits | No | Yes | 
| Full Reporting | Yes | Yes | 
