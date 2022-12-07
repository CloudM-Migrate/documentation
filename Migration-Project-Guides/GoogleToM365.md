---
layout: default
title: Google to M365
grand_parent: Migration Project Guides
parent: O365
nav_order: 1
has_children: false
has_toc: false

---

## Google to M365
{: .no_toc }

Before starting your migration project, make sure you have setup <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google</a> and <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/M365Tenant.html">M365</a> using their respective endpoint configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

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

## Standard Prestage Migration
{: .no_toc }

There are multiple approaches available to migrating data with CloudM Migrate. The following approach will prestage email older than 30 days as a batch. This will be followed by a Delta Sync to migrate recent data after your DNS cutover for a complete lossless migration. 

This approach eliminates user confusion from recent items being moved as they are created and categorized during normal business. The result will be a more accurate account of recent changes on the destination and less user support. 

CloudM Migrate doesn't duplicate emails or documents. Once an email is migrated it is not moved again or updated on the destination even if it has changed on the source. Documents are not duplicated, but maybe <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#overwritedoc">overwritten</a> based on either the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#filterdate">Creation Date or Modified Date</a>. 

### Adding Users
[Back to Top](#top)

On Step 3 on the left, select the Add items to migrate for options on how to collect targeted items to migrate from Google. The following options will be available:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource -  
- Add Shared Drive - Add a file share to the project.
- Add Group - 

### Scanning the Source 
[Back to Top](#top)

It's recommended to perform a scan against your Google source environment to proactively look for problems. While in CloudM Migrate select Step 5 on the left and then select Start. Depending on the size of the environment this can take some time to complete. When complete select Export Scan Results to download a zip of the scan results. 

The important files to check are the FileScanReport.html and MailScanReport.html. Users that have items errors are highlighted in red. Important errors to look for are:

- Path contains too many characters. These can be corrected before the migration or use the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#trunfoldfil">Truncate Folders and Files</a> option which is on by default and set the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#orphfold">Orphaned Items Folder</a> field to a target folder name.
- Dead User Objects. Files owned by non-existent accounts. 
- External File Shares. Items CloudM Migrate cannot migrate as they are external to the environment. 

### Address Replacement for Different Alias 
[Back to Top](#top)

If there is a need to change the alias on the O365 destination to fit a new naming convention this can be accomplished using the Export items button. This will export the user list to a CSV and you can change the ImportName column value by user to the new alias naming convention. 

Once the CSV has been updated to the new naming convention, re-import it into CloudM Migrate by using Add items to migrate and then selecting Bulk add/import items. This will overwrite the current user list and now show the new alias under the ImportName column. 

If the aliases are changing the CSV will also need to be uploaded to preserve permission mapping. Make a copy of the CSV and remove all columns besides ExportName and ImportName. Go to Step 4 and expand the Advanced Settings. Select the Address Replacement tab and import the CSV to the Address Replacements (.csv) field. 

### Creating the First Batch
[Back to Top](#top)

It's recommended to wait at least 24 hours post-provisioning the destination before you start migrating data as replication for the tenant can take some time.  

There are multiple methods for manipulating item lists. For this guide, Select the Filter option and then select Users. Select all users in scope on using the first column header. Validate all the item types are selected in the right most columns. 

Select Create Batch and name the Batch "Prestage". For Batch Configuration Type select disable migration items. 

### Date Ranges for the First Batch
[Back to Top](#top)

Select Step 4 and validate the source and destination domains are correct. Change the dates on the right set of columns to be 30 days before the current date. 

Select Next, Skip the Environment Scan and Select Start to begin execution against the batch. 

### Cutover 
[Back to Top](#top)

Once the first batch is completed a DNS cutover can be scheduled. After a successful and validated cutover the Delta Sync can be started to sync all recent data. 

It's recommended to use the longest stretch of off-peak hours available. This will greatly speed up the Delta Sync as less new mail is inbound and SharePoint throttling is reduced. 

### Delta Sync
[Back to Top](#top)

Return to Step 4 change the date listed in the right set of columns to 50 years in the future. 

Start the migration.

### Statistics and Summary
[Back to Top](#top)

After starting the migration, you'll have the option to view progress and export a summary by selecting Start and then selecting View Progress. Select More Statistics to see a complete summary by item type for your current batch. 

To export a report of the migration for record keeping select Projects in the left navigation. Select Item Progress and then select the orange User progress link. By selection the top and right most orange button a file of item success by user can be downloaded.

---

## Migration Enhancement Features 
[Back to Top](#top)

CloudM Migrate has several feature to enhance the migration, these can be configure before migrating based on desired results or to fit requirements. 

### Moving Attachments to OneDrive
{: .no_toc }

There are <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#email-attachment-to-drive">several features</a> for manipulating attachments while migrations are inflight. This includes removing attachments from the emails and replacing them with OneDrive links to the former attachments. Migrated documents can also optionally be shared with the recipients of the original email. This can dramatically shrink mailboxes on the destination.

---

## Unsupported Data Types for Migration
[Back to Top](#top)

### Google
{: .no_toc }

- Calendar: Calendar Reminders
- Mail: Google Categories such as Social, Promotions or, Updates. 
- Mail: Google Starred messages are not Flagged in Outlook.
- Mail: Gmail Snoozed emails.
- Mail: Gmail Scheduled emails are migrated to Office 365, but only as a draft in the All Mail folder, the scheduling is not migrated. 
- Google Keep Notes.
- Google Spaces.

### O365
{: .no_toc }

- Calendar: Acceptance status for meeting participants such as accepted, declined or tentative. 
- Mail: Email Signatures from Google are not supported in Office 365.
- Mail: Out of Office Notifications. 
