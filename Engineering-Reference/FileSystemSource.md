---
layout: default
title: File System
grand_parent: Engineering Reference
parent: Source Options
nav_order: 16
---

## File System Source Options
{: .no_toc }

---
This document will give an overview on all the File System Source Options in CloudM Migrate. 
       
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
### Migrate Top Level Folder 

Migrate files and folders into a top-level folder named the same as the top level file system folder

### File System Document Sharing

Choose whether the document should be shared as per the source file ACLs if they can be resolved to email addresses (see documentation).

### Excluded Account Permissions

Specify the list of NT account permissions, one per line in the format 'domain\\accountname', that will be ignored when migrating ACLs

### Set Migrating User as Owner 

Change the file owner to the migrating user. This setting also ensures that the file owner from the file system is added as a writer at the destination

### Resolve Email Addresses 

Select whether to resolve email addresses from Active Directory for file system permissions
