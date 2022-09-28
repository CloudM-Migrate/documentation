---
layout: default
title: Office 365
parent: Endpoint Configuration Guides
nav_order: 1
---

## Office 365 Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Office 365 as a source or destination endpoint. 

If you are planning a migration the approach matters and prepping your source and destination tenants is fundamental to project success. 

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

CloudM Migrate will need to have the right settings to successfully connect to both the source and destination and those settings differ by endpoint type. All tenants require the following basics: 

- An account that can access the data
- The source or destination location of that data
- SaaS to SaaS access rights for the transfer

For O365 this is defined by the following requirements:

- The Authenticaton Method
- The Account Used
- The O365 Tenant ID
- A Test Acount
- The SaaS to SaaS Access

### The Authentication Method

ClouldM Migrate uses Modern Authentication as a default. If Multi-Factor Authentication is enabled on the endpoint it'll need to be disabled temporarily or a PFX certificate has to be generated for access. 

### The Account Used

In most instances of using Exchange/O365 as a endpoint a Global Admin account is the widest and easist way to provide CloudM Migrate access to everything it needs. However that account is not always availble to use. In order of ease of use here are the available access methods: 

1. Global Admin Account
2. Exchange Admin Account
3. Receiptant Admin Account
4. An Account with impresenation access to all accounts in scope of the migration

#### Global Admin Account

### The O365 Tenant ID

### A Test Acount

### The SaaS to SaaS Access
