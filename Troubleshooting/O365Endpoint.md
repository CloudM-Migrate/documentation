---
layout: default
title: O365
parent: Troubleshooting
has_children: false
nav_order: 1
---

## O365 Troubleshooting
{: .no_toc }

---
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

### Migration Failed Remote Server Returned an Error 429 

The 429 error is caused by throttling from Microsoft to protect their own system resources. There is no way to work around this throttling short of asking Microsoft to lift it for your tenant.
 
There are two ways that you can try to delay the throttling, divide the submission of your migrations into different batches, and use a different Global Admin account for each batch.

#### Microsoft as Destination example
- Team sites/document libraries
- MS Throttling
- MS Quotas

Microsoft Graph allows you to access data in multiple services, such as Outlook or Azure Active Directory. These services impose their own throttling limits Request type Per app across all tenants

Any 2000 requests per second that affect applications that use Microsoft Graph to access them.

The specific limits described here are subject to change.

the term tenant refers to the Microsoft 365 organization where the application is installed. This tenant can be the same as the one where the application was created in the case of a single-tenant application, or it can be different in the case of a multi-tenant application.

Any request can be evaluated against multiple limits, depending on the scope of the limit (per app across all tenants, per tenant for all apps, per app per tenant, and so on), the request type (GET, POST, PATCH, and so on), and other factors. The first limit to be reached triggers throttling behaviour. In addition to the service specific-limits described in the section, the following global limits apply.

---

### 403 Forbidden Auth Methods Error  

The error indicates there is an issue with modern authentication

Delete the existing app registration in Azure - https://portal.azure.com > App Registrations.

Clear the Office 365 Auth tokens in CloudM - Projects Page

Run the PowerShell script in the following article to create a new app registration - If you have Modern Factor Authentication (MFA) enabled, authenticate using the powershell script.

Enter the new app registration details in step 1. Make sure to upload the new certificate.

Run the connection test again.

---

### Migration Failed The remote server returned an error: (401) Unauthorized

Ask if the admin has full access rights over the users account that is failing and to check credentials.
