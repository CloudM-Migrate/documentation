---
layout: default
title: Hosted Exchange to Google
grand_parent: Migration Project Guides
parent: Google
nav_order: 5
has_children: false
has_toc: false

---

## Hosted Exchange to Google
{: .no_toc }

Before starting your migration project, make sure you have setup the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">Hosted Exchange</a> endpoint and the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Configuration Guide</a>. Be sure to validate the tenant and the hosted environment have passed the connectivity tests with no errors. 

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

### Migrating to Google Workspace 

These steps should be completed in the Destination environment.
 
When migrating to Google workspace please review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

Select where the data will be migrated and if using Google Workspace for Business or Google Vault select to migrate data directly into Google Vault.

To enable Google Vault for the domain, please see the following article <a href="https://support.google.com/vault/bin/answer.py?hl=en&answer=2584132.html">Set up Vault for your organization</a>

Enter the user's full email address within the Export Name field. If already created in Google Workspace users then enter their username.

If the provider does not support delegated access or application impersonation, Then enter then user's passwords in the Password field.

To migrate files to a Google Workspace Team Drive, either select the item to migrate and select 'Migrate as Team Drive' from the actions menu or specify the import type as 'TeamDrive' when adding an item. Specify the name or ID of the Team Drive in the 'Given Name' field. If the Team Drive specified doesn't exist then it will be created. Please use a unique ID in the 'Import Name' field to identify the Team Drive across multiple migrations. Specify a specific folder to migrate from in the 'Documents Path' field, this will migrate only the specified folder and all subfolders.  Make sure that the migrating account has organizer permissions for any Team Drives that are being migrated.

To improve performance to Team Drives, configure multiple organizers to perform the migration with the configuration setting: Destination Platform Migration Settings > Google Workspace > Team Drive Options > Team Drive Default Organizers

If this fails validate the information has been entered correctly.
