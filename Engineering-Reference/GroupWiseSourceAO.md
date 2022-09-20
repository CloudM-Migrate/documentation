---
layout: default
title: GroupWise
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 7
---

## GroupWise Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the GroupWise Source Advanced Options in CloudM Migrate. 

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
## Server Details

1. [Server Port](#serverport)
2. [GroupWise 2014+ Admin Port](#groupwiseadmin)

### Server Port <a name="serverport"></a>
{: .no_toc }
Default Value: 1677

The GroupWise server port. This is the same port as the GroupWise client normally uses and is usually 1677.

Change Conditions: Your source uses a custom port. 

### GroupWise 2014+ Admin Port <a name="groupwiseadmin"></a>
{: .no_toc }
Default Value: 9710

The port the GroupWise 2014+ Admin service is running on, normally 9710.

Change Conditions: Your source uses a custom port. 

---
## Email
[Back to Top](#top)

1. [Category Labels](#catlabel)
2. [Use Expanded Recipients](#expandreci)
2. [Plain Text Only](#plaintext)
2. [Server MIME Generation](#servermime)

### Category Labels <a name="catlabel"></a>
{: .no_toc }
Default Value: Off

Apply category labels or categories to migrated messages in both accounts and archives (GroupWise 8 or higher only).

Change Conditions:

### Use Expanded Recipients <a name="expandreci"></a>
{: .no_toc }
Default Value: On

Use expanded recipients when resolving email recipients. Only turn off when directed by support.

Change Conditions:
### Plain Text Only <a name="plaintext"></a>
{: .no_toc }
Default Value: Off

Use only the plain text body when migrating internal GroupWise emails. Note that emails recieved from outside of the GroupWise system are migrated as normal.

Change Conditions:
### Server MIME Generation <a name="servermime"></a>
{: .no_toc }
Default Value: Off

Generate MIME messages on the GroupWise server rather than on the client.

Change Conditions:

---
## Contact
[Back to Top](#top)

1. [Address Book Processing](#addybook)
2. [Contact Extraction Language](#conextra)
3. [Excluded Sync Addresses](#excludsync)
4. [System Address Book Sync Type](#sysaddbook)
5. [Incoming Shared Address Books](#insharebook)
6. [Excluded Frequent Contact Addresses](#excludefreq)
5. [Migrate All Group Members](#migallgroup)

### Address Book Processing <a name="addybook"></a>
{: .no_toc }
Default Value: Personal and Frequent

Choose the combination of address books to migrate.

Change Conditions: ??

### Contact Extraction Language <a name="conextra"></a>
{: .no_toc }
Default Value: English

Specify the language that will be used to extract some information from GroupWise.

Change Conditions: ??

### Excluded Sync Addresses <a name="excludsync"></a>
{: .no_toc }
Default Value: Off

Specify a list of addresses that will be excluded from the GroupWise global address book sync.

Change Conditions: ??

### System Address Book Sync Type <a name="sysaddbook"></a>
{: .no_toc }
Default Value: Domain Profile and Shared Contracts

Select to sync the GroupWise System Address Book with Domain Profiles, Shared Contacts, or both.

Change Conditions: ??

### Incoming Shared Address Books <a name="insharebook"></a>
{: .no_toc }
Default Value: On

Choose whether to migrate incoming shared address books (GroupWise 8 only, for earlier versions this setting is ignored and incoming shared address books are always migrated).

Change Conditions: ??

### Excluded Frequent Contact Addresses <a name="excludefreq"></a>
{: .no_toc }
Default Value: None

Generate MIME messages on the GroupWise server rather than on the client.

Change Conditions: ??

### Migrate All Group Members <a name="migallgroup"></a>
{: .no_toc }
Default Value: On

Migrate all members of distribution lists from the selected address books, regardless of the actual containing address book.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Migrate Notes](#mignotes)
2. [Incoming Shared Calendars](#insharecal)
3. [Migrate Appointments from Mail Attachments](#migappmail)

### Migrate Notes <a name="mignotes"></a>
{: .no_toc }
Default Value: On

Migrate GroupWise notes as all day appointments.

Change Conditions: ??

### Incoming Shared Calendars <a name="insharecal"></a>
{: .no_toc }
Default Value: Off

Migrate incoming shared calendars from GroupWise. This will result in duplication of items between accounts and is not recommended.

Change Conditions: ??

### Migrate Appointments from Mail Attachments <a name="migappmail"></a>
{: .no_toc }
Default Value: On

Migrate GroupWise appointments that are attached to mail messages.

Change Conditions: ??

---
## Account/Archive
[Back to Top](#top)

1. [Archive Label/Folder Method](#archfoldmet)
2. [Incoming Shared Folders](#incomingshare)
2. [Archive Label/Folder](#archfold)
2. [Message Export Method](#mesexportmet)

### Archive Label/Folder Method <a name="archfoldmet"></a>
{: .no_toc }
Default Value: Folder Structure and Label/Category

Migrate GroupWise notes as all day appointments.

Change Conditions: ??

### Incoming Shared Folders <a name="incomingshare"></a>
{: .no_toc }
Default Value: Off

Migrate GroupWise notes as all day appointments.

Change Conditions: ??

### Archive Label/Folder <a name="archfold"></a>
{: .no_toc }
Default Value: GroupWise Archive

Migrate GroupWise notes as all day appointments.

Change Conditions: ??

### Message Export Method <a name="mesexportmet"></a>
{: .no_toc }
Default Value: Quick Messages

Select to use an alternate means of enumerating messages in a GroupWise folder.

Change Conditions: ??

---
## User
[Back to Top](#top)

1. [Migrate Signature](#migratesig)
2. [Migrate Account Delegation](#accountdel)
3. [Maintain Cabinet Name in Folder Hierarchy](#cabname)
4. [Migrate Rules/Filters](#migrules)
5. [Absolute Maximum Attachment Size](#maxattach)

### Migrate Signature <a name="migratesig"></a>
{: .no_toc }
Default Value: Off

Set to true to migrate the user's GroupWise signature.

Change Conditions: ??

### Migrate Account Delegation <a name="accountdel"></a>
{: .no_toc }
Default Value: Off

Set to true to migrate the user's account delegation rules.

Change Conditions: ??

### Maintain Cabinet Name in Folder Hierarchy <a name="cabname"></a>
{: .no_toc }
Default Value: Off

When migrating Cabinets, preserve the Cabinet name in the folder hierarchy e.g. Cabinet/Folder/SubFolder.

Change Conditions: ??

### Migrate Rules/Filters <a name="migrules"></a>
{: .no_toc }
Default Value: Off

Set to true to migrate the user's account rules (GroupWise 8 only).

Change Conditions: ??

### Absolute Maximum Attachment Size <a name="maxattach"></a>
{: .no_toc }
Default Value: 524288000

When processing attachments from any GroupWise item, skip the attachment it it is larger than this value (in bytes). This is required to prevent memory issues.

Change Conditions: ??

