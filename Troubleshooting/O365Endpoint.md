---
layout: default
title: O365
parent: Troubleshooting
has_children: false
nav_order: 1
---

## O365 Troubleshooting

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
 
There are two ways that you can try to delay the throttling, Divide the submission of your migrations into different batches, and use a different Global Admin account for each batch


Microsoft - 403 Forbidden Auth Methods Error  - The error indicates there is an issue with modern authentication

Delete the existing app registration in Azure - https://portal.azure.com > App Registrations.

Clear the Office 365 Auth tokens in CloudM - Projects Page

Run the PowerShell script in the following article to create a new app registration - If you have Modern Factor Authentication (MFA) enabled, authenticate using the powershell script

Enter the new app registration details in step 1. Make sure to upload the new certificate.

Run the connection test again.

 

### 
 
