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

When migrating Microsoft as the destination please follow the 0365 Endpoint Configuration.

CloudM Migrate will perform a connection test against the destination O365 tenant.

If this fails validate the information has been entered correctly.

---

### Delegated Access 

An account will need to be designated as a synthentic admin account by granting delegation rights to all other mailboxes in scope for migration.

Select Advanced Settings and under the Authentication section select Credential Method and change it to Delegated Access.

In the Admin Username field enter the account that has been giving delegation rights.

<a href="https://support.microsoft.com/en-us/office/allow-someone-else-to-manage-your-mail-and-calendar-41c40c04-3bd1-4d22-963a-28eafec25926.html#">Setting up delegated access</a>

