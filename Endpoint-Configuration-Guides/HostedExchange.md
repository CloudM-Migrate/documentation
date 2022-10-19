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

### Hosted Exchange
{: .no_toc }
Hosted Exchange CloudM Migrate has preset configurations for the most providers, select the provider and the server along with the authentication details. If the provider is not supported then enter the details manually, but keep in mind need to obtain the Auto discover or Direct EWS URL, and the authentication method.

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

If the  Hosted Exchange provider is listed, select it from the list of providers and the server details will be populated. If the provider is not listed, select 'My Provider is Not Listed' and enter the below details manually.

-	Auto discovery Service URL – In order to connect to the correct server, auto discovery is used to obtain the server information. Input the URL to the auto discovery service for your domain. The value for your Microsoft Exchange server is like https://yourserver/autodiscover/autodiscover.xml.
-	Admin Username – Enter the full email address of your Microsoft Exchange admin user.
-	Admin Password – Enter the password of the admin user.
-	Domain Name – Enter the domain name you will be migrating from. This should be the Internet domain name, not the local domain name.
-	Test User Name – Enter an email address of an active user within your Microsoft Exchange system. This account is used to test connections as in most cases the admin account will not be mailbox enabled.

CloudM Migrate will now perform a small connection test. If this fails validate the information has been entered correctly.

---
### Migrating to Google Workspace Section 
 
When migrating to Google workspace please review the Google Workspace Prerequisites  
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

---

### Migrating to Microsoft 0365 

When migrating Microsoft as the destination Please follow the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">0365 Endpoint Configuration</a>


The following will need to be done first and refer to these steps that should be completed in your Destination environment.
Setting up Application Impersonation can be configured for the admin account within CloudM Migrate. 
Select 'Setup Administrative Permissions' in the Destination Platform Settings page.
<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/HostedExchangeSourceAO.html#">Application Impersonation</a>.

