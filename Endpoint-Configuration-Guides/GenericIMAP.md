---
layout: default
title: IMAP
grand_parent: Endpoint Configuration Guides
parent: Other Source Endpoints
nav_order: 8
---

## IMAP Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Office 365 as a source or destination endpoint. 

For IMAP this is defined by the following requirements:

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

### IMAP Overview

Select the credentials (username and password) of the administrator account within the IMAP environment. 
When migrating from Gmail to IMAP select less secure apps in order to gain access.

---

### Supported IMAP Providers
These are CloudM’s Supported IMAP Providers 

Following these prerequisites steps are required before continuing onto the CloudM Migrate setup.

-	Bluehost
-	Dovecot Email Server
-	MDaemon
-	Zoho Mail
-	Amazon Work Mail
-	HCL (IBM) Verse
-	Fasthosts
-	Ionos
-	Scalahosting
-	Hostinger
-	Dreamhost

---

### Migrating to Google Workspace

These steps should be completed in the Destination environment.

When migrating to Google workspace review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

Select the user's full email address within the Export Name field. If already created in Google Workspace users then select their username.
If the provider does not support delegated access or application impersonation, Then select then user's passwords in the Password field.
If this fails validate the information has been entered correctly.

---

### Migrating to Microsoft 0365 Section

For Microsoft as the destination refer to to the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">0365 Tenant Endpoint Configuration</a>

Select the users full email address within the Export Name field. If this has already been created please use the Office 365 users you will need to select their username.

If this fails validate the information has been entered correctly.

---

### Delegated Access 

Delegated access gives a user account permission to access another. Delegated access must be set up if not utilizing an Enterprise plan of Office 365. 

Select Advanced Settings and under the Account Details section select Credential Method and change it to Delegated Access.

<a href="https://support.microsoft.com/en-us/office/allow-someone-else-to-manage-your-mail-and-calendar-41c40c04-3bd1-4d22-963a-28eafec25926.html#">Setting up delegated access</a>

---
  
### Office 365 Configuration, Provisioning and Migration Considerations
  
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
