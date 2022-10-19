---
layout: default
title:  Hosted Exchange
parent: Migration Project Guides
nav_order: 4
has_children: false
has_toc: false

---

### Migrating to Google Workspace 

These steps should be completed in the Destination environment.
 
When migrating to Google workspace please review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">**Google Tenant Endpoint Configuration**</a>

Select where the data will be migrated and if using Google Workspace for Business or Google Vault select to migrate data directly into Google Vault.

To enable Google Vault for the domain, please see the following article <a href="https://support.google.com/vault/bin/answer.py?hl=en&answer=2584132.html">**Set up Vault for your organization**</a>

Enter the user's full email address within the Export Name field. If already created in Google Workspace users then enter their username.

If the provider does not support delegated access or application impersonation, Then enter then user's passwords in the Password field.

To migrate files to a Google Workspace Team Drive, either select the item to migrate and select 'Migrate as Team Drive' from the actions menu or specify the import type as 'TeamDrive' when adding an item. Specify the name or ID of the Team Drive in the 'Given Name' field. If the Team Drive specified doesn't exist then it will be created. Please use a unique ID in the 'Import Name' field to identify the Team Drive across multiple migrations. Specify a specific folder to migrate from in the 'Documents Path' field, this will migrate only the specified folder and all subfolders.  Make sure that the migrating account has organizer permissions for any Team Drives that are being migrated.

To improve performance to Team Drives, configure multiple organizers to perform the migration with the configuration setting: Destination Platform Migration Settings > Google Workspace > Team Drive Options > Team Drive Default Organizers

If this fails validate the information has been entered correctly.

---

### Migrating to Microsoft 0365 

When migrating Microsoft as the destination Please follow the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">**0365 Endpoint Configuration**</a>

CloudM Migrate will perform a connection test against the O365 domain to verify that everything has been entered correctly.

If this fails validate the information has been entered correctly.

The following will need to be done first and refer to these steps that should be completed in the Destination environment.
Setting up Application Impersonation can be configured for the admin account within CloudM Migrate. 
Select 'Setup Administrative Permissions' in the Destination Platform Settings page.
<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/HostedExchangeSourceAO.html#">**Application Impersonation**</a>.

Click Advanced Settings and under the Account Details section select Credential Method and change it to Delegated Access.

---

### Office 365 Configuration, Provisioning and Migration Considerations.
  
CloudM Migrate includes a number of platform configuration and provisioning options for Office 365 migration that enable advanced automation scenarios. These options can be executed during the migration process and will run as part of the migration of users' data. 

There are special considerations when you need to preserve the user's domain in the target tenancy. It is not in good practice to have the same domain in two Office 365 tenancies at the same time. The recommended approach to achieve this is detailed below:

All users to be migrated in the source tenancy will have a primary SMTP email address ending in their current domain e.g. 'user@company.com'. 
Check that each of these also has at least one alias. This will be needed later to avoid having to delete users in order to stop mail going to their original mailboxes Provision users mailboxes in the target tenancy with their primary SMTP email addresses based on the '.onmicrosoft.com' domain.
Configure CloudM Migrate with the target domain based on the new tenancy's '.onmicrosoft.com' domain. This will be used for both the bulk migration pass and the delta pass.
  
On completion of the delta pass, all the users should have their current primary SMTP address switched to their alias. This will in-effect stop mail from being received and be the start of the mail 'down-time'.
Remove the 'company.com' domain from all users in the source tenancy. It is essential that no objects remain assigned to this domain otherwise you will not be able to remove the domain from the tenancy.
Remove the 'company.com' domain from the source tenancy.
Add the 'company.com' domain to the target tenancy
Assign the 'company.com' domain to all the users in the target tenancy and make this the primary SMTP email address
This ends the 'mail down-time' as mail will now successfully flow to the users again in the new tenancy.
 

