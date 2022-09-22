---
layout: default
title: PST Archive
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 11
---

## PST Archive Endpoint Options

---
This document will give an overview on all the PST Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/PSTSourceAO.html">PST Archive Source Advanced Options</a>

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

### Archive Label <a name="sharepointapi"></a>
Default Value: PST Archive

The label/category that will be applied to migrated PST messages when labelling/categories are enabled.

### PST Special Folder Names
Default Value: Inbox:Inbox;Drafts:Drafts;Sent Items:Sent Items;Deleted Items:Deleted Items;Junk E-Mail:Junk E-Mail;RSS Feeds:RSS Feeds;Calendar:Calendar;Contacts:Contacts;Tasks:Tasks;Notes:Notes;

The display names of the special PST folders.

### Auto-Generate Missing Message IDs 

Auto generate message Ids for messages that have none in PST archives.

### Allow Duplicate Messages 

Allow migration of duplicate messages when they may have been copied to multiple folders.

### Include Folders with missing Container Class 

Include a folder in the Export even if it is missing a Folder Container Class.

### Archive Label Method
Default Value: Orginal Folder Structure and Label/Category

The folder structure and/or label/catogories that will be applied to migrated archive messages.

### Excluded Item Classes

Specify the list of item classes that will not be processed as part of a migration. Exact matches are made on the value specified here.

### PST Encoding

Export_Pst_Econding_Description_Name

### Migrate Drafts 

Allow migration of unsent messages. Some fields, such as Message-ID, To and From may be automatically populated to allow migration to the destination system.



