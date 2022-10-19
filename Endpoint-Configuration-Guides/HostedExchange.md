---
layout: default
title: Hosted Exchange
parent: Endpoint Configuration Guides
nav_order: 3
---

## Hosted Exchange Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Hosted Exchange as a source endpoint. 

For Hosted Exchange this is defined by the following requirements:

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

### Hosted Exchange Overview
{: .no_toc }
When selecting Hosted Exchange CloudM Migrate has preset configurations for the most providers, choose the provider and the server along with the authentication details. If the provider is not supported then enter the details manually, but keep in mind need to obtain the Auto discover or Direct EWS URL, and the authentication method.

### Supported Hosted Exchanged Providers

Please make sure that the following prerequisites are complete before continuing onto the CloudM Migrate setup.

Currently supported Hosted Exchange Providers:

-	1&1
-	AppRiver
-	Apptrix
-	Claranet
-	CobWeb
-	Giacom
-	GoDaddy
-	Intermedia
-	MailStreet
-	MailStream
-	MindShift
-	Ozhosting
-	Rackspace
-	RTW Hosting
-	Sherweb
-	SilverSky/SoftLayer
-	Time Warner Cable
-	VAR Dynamics
-	WebCentral

---
### Entering Hosted Exchange Information 

If the Hosted Exchange provider is listed, select it from the list of providers and the server details will be populated. If the provider is not listed, select 'My Provider is Not Listed' and enter the below details manually.

-	Auto discovery Service URL in order to connect to the correct server, auto discovery is used to obtain the server information. 
Input the URL to the auto discovery service for your domain. The value for the Microsoft Exchange server is like https://yourserver/autodiscover/autodiscover.xml.
-	Admin Username  Enter the full email address of the Microsoft Exchange admin user.
-	Admin Password Enter the password of the admin user.
-	Domain Name Enter the domain name that will be migrating from. This should be the Internet domain name, not the local domain name.
-	Test User Name Enter an email address of an active user within Microsoft Exchange system. This account is used to test connections as in most cases the admin account will not be mailbox enabled.

CloudM Migrate will now perform a small connection test. If this fails validate the information has been entered correctly.

---
### Migrating to Google Workspace Section 

These steps should be completed in the Destination environment.
 
When migrating to Google workspace please review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

Select where the data will be migrated and if using Google Workspace for Business or Google Vault select to migrate data directly into Google Vault.

To enable Google Vault for the domain, please see the following article:  <a href="https://support.google.com/vault/bin/answer.py?hl=en&answer=2584132.html"</a>
">Set up Vault for your organization</a>

Enter the user's full email address within the Export Name field. If already created in Google Workspace users then enter their username.

If the provider does not support delegated access or application impersonation, Then enter then user's passwords in the Password field.

To migrate files to a Google Workspace Team Drive, either select the item you wish to migrate and select 'Migrate as Team Drive' from the actions menu or specify the import type as 'TeamDrive' when adding an item. Specify the name or ID of the Team Drive in the 'Given Name' field. If the Team Drive specified doesn't exist then it will be created. Please use a unique ID in the 'Import Name' field to identify the Team Drive across multiple migrations. You can specify a specific folder to migrate from in the 'Documents Path' field, this will migrate only the specified folder and all subfolders.  Make sure  that the migrating account has organizer permissions for any Team Drives that are being migrated.

To improve performance to Team Drives, configure multiple organizers to perform the migration with the configuration setting: Destination Platform Migration Settings > Google Workspace > Team Drive Options > Team Drive Default Organizers

If this fails validate the information has been entered correctly.

---

### Migrating to Microsoft 0365 

When migrating Microsoft as the destination Please follow the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">0365 Endpoint Configuration</a>

CloudM Migrate will perform a connection test against your O365 domain to verify that everything has been entered correctly.

If this fails validate the information has been entered correctly.

The following will need to be done first and refer to these steps that should be completed in the Destination environment.
Setting up Application Impersonation can be configured for the admin account within CloudM Migrate. 
Select 'Setup Administrative Permissions' in the Destination Platform Settings page.
<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/HostedExchangeSourceAO.html#">Application Impersonation</a>.

Click Advanced Settings and under the Account Details section select Credential Method and change it to Delegated Access.

---
  
Office 365 Configuration, Provisioning and Migration Considerations.
  
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
 


---

### Delegated Access Steps

Setting up Delegated Access

Delegated access gives a user account permission to access another. Delegated access must be set up if not utlizing an Enterprise plan of Office 365.

<a href="https://support.microsoft.com/en-us/office/allow-someone-else-to-manage-your-mail-and-calendar-41c40c04-3bd1-4d22-963a-28eafec25926.html#">Setting up delegated access</a>




