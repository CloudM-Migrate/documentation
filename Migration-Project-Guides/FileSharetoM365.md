---
layout: default
title: File Share to M365
grand_parent: Migration Project Guides
parent: M365
nav_order: 5
has_children: false
has_toc: false

---

## File Share to M365
{: .no_toc }

Before starting your migration project, make sure you have setup the <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/FileSystem.html">File Share</a> endpoint and the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/M365Tenant.html">M365</a> endpoint using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

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
- Export Name: Any value
- Import Name: SharePoint Document Library or OneDrive UPN
- Given Name \ Item Name: N/A 
- Family Name: N/A
- Password: N/A
- Document Path: Mapped drive letter with subfolder path if needed

Validate **Migrate** and **Drive** are checked and select **Save** to add the migration line item. Repeat for each file share in scope for migration. The folder structure entered under Document Path will be perserved on the destination. 

**NOTE**: The destination for the file share can be a SharePoint site collection or a user OneDrive. 

### Execute Migration

When ready to execute select the Paper Airplane on the left and select **Start** to begin the migration. 
