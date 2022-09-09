---
layout: default
title: Google Vault
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 6
---

## Google Vault Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Google Vault Source Advanced Options in CloudM Migrate. 

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
## Vault

1. [Polling Interval](#pollingint)
2. [Chat Search Term](#chatterm)
3. [Concurrent Download Limit](#condownlimit)
4. [Preserve Matters On Completion](#perservecomp)
5. [Mail Search Term](#mailterm)
6. [Concurrent Export Limit](#conexport)
7. [Search Timezone](#searchzone)

### Polling Interval <a name="pollingint"></a>
{: .no_toc }
Default Value: 10

The interval in minutes used to poll for the status of an export.

Change Conditions: ??

### Chat Search Term <a name="chatterm"></a>
{: .no_toc }
Default Value: None

Chat search term used to narrow or broaden the export search.

Change Conditions: ??

### Concurrent Download Limit <a name="condownlimit"></a>
{: .no_toc }
Default Value: 10

The number of export archives downloadable at the same time.

Change Conditions: ??

### Preserve Matters On Completion <a name="perservecomp"></a>
{: .no_toc }
Default Value: Off

Preserve the Google Vault Matters created during the export process on migration completion (Success or Failure).

Change Conditions: ??

### Mail Search Term <a name="mailterm"></a>
{: .no_toc }
Default Value: None

Mail search term used to narrow or broaden the export search.

Change Conditions: ??

### Concurrent Export Limit <a name="conexport"></a>
{: .no_toc }
Default Value: 2

The number of exports allowed at the same time.

Change Conditions: ??

### Search Timezone <a name="searchzone"></a>
{: .no_toc }
Default Value: Europe Timezone

The default timezone to use when building export search.

Change Conditions: ??

---
## Mail Archive
[Back to Top](#top)

1. [Archive Label Method](#labelmethod)
2. [Archive Label](#archlabel)

### Archive Label Method <a name="labelmethod"></a>
{: .no_toc }
Default Value: Email Labels (Gmail Archive)

Select the way to specify the destination label or folder.

Change Conditions: ??

### Archive Label <a name="archlabel"></a>
{: .no_toc }
Default Value: Mail Archive

The label/category that will be applied to migrated FileSystemArchive messages when labelling/categories are enabled.

Change Conditions: ??

---
## Email
[Back to Top](#top)

1. [Special Folder Names](#foldname)
2. [Export Spam Emails](#exportspam)
3. [Auto Generate Missing Message IDs ](#autoids)

### Special Folder Names <a name="foldname"></a>
{: .no_toc }
Default Value: INBOX:INBOX;DRAFT:DRAFT;SENT:SENT;TRASH:TRASH;

The names of the special folders. Leave a folder name empty to exclude it from the migration, or if it does not exist.

Change Conditions: ??

### Export Spam Emails <a name="exportspam"></a>
{: .no_toc }
Default Value: Off

Export Spam Emails

Change Conditions: ??

### Auto Generate Missing Message IDs <a name="autoids"></a>
{: .no_toc }
Default Value: On

Use automatically generated message IDs for any messages that do not contain a message ID.

Change Conditions: ??

---
## Chat
[Back to Top](#top)

1. [Migrate Chat History](#chathist)
2. [Migrated Chat Label](#migchatlabel)

### Migrate Chat History <a name="chathist"></a>
{: .no_toc }
Default Value: Off

Migrate chat history.

Change Conditions: ??

### Migrated Chat Label <a name="migchatlabel"></a>
{: .no_toc }
Default Value: Migrated Chats

The label that will be applied to migrated chats.

Change Conditions: ??
