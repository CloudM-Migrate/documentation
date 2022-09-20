---
layout: default
title: O365
grand_parent: Engineering Reference
parent: Source Options
nav_order: 2
---

## O365 Source Options
{: .no_toc }

---

This document will give an overview on all the O365 Source Options in CloudM Migrate. 

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
### Office 365 Plan <a name="off365plan"></a>
Default Value: Office 365

Office 365 Germany is a differentiated option to the Office 365 services already available across Europe. It helps address the needs of the most regulated customers in Germany.

### Authentication Method <a name="sharepointadmin"></a>
Default Value: Modern

Choose the authetication type that will be used with the server. For Office 365 this should be set to 'Modern'.

### Admin Username <a name="sharepointadmin"></a>

The email address of an administrator (for Office 365), or an email or username in the form 'domain\\user name' (for on-premise installations), setup to perform migrations.

### Admin Password <a name="sharepointadmin"></a>

The password for the specified admin account.

### Client ID <a name="sharepointadmin"></a>

Client Id can be obtained by registering an application under 'App registrations' in Azure Active Directory (see documentation)

### Application Password <a name="sharepointadmin"></a>

The pasword for the azure application.

### Domain Name <a name="sharepointadmin"></a>

The domain name of the Exchange domain. This should be the internet domain of the Exchange system, not the local domain name.

### Test Username <a name="sharepointadmin"></a>

The email of a non-admin user within the system to test Impersonation or Delegation. Specify a primary SMTP email address or just the part before the '@' symbol and the domain name will be appended. This user must have an active mailbox.

### PFX Certificate Path <a name="sharepointadmin"></a>

The location of your pfx certificate. Please provide the full path.

### PFX Certificate Password <a name="sharepointadmin"></a>

The pasword for the pfx certificate (leave blank if there is no password).
