---
layout: default
title: Box
parent: Endpoint Configuration Guides
nav_order: 17
---

## Box Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Box as a source endpoint. 

If you are planning a migration the approach matters and prepping your source and destination tenants is fundamental to project success. 

CloudM Migrate will need to have the right settings to successfully connect to both the source and destination and those settings differ by endpoint type. All endpoints require the following basics: 

- An account that can access the data
- The source or destination location of that data
- Environment to SaaS access rights for the transfer
- What region should host the VM used to facilate the migration

For Box this is defined by the following requirements:

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

### Creating a Box Application for a Client ID and Client Secret Key

1. Log into your Box account as an administrative user for your organization: https://app.box.com/developers/console
2. Navigate to **Dev Console**.
3. Navigate to **My Apps**.
4. Select Create **New App**.
5. Select **Enterprise Integration**.
6. On the **Authentication Method** screen, select **Standard OAuth 2.0 (User Authentication)**.
7. Give your application a name such as 'CloudM Migration'.
8. In the section OAuth 2.0 Credentials copy the Client ID and Client Secret Key values.
9. Update the Redirect URI field with the below URL: https://oauth.pingone.com/ocs/ppm/rest/v1/oauth/oastempcredresponse/
10. Select **Save Changes**. 
