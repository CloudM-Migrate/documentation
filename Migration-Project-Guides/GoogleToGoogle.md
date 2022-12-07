---
layout: default
title: Google to Google
grand_parent: Migration Project Guides
parent: Google
nav_order: 1
has_children: false
has_toc: false

---

## Google Workspace to Google Workpsace
{: .no_toc }

Before starting your migration project, make sure you have setup <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">the Google Workspace tenants</a> using the endpoint configuration guide. Be sure to validate both tenants have passed their connectivity tests with no errors. 

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

- Path contains too many characters. These can be corrected before the migration or use the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#trunfoldfil">Truncate Folders and Files</a> option which is on by default and set the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#orphfold">Orphaned Items Folder</a> field to a target folder name.
- Dead User Objects. Files owned by non-existent accounts. 
- External File Shares. Items CloudM Migrate cannot migrate as they are external to the environment. 

### Domain and Address Replacements 
[Back to Top](#top)

> **Note**
Domains should always be mapped, but address replacements are optional and usually only need to be provided when you have specialist requirements. CloudM Migrate maps usernames and email addresses automatically if they have been configured in the user list however if you need to map unlisted users you can add them to the Address Replacements File.

There are a number of options which control how replacements are performed. It is important to understand how these applied, in which order and under which conditions. It is possible to end up with incorrect email addresses if the options are not fully understood.

**Replace Usernames** – Replace any re-mapped usernames from the users tab, when migrating the items specified in **Domain Replacement Types** in Common settings. If this option is disabled and replacements are required, explicit mappings for email addresses and domain names should be provided via the other settings in this section. Only addresses that belong to source domains are automatically mapped. When migrating from Google Workspace, the source domains are automatically identified, but when migrating from other sources you should specify the domains in the next setting: Address Domain Replacements

**Address Domain Replacements** - If migrating from one domain name to another, specify the domain names that should be replaced and the value with which they should be replaced with. For example, when migrating from example.com to domain.com, you should provide example.com and domain.com in this setting. If migrating from one Google Workspace domain to another, domain replacements are performed automatically unless **Replace CSV Addresses Only** is selected and you have not provided the domain mappings within the file.

**Address Replacements (File)** – Use this option to provide an explicit list of email addresses to be mapped as part of a migration. If performing domain consolidation or if you have other specialized requirements then this option can be used to map any source email address to any other address. Addresses should be mapped using a simple CSV file containing two columns, the first for the address to be replaced and the second the replacement address.

### Batching
[Back to Top](#top)

CloudM Migrate allows you to create a batch from your master user list, in a separate configuration. This enables you to quickly segment your user list and streamlines your migration process by running batches of users.

1. Select the users you want in your migration batch.
2. From the menu, select **Create Batch**.
3. Name your Child Configuration.
4. Select your configuration type.
- Disable Migration Items - Use this if you want to modify the migration items for a subset of your users. e,g. Do not migrate Drive.
- Delete Migration Items - Use this if you want to create a subset of users to migrate. e.g. a VIP group of users.
5. Select Create to create the batch, or Create and Edit or create the batch, and be taken to the edit screen for that batch. Batches can be modified from the Projects screen, and work in the same way as normal configuration.

### Date Ranges for the First Batch
[Back to Top](#top)

Select Step 4 and validate the source and destination domains are correct. Change the dates on the right set of columns to be 30 days before the current date. 

### Cutover 
[Back to Top](#top)

Once the first batch is completed a DNS cutover can be scheduled. After a successful and validated cutover the Delta Sync can be started to sync all recent data. 

It's recommended to use the longest stretch of off-peak hours available. This will greatly speed up the Delta Sync as less new mail is inbound and throttling is reduced. 

### Delta Sync
[Back to Top](#top)

Return to Step 4 change the date listed in the right set of columns to a future date - note all calendar events up to the selected date will be migrated. For recurring events the first event in the series must be within the date range selected for the entire series to be migrated.

Start the migration.

### Statistics and Summary
[Back to Top](#top)

After starting the migration, you'll have the option to view progress and export a summary by selecting **Start** and then selecting **View Progress**. Select **More Statistics** to see a complete summary by item type for your current batch. 

To export a report of the migration for record keeping select Projects in the left navigation. Select **Item Progress** and then select the orange User progress link. By selecting the top and right most orange button a file of item success by user can be downloaded.

---

## Google Drive
[Back to Top](#top)

Due to the flexibility of how files and folders can be organized within Google Drive, CloudM Migrate has to perform Google Drive migrations in a specific way to maintain integrity in the destination Drive. CloudM Migrate has been implemented to provide extremely high integrity and fidelity during a Google Drive migration.  All folder structures, included shared folder structures, file locations, item starring and modification dates are preserved during a migration.

There are a few things to be aware of when performing a Google Drive migration:

**Provision all Users and Groups Before Migration**
Provision all of your users and groups before performing a Drive migration. This is required to ensure all sharing and Drive hierarchies are preserved correctly during the migration. 

You should ensure all of your Drive users have Drive enabled in the destination.

Usage of the destination drive during a migration is not recommended. Items may not be moved into place for all users until the full migration for all users has completed. If items are moved around in the destination domain during a migration multiple problems can occur with migration and may cause migration times to increase significantly.

If you are renaming users as part of the migration, you must make sure all import and export names are present and have been updated to the names in the new system.  You should ensure you have provisioned all of your users before migrating your groups. You should not rename groups during a migration. This must be done before the migration begins. If you are migrating Drive items, the tool will warn you before the migration.

**Migrate Items Only From Listed Users**

This option will migrate only Drive files from those users listed on the Users tab. **Migrate All Drive Items** should be also set to true for this setting to work. If you want to migrate items from users other than those being migrated add them to the user tab but do not select them for migration.

**Migrate Items Only from Listed Users** should be used with care and only ever used if you are only migrating a subset of your users. If you are migrating all of your users during a migration, you should not select this option for any part of your migration. If you do use the option, you should ensure that your user list is fully correct before starting the first migration.

**Migrate Contents of Non-Owned Folders**

Migrate files from folders not owned by the migrating users. This usually only needs enabling when some users are not migrated but the Drive items need to be migrated. Folders will always be processed. This option should not be used in conjunction with **Migrate Items Only From Listed Users**.

**Files and Folders May be Migrated for Other Users**

During a migration of the migrating user, files and folders that were shared with the migrating user may be migrated for the owning users, even when they are not being migrated at that time. This is essential to preserve the complex structure of Google Drive. It is possible to disable this action by setting the option **Migrate All Drive Items** to False, but it is highly recommended to use the default behaviour to preserve Drive integrity.

**Files from Outside of the Domain**

Only files owned by users inside your domain are migrated. While it may be possible to migrate files from outside of the domain where the user has edit access, this involves making changes to files outside of the migrating domain which raises many security issues for the external domains and is therefore not enabled.

**Folder Hierarchies from Outside of the Domain**

It is possible to add folders that have been shared with you into your folder hierarchy, and other users could also have done the same thing. If this is a folder from outside of your domain, then the first user to migrate the folder will become the new owner and it will then be treated as belonging to that user. All external ACLs will be removed from the folder but all domain ACLs will be preserved.

**Comments and Revision History**

Comments can be migrated but revision history cannot.

**Deleted Files and Folders**

Deleted files and folders a user owns are not migrated. 

If a user has deleted a file that has been shared with them making the file invisible in their account but have not actually deleted the source file or the sharing rights, then these files will be visible again in the **Shared with me** folder following the migration. This particular case is not handled by CloudM Migrate as its usage is rare, and when encountered increases migration times. Additionally, even though the file may be invisible, the sharing rights as allocated by the sharer still exist.

**Renaming Users and/or Groups**

CloudM Migrate has functionality to allow user or group email addresses to be changed or mapped during a migration. This is achieved via address replacements.

---

## Vanity Domain Switch
[Back to Top](#top)

Google Workspace domain-switch migrations can be performed in the same way as other Google Workspace migrations, however, if the source domain name is being migrated to the destination this adds an additional layer of complexity relating to the domain name registration and CloudM Migrate licensing. This guide explains how to perform such migrations without running into issues. It is very important to plan ahead to minimize downtime during this process, so we recommend this guide is reviewed thoroughly and all steps planned well in advance of a switch-over.

If the source domain name(s) are not being migrated, then the migration can be configured and performed without any extra steps.

Because Google does not allow a domain to be associated with two instances at the same time. This means an initial migration must be performed to users with a temporary domain, then the domain must be deleted at the source and added to the destination before a delta migration is performed.

1. Configure CloudM Migrate to migrate from your source domain to your temporary destination domain.
2. Migrate all historic email and Google Drive data, whatever is applicable.
3. Rename all the migrated source users to another, either a sub-domain or temporary domain.
4. Change the primary domain at the source.
5. Delete the original primary domain from the source per this guide.
6. Add the new domain to the destination instance as a secondary domain.
7. Add that domain to all new migrating destination users as aliases.
8. Update your CloudM Migrate config to migrate from the new primary domain to the temporary destination domain.
9. Run the delta migration for email and Google Drive.
10. Rename the users in the destination from the temporary domain to the new domain.
11. Create a new CloudM MIgrate project/configuration to then migrate contacts, calendars/resources and tasks if applicable.
12. Change the primary domain on the destination.
13. Finally, you may need to perform a cleanup by removing the temporary destination domain/associated aliases. 

> **Note** Changing the primary domain is not available for: Google Workspace Free edition, Google Workspace or Cloud Identity accounts in a trial period, Google Workspace or Cloud Identity accounts that included the purchase of your domain, Google Workspace accounts purchased through Google Domains, Google Workspace Resellers Licensing

CloudM Migrate licenses are assigned to each destination domain. This means that when performing the delta migration, after renaming the accounts, it will require another CloudM Migrate license. If you are running such a migration, you should contact us through your account manager or via sales@cloudm.io and we will be able to provide additional licenses to mitigate this at no extra cost.

---

## Google Groups
[Back to Top](#top)

When using **Get Items from source**, groups will be populated in the userlist along with users, shared drives and calendar resources. When selected for migration, CloudM Migrate will create the Groups in the destination with the specified Import Name. It will add the members and their membership status (member / manager / owner) will be applied. Subsequent migrations will add new members if they are added on the source. Member deletions and changes to member statuses are not applied. Alternatively, objects including Groups can be imported via CSV file.

It's important to check if there are existing groups in the destination Google Workspace instance. Any groups that are listed from the source could potentially have equivalent groups in the destination, so renaming the migrating groups import names in your items list, to create new ones and/or to distinguish them from the destination groups, would be advised. If you are renaming groups import names, these changes will need to be reflected in an address replacements CSV file.

> **Note**
Google Group settings and content are not migrated - only the group itself and its membership

---

## Migration Enhancement Features 
[Back to Top](#top)

CloudM Migrate has several feature to enhance the migration, these can be configure before migrating based on desired results or to fit requirements. 

### Moving Attachments to MyDrive
{: .no_toc }

There are <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.html#email-attachment-to-drive">several features</a> for manipulating attachments while migrations are inflight. This includes removing attachments from the emails and replacing them with MyDrive links to the former attachments. Migrated documents can also optionally be shared with the recipients of the original email. This can dramatically shrink mailboxes on the destination.

---

## Unsupported Data Types for Migration
[Back to Top](#top)

- Calendar: Calendar Reminders
- Mail: Google Categories such as Social, Promotions, Updates, Forums.
- Mail: Google Starred messages are not Flagged in Outlook.
- Mail: Gmail Snoozed emails as limited by the Gmail API.
- Mail: Gmail Scheduled emails are migrated to Office 365, but only as a draft in the All Mail folder, the scheduling is not migrated. 
- Google Keep Notes.
- Google Spaces.
