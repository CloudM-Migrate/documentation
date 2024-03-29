---
layout: default
title: File Share to M365
grand_parent: Migration Project Guides
parent: Microsoft 365
nav_order: 5
has_children: false
has_toc: false

---

## File Share to M365
{: .no_toc }

Before starting your migration project, make sure you have setup the <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/FileSystem.html">File Share</a> endpoint and the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/M365Tenant.html">M365</a> endpoint using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

The destination for the file share can be a SharePoint document library or a user OneDrive. 

The <a href="https://docs.cloudm.io/Engineering-Reference/M365DestinationAO.html#sharepoint-admin-url-">SharePoint Admin URL</a> needs to be populated on the Destination Advanced Options. 

<a name="top"></a>
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

### Adding File Shares as Migration Items

The auto discovery function within CloudM Migrate does not work for File Shares so each file share need to be added manually. 

To add a File Share navigate to Step 3 within CloudM Migrate and select **+Add items to migrate**. Select **Add User** and populate the following fields:

- Export Type: User
- Import Type: Team Site 
- Export Name: Any value that refers to source such as E:\
- Import Name: SharePoint Document Library (example: sites/site-name) or <a href="https://learn.microsoft.com/en-us/sharepoint/upn-changes">OneDrive UPN</a>
- Given Name \ Item Name: Documents
- Family Name: SharePoint Site Name
- Password: N/A
- Document Path: Full <a href="https://learn.microsoft.com/en-us/dotnet/standard/io/file-path-formats#unc-paths">UNC path</a> on source (example: \\\hostname\rootfolder\subfolder)

Validate **Migrate** and **Drive** are checked and select **Save** to add the migration line item. Repeat for each file share in scope for migration. The folder structure entered under Document Path will be preserved on the destination unless otherwise specified by having <a href="https://docs.cloudm.io/Engineering-Reference/FileSystem.html#migrate-top-level-folder">Migration Top Level Folder</a> checked and <a href="https://docs.cloudm.io/Engineering-Reference/ProjectAdvancedOptions.html#topfolder">target folder</a> specified.

### Execute Migration

When ready to execute select the Paper Airplane on the left and select **Start** to begin the migration. CloudM Migrate will first index the source to validate access to the entire folder structure. Once completed the folder structure is applied to the SharePoint site. Files are then copied into an <a href="https://learn.microsoft.com/en-us/sharepointmigration/sharepoint-online-provided-azure-containers-and-queues-for-spo-migration-api">Azure container</a> before being surfaced in SharePoint. 

### File Name Conflicts

If CloudM Migrate moves a file to the destination that already has a file with the same name the migrating file will be renamed with a _ character in the beggining of the file name. 

If the file was perviously migrated and has been updated on the source, the <a href="https://docs.cloudm.io/Engineering-Reference/ProjectAdvancedOptions.html#overwritedoc">Overwrite Files</a> can be enabled to overwrite based on <a href="https://docs.cloudm.io/Engineering-Reference/ProjectAdvancedOptions.html#filterdate">Created Date or Modified Date</a>. 


