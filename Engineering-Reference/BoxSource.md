---
layout: default
title: Box
grand_parent: Engineering Reference
parent: Source Options
nav_order: 18
---

## Box Source Options
{: .no_toc }

---
This document will give an overview on all the Box Source Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/BoxSourceAO.html">Box Source Advanced Options</a>
         
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
### Client ID

Client Id can be obtained by creating an app in the Box app creation page (see documentation).

### Client Secret

Client secret can be obtained by creating an app in the Box app creation page (see documentation).

### Redirect URI
Default Value: https://cloudm.co/callback

Redirect URI entered in Box API console.

### Admin Email

Admin Email

### Test User Name

The login email address of a non-admin user within the system to test. This user must have the active status in Box.

### Use JWT Authentication

Select whether to enable JWT authentication for access to users and data.

### Authorisation Code

Authorisation Code

### Retry Count
Default Value:10

The number of times an operation will be attempted before failing.

### Timeout
Default Value: 1800000

The timeout that will apply to communications with the Box server.
