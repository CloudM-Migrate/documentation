---
layout: default
title: Box
parent: Endpoint Configuration Guides
nav_order: 18
---

## Box Tenant

### Creating a Box Application for a Client ID and Client Secret Key

1. Log into your Box account as an administrative user for your organization: https://app.box.com/developers/console
2. Navigate to **Dev Console**.
3. Navigate to **My Apps**.
4. Select Create **New App**.
5. Select **Enterprise Integration**.
6. On the **Authentication Method** screen, select **Standard OAuth 2.0 (User Authentication)**.
7. Give your application a name, such as 'CloudM Migration'.
8. In the section OAuth 2.0 Credentials, copy the Client ID and Client Secret values for later use.
9. Update the Redirect URI field with the below URL: https://oauth.pingone.com/ocs/ppm/rest/v1/oauth/oastempcredresponse/
10. Select **Save Changes**. 
