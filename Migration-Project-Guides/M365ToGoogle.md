---
layout: default
title: Microsoft 365 to Google Workspace
grand_parent: Migration Project Guides
parent: Google
nav_order: 2
has_children: false
has_toc: false

---

## Microsoft 365 to Google Workspace
{: .no_toc }

Before starting your migration project, make sure you have setup the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/M365Tenant.html">M365</a> and <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/Google.html">Google Workspace</a> endpoints using the configuration guides. Be sure to validate both endpoints have passed their connectivity tests with no errors. 

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

There are multiple approaches available to migrating data with CloudM Migrate. The following approach will prestage email and documents older than 30 days as a batch. This will be followed by a Delta Sync to migrate recent data after your DNS cutover for a complete lossless migration. 

This approach eliminates user confusion from recent items being moved as they are created and categorized during normal business. The result will be a more accurate account of recent changes on the destination and less user support. 

CloudM Migrate doesn't duplicate emails or documents. Once an email is migrated it is not moved again or updated on the destination even if it has changed on the source. Documents are not duplicated, but may be <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#overwritedoc">overwritten</a> based on either the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#filterdate">Creation Date or Modified Date</a>. 

### Adding Users
[Back to Top](#top)

On Step 3 on the left, select the Add items to migrate for options on how to collect targeted items to migrate from Google. The following options will be available:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource -  
- Add Public Folder
- Add M365 Group
- Add Team Site
- Add Microsoft Team

### Scanning the Source 
[Back to Top](#top)

It's recommended to perform a scan against your M365 source environment to proactively look for problems. While in CloudM Migrate select Step 5 on the left and then select Start. Depending on the size of the environment this can take some time to complete. When complete select Export Scan Results to download a zip of the scan results. 

The important files to check are the FileScanReport.html and MailScanReport.html. Users that have items errors are highlighted in red. Important errors to look for are:

- Path contains too many characters. These can be corrected before the migration or use the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/M365DestinationAO.html#trunfoldfil">Truncate Folders and Files</a> option which is on by default and set the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/M365DestinationAO.html#orphfold">Orphaned Items Folder</a> field to a target folder name.
- Dead User Objects. Files owned by non-existent accounts. 
- External File Shares. Items CloudM Migrate cannot migrate as they are external to the environment. 

### Address Replacement for Different Alias 
[Back to Top](#top)

If there is a need to change the alias on the M365 destination to fit a new naming convention this can be accomplished using the Export items button. This will export the user list to a CSV and you can change the ImportName column value by user to the new alias naming convention. 

Once the CSV has been updated to the new naming convention, re-import it into CloudM Migrate by using Add items to migrate and then selecting Bulk add/import items. This will overwrite the current user list and now show the new alias under the ImportName column. 

If the aliases are changing the CSV will also need to be uploaded to preserve permission mapping. Make a copy of the CSV and remove all columns besides ExportName and ImportName. Go to Step 4 and expand the Advanced Settings. Select the Address Replacement tab and import the CSV to the Address Replacements (.csv) field. 

### Creating the First Batch
[Back to Top](#top)

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

### Moving Attachments to Google Drive
{: .no_toc }

There are <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#email-attachment-to-drive">several features</a> for manipulating attachments while migrations are inflight. This includes removing attachments from the emails and replacing them with Drive links to the former attachments. Migrated documents can also optionally be shared with the recipients of the original email. This can dramatically shrink mailboxes on the destination.

---

## Unsupported Data Types for Migration
[Back to Top](#top)

### O365
{: .no_toc }

- Calendar: Notifications such as invitations, cancellations, etc.
- Mail: Copies of emails which exist in multiple folders will only be migrated once, from the first folder in which they are found. For all other folders, they will be skipped as Already Exists. This may result in whole folders contents not being migrated.
- Mail: Items that do not match folder types such as calendar responses within a mail folder.
- Mail: Custom items that do not inherit from the core system types. These are items which are not true email, calendars, contacts, journals, mail, notes, or tasks.
- Mail: Server-based Distribution Lists.
- Mail: Dynamic Distribution Lists.
- Mail: Non-Delivery Report/Receipt (NDR) or Delivery Status Notification (DSN).
- Mail: Personal Messaging Resource Management (MRM) Tags.
- Mail: Outlook Quick Steps.
- Mail: Color-coding for categories.
- Settings: Client-side rules are not migrated. Client-only rules do not execute until the user who created the rules logs into the Outlook client with the same profile used to create the rule.
- Settings: Server-side rules are not migrate, these include rules created by a user within the Outlook Web App or via the Exchange Admin Center.
- Settings: Linked mailboxes such as described in <a href="https://technet.microsoft.com/en-us/library/bb123524.aspx">Technet</a>. For linked mailboxes, Exchange creates a disabled user account in the local forest that is used as a stand-in for the foreign account. CloudM Migrate can migrate linked mailboxes only if the mailbox is accessible via web access (OWA/EWS).
- Contacts: Pictures that have been added within a Business Card, under Contacts. Note: Pictures are included in the migration for the migration scenarios with high fidelity, e.g., for Exchange to Office 365, and Office 365 to Office 365.
- Settings: Delegation - This is an EWS limitation, the setting cannot be exported.
- Contacts: Contact categories.
- Contacts: Group ACLs.
- OneDrive: Direct/Individual link sharing 
- InfoPath Forms
- RSS feeds
- SharePoint: Creation date gets changed to the "date of migration" date
- SharePoint: Document history
- SharePoint: Version history
- SharePoint: Direct/individual shareable links cannot be migrated to Google Drive. For more information about shareable links see here.
- SharePoint: Site logos and customizations
- SharePoint: Task lists
- SharePoint: Custom tasks
- SharePoint: News feed
- SharePoint: Versioning
- SharePoint: Metadata




