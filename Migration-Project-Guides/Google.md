---
layout: default
title: Google Workspace
parent: Migration Project Guides
nav_order: 2
has_children: true
has_toc: false

---

## Google Workspace Destination Guides
{: .no_toc }

Getting ready to Migrate? Find the guide for your source and destination. 

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

### Licensing and Provisioning for Google Workspace

Under Step 5 in CloudM Migrate an option to scan the source can be leveraged to help determine the exact numbers of licenses needed for Google Workspace. It's recommended to purchase licenses and provision users before migrating. 

### Create Users in Google Workspace

<a href="https://support.google.com/a/answer/179832?hl=en">Adding users and licenses</a>

### Domains

CloudM Migrate must be licensed for a valid destination domain name. This can be the primary or a secondary Google Workspace domain, and you can migrare to objects in multiple domains in an organization using the same licence.

---

## Scanning the Source Environment Endpoint

Environment Scan allows you to plan and prepare your migration by performing analysis of your source file and mail environment. This will return important information such as item counts, data volume, permissions, and folder depth. This can be performed after a connectivty test passes for the source under Step 5 in the CloudM Migrate project.

The reports produced can be exported and analysed to address any potential issues before any migration begins.

> **NOTE** - To run an environment scan, you will first need to have purchased a CloudM Migrate license, issued for the correct destination domain.

---

## Throttling, Quotas and Performance 
[Back to Top](#top)

CloudM Migrate uses Google Workspace APIs to perform migrations. These means that the standard <a href="https://support.google.com/a/answer/1071518?hl=en">Gmail bandwidth limits</a> do not apply for migrations with CloudM, but each API does have quotas and usage limits which can affect performance:

<a href="https://developers.google.com/gmail/api/reference/quota">Gmail API</a>

<a href="https://developers.google.com/drive/api/guides/limits">Drive API</a> 

Many of these limits are on a per-user basis. This means that migrating one user (if the rate is limited for that user) can often take as long as migrating ten users. Therefore the way to get the best migration performance is to migrate as many users simultaneously as possible.

---

## Impact to Users
[Back to Top](#top)

### Options for Communications to Users

Migrations have business impact but good communication with your user base can minimize the impact. 

CloudM Migrate can send an email to the users when their migration is completed but you'll want to prepare your user base before your migration cutover. 

We also recommend preparing your support team for questions on new mail clients and where their data is located after cutover. 

---

## Planning your DNS Cutover
[Back to Top](#top)

### DNS Record TTL Preparation
Lower the TTL value for all mail related DNS records such as MX and SPF. 

- MX - Mail Routing
- SPF - Source IP of mailserver domain that's used to prevent domain spoofing. 

---

## Migrate Reporting and Statistics 
[Back to Top](#top)

If you need a summary record of the migration after completion a select the link **Download Migration Summary Report** at the top of the Project page. 

For a report by datatype with the total number of completed and failed items can be found under the **Download Project Level Report** link. 
