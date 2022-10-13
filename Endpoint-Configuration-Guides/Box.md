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

For Box this is defined by the following requirements:

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

---
### Creating a Box application steps 

Client ID

- Client Id can be obtained by creating an app in the Box app creation page (see documentation).

- Client Secret

Client secret can be obtained by creating an app in the Box app creation page (see documentation).

- Redirect URI
Default Value: https://cloudm.co/callback

Redirect URI entered in Box API console.

- Admin Email

Admin Email

- Test User Name

The login email address of a non-admin user within the system to test. This user must have the active status in Box.

- Use JWT Authentication

Select whether to enable JWT authentication for access to users and data.

- Authorisation Code

Authorisation Code

- Retry Count
Default Value:10

The number of times an operation will be attempted before failing.

- Timeout
Default Value: 1800000

The timeout that will apply to communications with the Box server.


