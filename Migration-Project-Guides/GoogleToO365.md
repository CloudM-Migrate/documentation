---
layout: default
title: Google to O365
parent: Migration Project Guides
nav_order: 1
has_children: True
has_toc: false

---

## Google to O365
{: .no_toc }


Before starting your migration project, make sure you have have setup <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google</a> and <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> using their repective configuration guides. Both have passed their connectivity tests with no errors. 

There are many options for customizing the migration but for the purposes of this guide it's assumed this is a typical full migration. 

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

### Adding Users

On Step 3 on the left, select the Add items to migrate for options on how to collect targeted items to migrate from Google. The following options will be avilable:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource -  
- Add Shared Drive - Add a file share to the project.
- Add Group - 

### Scanning the Source 

It's recommended to perform a scan against your Google source environment to proactively look for problems. While in CloudM Migrate select Step 5 on the left and then select Start. Depeending on the size of the envornment this can take some time to complete. When complete select Export Scan Results to download a zip of the scan results. 

The important files to check are the FileScanReport.html and MailScanReport.html. Users that have items errors are highlighted in red. Important errors to look for are:

- Path Contains too many characters. These can be corrected before the migration or use the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#trunfoldfil">Truncate Folders and Files</a> option which is on by default and set the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#orphfold">Orphaned Items Folder</a> field to a target folder name.
- Dead User Objects. 
- External File Shares. 

### Purchasing Licenses for O365

The scan will also help determine the exact license purchase for O365. It's recommend to purchase licensing and provision OneDrive and SharePoint before migrating. 

### Setting the Domain on the O365 Tenant

For Google to O365 use the target vanity domain when configuring your destination name regardless if it's different from source or not. 

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/setup/add-domain?view=o365-worldwide">Add a domain to Microsoft 365</a>

### Create Users in O365

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/add-users?view=o365-worldwide">Add users and assign licenses at the same time</a>

### Provision OneDrive

<a href="https://learn.microsoft.com/en-us/onedrive/pre-provision-accounts">Pre-provision OneDrive for users in your organization</a>

### Provision O365 Archives  
 
<a href="https://learn.microsoft.com/en-us/microsoft-365/compliance/enable-archive-mailboxes?view=o365-worldwide">Enable archive mailboxes for Microsoft 365</a>

### Address Replacement for Different Alias 

If there is a need to change the alias on the O365 destination to fit a new naming convention this can be accomplished using the Export items function. This will export the user list to a CSV and the ImportName column changed to the new alias naming convention. 

Once the CSV has been updated to the new naming convention, re-import it into CloudM Migrate by using Add items to migrate and then selecting Bulk add/import items. This will overwrite the current user list and now show the new alias under the ImportName column. 

If the aliases are changing the CSV will also need to be uploaded to perserve permission mapping. Make a copy of the CSV and remove all columns besides ExportName and ImportName. Go to Step 4 and expand the Advanced Settings. Select the Address Replacement tab and import the CSV to the Address Replacements (.csv) field. 

## Start Migration

There are multiple approaches available to migrating data with CloudM Migrate. The following approach will prestage email and documents older then 30 days as a  batch. This will be followed by a Delta Sync for recent data after DNS cutover for a complete lossless migration. 

### Creating the first Batch

It's recommended to wait at least 24 hours post-provisioning the destination before you start migrating data. 

Select the Filter option and the select Users and the select create Batch. 

Select all users in scope on Step 3 using the first column header. Select the Migrate column header to enable all users to migrate. Validate all the item types are selected in the right most columns. 

### Date Ranges First Batch

Select Step 4 and validate the source and destination domains are correct. Change the dates on the right set of columns to be 30 days before the current date. 

Select Next, Skip the Environment Scan and Select Start to begin execution against the batch. 

### Cutover 

Once the first batch is completed a DNS cutover can be scheduled. After a successful and validated cutover the Delta Sync can be started to sync all recent data. 

### Delta Sync

Return to Step 4 and change the date ranges on the left set of columns to be same date as the right set of columns. Change the date listed in the right set of columns to one day after your DNS cutover was validated. 

Start the migration.

### Statistics and Summary


