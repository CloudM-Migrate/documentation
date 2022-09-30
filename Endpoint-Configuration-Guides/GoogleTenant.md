---
layout: default
title: Google
parent: Endpoint Configuration Guides
nav_order: 2
---

## Google Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Google as a source or destination endpoint. 

If you are planning a migration the approach matters and prepping your source and destination tenants is fundamental to project success. 

CloudM Migrate will need to have the right settings to successfully connect to both the source and destination and those settings differ by endpoint type. All endpoints require the following basics: 

- An account that can access the data
- The source or destination location of that data
- Environment to SaaS access rights for the transfer
- What region should host the VM used to facilate the migration

For Goolge this is defined by the following requirements:

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

### What Region for the Virtual Machine

Upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the VM. Select the region closest to the desintation. 

### Authentication Method

Google endpoints are accessed by a Super Admin account. 

### Service Account

### Service Account Scopes

### Service Account P12 Access Key

