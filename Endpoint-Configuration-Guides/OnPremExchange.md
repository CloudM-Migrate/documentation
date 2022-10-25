---
layout: default
title: On-Premesis Exchange
grand_parent: Endpoint Configuration Guides
parent: Other Source Endpoints
nav_order: 9
---

## On-Premesis Exchange Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure On-Premesis Exchange as a source endpoint.

For On-Premesis Exchange this is defined by the following requirements:

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

### What Region for the Virtual Machine

Upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the VM. Select the region closest to the desintation. 

### Exchange Version

CloudM Migrate supports Exchange 2007 to Exchange 2019 however some earlier versions of Exchange don't support all <a href="https://learn.microsoft.com/en-us/exchange/client-developer/exchange-web-services/ews-functionality-in-exchange-product-versions">EWS methods</a> for all item types. 

### Authentication Method

An Exchange Admin account and password will be need to access the source environment. 

### Domain

The domain of the source domain will be needed. If the destination is an O365 tenant that will eventually contain the same vanity domain this will be addresses during the migration project. 

### Test Username

A test mailbox within the migration scope will be needed to test connectivity. 
