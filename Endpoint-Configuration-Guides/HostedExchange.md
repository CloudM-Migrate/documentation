---
layout: default
title: Hosted Exchange
grand_parent: Endpoint Configuration Guides
parent: Other Source Endpoints
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

These are CloudM's supported hosted exchange providers:

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

If the Hosted Exchange provider is listed, select it from the list of providers and the server details will be populated. If the provider is not listed, select 
**My Provider is Not Listed** and enter the below details manually.

Select the **Platform** that correspondes to the intended source environment. Consult the hosted providers documentation to determine which one to select which will auto-populate the correct **Exchange URL**.

-	Exchange URL - Pre-populated by selecting the platform. Query the hosted provider for their recommendation. 
-	Admin Username - Enter the full email address of the Microsoft Exchange mailbox with delegated rights.
-	Admin Password - Enter the password of the mailbox with delegated rights.
-	Domain Name - Enter the domain name of the source environment. 
-	Test User Name - Enter an email address of an active user within athe source environment. Pick a mailbox that is within the scope of the migration project. 

Select **Next** and CloudM Migrate will perform a connectivity test. 

If this fails validate the information has been entered correctly.

---

### Delegated Access 

An account will need to be designated as a synthentic admin account by granting delegation rights to all other mailboxes in scope for migration. 

Select **Advanced Settings** and under the **Authentication** section select **Credential Method** and change it to **Delegated Access**.

In the **Admin Username** field enter the account that has been giving delegation rights. 

<a href="https://support.microsoft.com/en-us/office/allow-someone-else-to-manage-your-mail-and-calendar-41c40c04-3bd1-4d22-963a-28eafec25926.html#">Setting up delegated access</a>.

---
### Migrating to Google Workspace 

These steps should be completed in the Destination environment.
 
When migrating to Google workspace review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

To enable Google Vault for the destination, please see the following article <a href="https://support.google.com/vault/answer/2584132?hl=en&ref_topic=2739742">Set up Vault for your organization</a>.

---

### Migrating to Microsoft 0365 

When migrating Microsoft as the destination please follow the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">0365 Endpoint Configuration</a>.

CloudM Migrate will perform a connection test against the destination O365 tenant.

If this fails validate the information has been entered correctly.






