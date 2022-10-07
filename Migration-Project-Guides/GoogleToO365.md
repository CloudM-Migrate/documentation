---
layout: default
title: Google to O365
parent: Migration Project Guides
nav_order: 1
has_children: True
has_toc: True

---

## Google to O365
{: .no_toc }

Before starting your migration project, make sure you have have setup <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google</a> and <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> using their repective configuration guides. Both have passed their connectivity tests with no errors. 

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

## Things to Consider

### Purchasing Licenses for O365

Under Step 5 in CloudM Migrate an option to scan the source can be leveraged to help determine the exact numbers of licenses needed for O365. It's recommended to purchase licenses and provision OneDrive, SharePoint and Archive Mailboxes before migrating. 

### Setting the Domain on the O365 Tenant

For Google to O365 use the target vanity domain when configuring your destination name regardless if it's different from source or not. 

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/setup/add-domain?view=o365-worldwide">Add a domain to Microsoft 365</a>

Now is a good time to lower the TTL value for all mail related DNS records such as MX and SPF. 

### Create Users in O365

<a href="https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/add-users?view=o365-worldwide">Add users and assign licenses at the same time</a>

### Provision OneDrive

<a href="https://learn.microsoft.com/en-us/onedrive/pre-provision-accounts">Pre-provision OneDrive for users in your organization</a>

### Provision O365 Archives  
 
<a href="https://learn.microsoft.com/en-us/microsoft-365/compliance/enable-archive-mailboxes?view=o365-worldwide">Enable archive mailboxes for Microsoft 365</a>

---

## Impact to Users

### A

---

## Planning your DNS Cutover

### B

---

## Migration Approaches
