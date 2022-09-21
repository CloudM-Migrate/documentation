---
layout: default
title: Mail Archive
grand_parent: Engineering Reference
parent: Source Options
nav_order: 12
---

## Mail Archive Source Options
{: .no_toc }

---
This document will give an overview on all the Mail Archive Source Options in CloudM Migrate. 

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

### Archive Label Method
Default Value: Specified Label

Select the way to specify the destination label or folder.

### Archive Label

The label/category that will be applied to migrated FileSystemArchive messages when labelling/categories are enabled.

### Mail Archive Format Type

Select the format type

### Special Folder Names
Default Value: Inbox:INBOX;Drafts:Drafts;Sent Items:Sent Items;Trash:Trash;

The names of the special folders. Leave a folder name empty to exclude it from the migration, or if it does not exist.

### Auto Generate Missing Message IDs 

Use automatically generated message IDs for any messages that do not contain a message ID.
