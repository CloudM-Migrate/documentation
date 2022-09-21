---
layout: default
title: O365 Platform Configuration and Provisioning 
parent: Engineering Reference
nav_order: 6
---

## O365 Platform Configuration and Provisioning 
{: .no_toc }
---
This document will give an overview on all the Platform Configuration and Provisioning options in CloudM Migrate. The Platform Configuration and Provisioning options allow CloudM to have it's unique flexibility to fit a wide range of requirements. This guide will provide an explination for each so you can decide if it's relavent to your requirements. 

We recommend reviewing these options as they can have a fundamental impact on the success of your project. 

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
### Usage Location
Default Value: United Kingdom

Defines the geographical location of the user who is being assigned an Office 365 license.

Change Conditions: Select the region where the destination tenant will located. 

### License 
Default Value: - CUSTOM SKU INDENTIFIER - 

Defines the license that you want to assign to users using CloudM Migrate.

Change Conditions: Select the license for the destination tenant. 

### SKU identifier

The SKU Code associated with your selected license. Automatically populated but may be overridden.

Change Conditions: 

### Create root public folder mailbox

Creates the root public folder mailbox in Exchange and assigns permissions to it 

Applies to: ExchangeOnline 

### Provision OneDrive for Business for all licensed users

Provisions OneDrive for Business for all licensed users, if the O365 plan includes OneDrive

Applies to: AzureAD, SharePointOnline 

### License and provision OneDrive for Business for all users

Licenses and provisions OneDrive for Business for all users, where licenses are available

Applies to: AzureAD, SharePointOnline 

### License Exchange and Office for all users

Licenses Exchange and Office only, for all users

Applies to: AzureAD 

### Enable Mailbox Archive for all users

Enables Exchange Online archiving for all user mailboxes

Applies to: ExchangeOnline 

### Check user exists and create

Checks whether each user exists and creates that user, if necessary

Applies to: ExchangeOnline, AzureAD 

### Provision OneDrive for Business per user

Provisions OneDrive for Business for each user, if the O365 plan includes OneDrive

Applies to: AzureAD, SharePointOnline 

### License and provision OneDrive for Business per user

Licenses and provisions OneDrive for Business for each user, where licenses are available

Applies to: AzureAD, SharePointOnline

### License Exchange and Office per user

Licenses Exchange and Office only, for each user

Applies to: AzureAD 

### Enable Mailbox Archive per user

Enables Exchange Online archiving for each user

Applies to: ExchangeOnline 

### Deprovision User

Place User on Litigation Hold and Remove Mailbox

Applies to: ExchangeOnline 
