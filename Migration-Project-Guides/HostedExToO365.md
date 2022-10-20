---
layout: default
title: Hosted Exchange to O365
grand_parent: Migration Project Guides
parent: O365
nav_order: 4
has_children: false
has_toc: false

---
## Hosted Exchange to O365
{: .no_toc }

Before starting your migration project, make sure you have setup both <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> endpoints using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

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

## Things to Consider

### Purchasing Licenses for O365

Under Step 5 in CloudM Migrate an option to scan the source can be leveraged to help determine the exact numbers of licenses needed for O365. It's recommended to purchase licenses and provision OneDrive, SharePoint and Archive Mailboxes before migrating. 

### Setting the Domain on the O365 Tenant

For Google to O365 use the target vanity domain when configuring your destination name regardless if it's different from source or not. 

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/setup/add-domain?view=o365-worldwide">Add a domain to Microsoft 365</a>

### Create Users in O365

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/add-users?view=o365-worldwide">Add users and assign licenses at the same time</a>

### Provision OneDrive

<a href="https://learn.microsoft.com/en-us/onedrive/pre-provision-accounts">Pre-provision OneDrive for users in your organization</a>

### Provision O365 Archives  
 
<a href="https://learn.microsoft.com/en-us/microsoft-365/compliance/enable-archive-mailboxes?view=o365-worldwide">Enable archive mailboxes for Microsoft 365</a>

---

## Impact to Users
[Back to Top](#top)

### Options for Communications to Users

Migrations have business impact but good communication with your user base can minimize the impact. 

CloudM Migrate can send an email to the users when their migration is completed but you'll want to prepare your user base before your migration cutover. 

---

## Planning your DNS Cutover
[Back to Top](#top)

### DNS Record TTL Preparation
Lower the TTL value for all mail related DNS records such as MX and SPF. 

- MX - Mail Routing
- SPF - Source IP of mail is allowed to send for the domain. 

---


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
 

