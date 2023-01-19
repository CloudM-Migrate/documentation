---
layout: default
title: On-Premise Exchange
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 9
---

## On-Premise Exchange Endpoint Options
{: .no_toc }

---

This document will give an overview on all the On-Premise Exchange Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/OnPremExchangeSourceAO.html">On-Premise Exchange Source Advanced Options</a>

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
### Exchange Version

Choose the version of Exchange

### Autodiscovery Service URL

The URL for the Exchange Auto Discovery Service to use when resolving addresses to use for the migration. Used if the direct Exchange EWS URL is not present. Should be used in preference to a direct EWS URL where possible.

### Admin Username

The email address of an administrator (for Office 365), or an email or username in the form 'domain\\user name' (for on-premise installations), setup to perform migrations.

### Admin Password

The password for the specified admin account.

### Domain Name

The domain name of the Exchange domain. This should be the internet domain of the Exchange system, not the local domain name.

### Test Username

The email of a non-admin user within the system to test Impersonation or Delegation. Specify a primary SMTP email address or just the part before the '@' symbol and the domain name will be appended. This user must have an active mailbox




