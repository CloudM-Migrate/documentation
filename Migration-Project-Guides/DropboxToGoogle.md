---
layout: default
title: Dropbox to Google Workspace
grand_parent: Migration Project Guides
parent: Google
nav_order: 5
has_children: false
has_toc: false

---

## Dropbox to Google Workspace
{: .no_toc }

Before starting your migration project, make sure you have setup the <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/Dropbox.html">Dropbox</a> endpoint and the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/Google.html">Google Workspace</a> endpoint using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

The destination for the file share can be a SharePoint personal Google Drive or Shared Drive. 

<a name="top"></a>
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Standard Prestage Migration
{: .no_toc }

There are multiple approaches available to migrating data with CloudM Migrate. The following approach will prestage email older than 30 days as a batch. This will be followed by a Delta Sync to migrate recent data after your DNS cutover for a complete lossless migration. 

This approach eliminates user confusion from recent items being moved as they are created and categorized during normal business. The result will be a more accurate account of recent changes on the destination and less user support. 

CloudM Migrate doesn't duplicate emails or documents. Once an email is migrated it is not moved again or updated on the destination even if it has changed on the source. Documents are not duplicated, but may be <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#overwritedoc">overwritten</a> in delta migrations.

### Adding Users
[Back to Top](#top)

On Step 3 on the left, select **Add items to migrate** for options on how to collect targeted items to migrate from Google. The following options will be available:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource - Add a specific calendar resource to the project.
- Add Shared Drive - Add a Shared Drive to the project.
- Add Group - Add a Google Group to the project.

### Scanning the Source 
[Back to Top](#top)

It's recommended to perform a scan against your Google source environment to proactively look for problems. While in CloudM Migrate select Step 5 on the left and then select Start. Depending on the size of the environment this can take some time to complete. When complete select Export Scan Results to download a zip of the scan results. 

The important files to check are the FileScanReport.html and MailScanReport.html. Users that have items errors are highlighted in red. Important errors to look for are:

- Dead User Objects. Files owned by non-existent accounts. 
- External File Shares. Items CloudM Migrate cannot migrate as they are external to the environment. 

### Domain and Address Replacements 
[Back to Top](#top)

> **Note**: Domains should always be mapped, but address replacements are optional and usually only need to be provided when you have specialist requirements. CloudM Migrate maps usernames and email addresses automatically if they have been configured in the user list however if you need to map unlisted users you can add them to the Address Replacements File.

There are a number of options which control how replacements are performed. It is important to understand how these applied, in which order and under which conditions. It is possible to end up with incorrect email addresses if the options are not fully understood.

**Replace Usernames** – Replace any re-mapped usernames from the users tab, when migrating the items specified in **Domain Replacement Types** in Common settings. If this option is disabled and replacements are required, explicit mappings for email addresses and domain names should be provided via the other settings in this section. Only addresses that belong to source domains are automatically mapped. When migrating from Google Workspace, the source domains are automatically identified, but when migrating from other sources you should specify the domains in the next setting: Address Domain Replacements

**Address Domain Replacements** - If migrating from one domain name to another, specify the domain names that should be replaced and the value with which they should be replaced with. For example, when migrating from example.com to domain.com, you should provide example.com and domain.com in this setting. If migrating from one Google Workspace domain to another, domain replacements are performed automatically unless **Replace CSV Addresses Only** is selected and you have not provided the domain mappings within the file.

**Address Replacements (File)** – Use this option to provide an explicit list of email addresses to be mapped as part of a migration. If performing domain consolidation or if you have other specialized requirements then this option can be used to map any source email address to any other address. Addresses should be mapped using a simple CSV file containing two columns, the first for the address to be replaced and the second the replacement address.

