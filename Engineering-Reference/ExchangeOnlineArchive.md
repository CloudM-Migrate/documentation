---
layout: default
title: Exchange Online Archive
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 13
---

## Exchange Online Archive Endpoint Options
{: .no_toc }

---
This document will give an overview on all the Exchange Online Archive Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ExchangeOnlineArchiveAO.html">Exchange Online Archive Source Advanced Options</a>

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
### Authentication Method
Default Value: Modern

Choose the authetication type that will be used with the server. For Office 365 this should be set to 'Modern'.

### Admin Username

The email address of an administrator (for Office 365), or an email or username in the form 'domain\\user name' (for on-premise installations), setup to perform migrations.

### Admin Password

The password for the specified admin account.

### Client ID

Client Id can be obtained by registering an application under 'App registrations' in Azure Active Directory (see documentation).

### Application Password

The pasword for the azure application.

### Domain Name

The domain name of the Exchange domain. This should be the internet domain of the Exchange system, not the local domain name.

### Test Username

The email of a non-admin user within the system to test Impersonation or Delegation. Specify a primary SMTP email address or just the part before the '@' symbol and the domain name will be appended. This user must have an active mailbox.

### PFX Certificate Path

The location of your pfx certificate. Please provide the full path.

### PFX Certificate Password

The pasword for the pfx certificate (leave blank if there is no password).


