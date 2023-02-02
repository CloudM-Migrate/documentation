---
layout: default
title: M365
parent: Support
has_children: false
nav_order: 3
---

## M365 Troubleshooting
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


#### Microsoft Throttling and Quotas

Microsoft Graph allows you to access data in multiple services, such as Outlook or Azure Active Directory. These services impose their own throttling limits.

Microsoft limits the Graph API to 2000 requests per second.

The specific limits described here are subject to change.

The term tenant refers to the Microsoft 365 organization where the application is installed. This tenant can be the same as the one where the application was created in the case of a single-tenant application, or it can be different in the case of a multi-tenant application.

Any request can be evaluated against multiple limits, depending on the scope of the limit (per app across all tenants, per tenant for all apps, per app per tenant, and so on), the request type (GET, POST, PATCH, and so on), and other factors. The first limit to be reached triggers throttling behaviour. In addition to the service specific-limits described in the section, the following global limits apply.

Example Error - [2022-10-13 20:09:13.6813] [MailImporter] [Error] [6] [Test@cloudm.com] [] Unexpected exception processing import. Message is: "Destination: Exchange response error. Code: 'ErrorInternalServerError'. Message: 'An internal server error occurred. The operation failed.'. InnerErrorResponseCode: 'ErrorQuotaExceeded' InnerErrorMessageText: 'Cannot save changes made to an item to store.'" cloud.solutions.Migration.ExchangeWS.ExchangeWSImporterException
Destination: Exchange response error. Code: 'ErrorInternalServerError'. Message: 'An internal server error occurred. The operation failed.'. InnerErrorResponseCode: 'ErrorQuotaExceeded' InnerErrorMessageText: 'Cannot save changes made to an item to store.'

This error is tied to the number of messages with Exchange Online which is a limitation of 1 million messages per folder.

<a href="https://learn.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits">Mailbox folder limits</a> 

---

### Common Microsoft Errors

### Migration Failed The remote server returned an error: (401) Unauthorized

Validate that the admin has full access rights over the users are failing and to check the credentials.

---

### 403 Forbidden Auth Methods Error  

The error indicates there is an issue with modern authentication

Delete the existing app registration in Azure - https://portal.azure.com > App Registrations.

Clear the Office 365 Auth tokens in CloudM - Projects Page

If O365 is the source and MFA can not be disabled the Azure Application used to perform migrations can be created with a PowerShell script <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/CreateAzureADApplication.ps1">CreateAzureADApplication.ps1</a> 

Enter the new app registration details in either the source or destination depending on the migration. 

Make sure to upload the new certificate to CloudM Migrate.

Run the connection test again.

---

### Migration Failed Remote Server Returned an Error 429 

The 429 error is caused by throttling from Microsoft to protect their own system resources. There is no way to work around this throttling short of asking Microsoft to lift it for your tenant.
 
There are two ways that you can try to delay the throttling, divide the submission of your migrations into different batches, and use a different Global Admin account for each batch.

