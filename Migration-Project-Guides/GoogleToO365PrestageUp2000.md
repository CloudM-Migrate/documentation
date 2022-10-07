---
layout: default
title: Prestage Up to 2000
grand_parent: Migration Project Guides
parent: Google to O365
nav_order: 2
has_children: false

---

## Prestage Up to 2000 Users
{: .no_toc }

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

On Step 3 on the left, select the Add items to migrate for options on how to collect targeted items to migrate from Google. The following options will be available:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource -  
- Add Shared Drive - Add a file share to the project.
- Add Group - 

### Scanning the Source 

It's recommended to perform a scan against your Google source environment to proactively look for problems. While in CloudM Migrate select Step 5 on the left and then select Start. Depending on the size of the environment this can take some time to complete. When complete select Export Scan Results to download a zip of the scan results. 

The important files to check are the FileScanReport.html and MailScanReport.html. Users that have items errors are highlighted in red. Important errors to look for are:

- Path contains too many characters. These can be corrected before the migration or use the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#trunfoldfil">Truncate Folders and Files</a> option which is on by default and set the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#orphfold">Orphaned Items Folder</a> field to a target folder name.
- Dead User Objects. Files owned by non-existent accounts. 
- External File Shares. Items CloudM Migrate cannot migrate as they are external to the environment. 

### Address Replacement for Different Alias 

If there is a need to change the alias on the O365 destination to fit a new naming convention this can be accomplished using the Export items button. This will export the user list to a CSV and you can change the ImportName column value by user to the new alias naming convention. 

Once the CSV has been updated to the new naming convention, re-import it into CloudM Migrate by using Add items to migrate and then selecting Bulk add/import items. This will overwrite the current user list and now show the new alias under the ImportName column. 

If the aliases are changing the CSV will also need to be uploaded to preserve permission mapping. Make a copy of the CSV and remove all columns besides ExportName and ImportName. Go to Step 4 and expand the Advanced Settings. Select the Address Replacement tab and import the CSV to the Address Replacements (.csv) field. 

### Start Migration

There are multiple approaches available to migrating data with CloudM Migrate. The following approach will prestage email and documents older than 30 days as a batch. This will be followed by a Delta Sync for recent data after DNS cutover for a complete lossless migration. 

This approach eliminates user confusion from recent items being moved as they created and categorized. The result will be a more accurate account of recent changes on the destination. CloudM Migrate doesn't duplicate emails or documents. 

Once an email is migrated it is not moved again or updated on the destination even if it has changed on the source. 

Documents are not duplicated, but maybe overwritten based on either the Creation Date or Modified Date. 

### Creating the First Batch

It's recommended to wait at least 24 hours post-provisioning the destination before you start migrating data as replication for the tenant can take some time.  

There are multiple methods for manipulating item lists. For this guide, Select the Filter option, select Users, check box thing and the select create Batch. 

Select all users in scope on Step 3 using the first column header. Validate all the item types are selected in the right most columns. 

### Date Ranges for the First Batch

Select Step 4 and validate the source and destination domains are correct. Change the dates on the right set of columns to be 30 days before the current date. 

Select Next, Skip the Environment Scan and Select Start to begin execution against the batch. 

### Cutover 

Once the first batch is completed a DNS cutover can be scheduled. After a successful and validated cutover the Delta Sync can be started to sync all recent data. 

It's recommended to use the longest stretch of off-peak hours available. This will greatly speed up the Delta Sync as less new mail is inbound and SharePoint throttling is reduced. 

### Delta Sync

Return to Step 4 change the date listed in the right set of columns to 50 years in the future. 

Start the migration.

### Statistics and Summary

After starting the migration, you'll have the option to view progress and export a summary by select Start and then selecting View Progress. Select More Statistics to see a complete summary by item type. 

To export a report of the migration for record keeping select Projects in the left navigation. Select Item Progress and then select the orange User progress link. By selection the top and right most orange button a file of item success by user can be downloaded.
