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

### Self-Hosted Install

CloudM Migate will need to be <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/SelfHostedGuides.html">installed</a> on a VM/Server in the source environment. 

### Mapping File Shares 

All source file shares need to be mapped as network drives to the CloudM Migrate server. If using a cluster all Secondary nodes will also need the same drives mapped. 

The file share mappings will need to done using the server/node System account and made persistant. 

Use the following steps to map the drives: 

1. Download the SysInternals tool <a href="https://learn.microsoft.com/en-gb/sysinternals/downloads/psexec">PsExec</a> to the server/node. Extract the zip file to a working directory such as Temp. 
2. Open a Command Prompt as Administrator. 
3. Navigate to the working directory and enter `psexec -i -s cmd.exe`
4. In the new command prompt from PsExec enter `net use e: \\servername\sharedfolder /persistent:yes`
5. Each file share will need to be mapped in turn with the same drive letters used on any additional nodes.

**Note**: The mapped drives will appears as disconnected when viewed from File Explorer. 

### Adding File Shares as Migration Items

The auto discovery function within CloudM Migrate does not work for File Shares so each file share need to be added manually. 

To add a File Share navigate to Step 3 within CloudM Migrate and select **+Add items to migrate**. Select **Add User** and populate the following fields:

- Export Type: User
- Import Type: Team Site 
- Export Name: N/A
- Import Name: Default Site Collection URL
- Given Name \ Item Name: Custom Site Collection URL or OneDrive URL
- Family Nmae: N/A
- Password: N/A
- Document Path: Mapped drive letter with subfolder path if needed

Validate Migrate and Drive are checked and select **Save** to add the migration line item. 
