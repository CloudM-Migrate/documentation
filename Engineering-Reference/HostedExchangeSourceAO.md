---
layout: default
title: Hosted Exchange
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 3
---

## Hosted Exchange Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Hosted Exchange Source Advanced Options in CloudM Migrate. 

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
## Email

1. [Excluded Item Classes](#excludeitem)
2. [Log Excluded Items](#logexcludeitem)
3. [Recoverable Mail Items](#recovermailitem)
4. [Extended MAPI Properties](#extendmapiprop)
5. [Included Item Classes](#includeitemclass)
6. [Migrate SMIME Signed Messages Without Modification ](#migratesmime)
7. [Recoverable Mail Items Label/Category](#recovermailitemlabel)

### Excluded Item Classes <a name="excludeitem"></a>
{: .no_toc }
Default Value: None

Specify the list of item classes that will not be processed as part of a migration. Exact matches are made on the value specified here.

Change Conditions: ??

### Log Excluded Items <a name="logexcludeitem"></a>
{: .no_toc }
Default Value: Off

Include excluded mail items in the migration reports. May produce large reports where many items are not migrated due to matching rules.

Change Conditions: ??

### Recoverable Mail Items <a name="recovermailitem"></a>
{: .no_toc }
Default Value: None

Select how to include recoverable mail items when migrating from Exchange and Office 365.

Change Conditions: ??

### Extended MAPI Properties <a name="extendmapiprop"></a>
{: .no_toc }
Default Value: Archive ID:String;Saveset ID:String;ExMD5:String;ExShortcut:Integer;PR_MSGID2:String;

Specify the list of custom MAPI properties to migrate (valid when migrating to Exchange/Office 365 only).

Change Conditions: ??

### Included Item Classes <a name="includeitemclass"></a>
{: .no_toc }
Default Value: IPM.Note;IPM.Note.*

Specify the list of item classes that will be processed as part of a migration. Wildcard matches can be used.

Change Conditions: ??

### Migrate SMIME Signed Messages Without Modification <a name="migratesmime"></a>
{: .no_toc }
Default Value: On

When migrating SMIME signed messages, perform no modification of the messages. This could mean some other features of CloudM Migrate may not be executed, such as moving attachments to Drive or ensuring the sent address is correct. It will ensure however that the digital signature verifies.

Change Conditions: ??

### Recoverable Mail Items Label/Category <a name="recovermailitemlabel"></a>
{: .no_toc }
Default Value: Recoverable Items

Apply the specified label/category to items migrated from within the Recoverable Items folder. Leave empty to not apply a label/category.

Change Conditions: ??

---
## Contact
[Back to Top](#top)

1. [Primary Contact Type](#primarycontact)
2. [Exclude Group GAL Contact Aliases](#exludegalcontact)

### Primary Contact Type <a name="primarycontact"></a>
{: .no_toc }
Default Value: SMTP

Choose either SMTP or SIP address when resolving contact email addresses.

Change Conditions: ??

### Exclude Group GAL Contact Aliases <a name="exludegalcontact"></a>
{: .no_toc }
Default Value: SMTP

Exclude additional email addresses (aliases) when resolving a Group GAL contact.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Migrate Non-Organizer Attendee Statuses](#migratenonorgattend)
2. [Exchange 2007 Calendar Timezone](#exchange2007cal)

### Migrate Non-Organizer Attendee Statuses <a name="migratenonorgattend"></a>
{: .no_toc }
Default Value: Off

Attempt to migrate attendee statuses for appointments where the migrating user is not the owner (when the owner is being migrated attendee statuses are always preserved). Due to API limitations, for any appointments from outside of the domain and from any accounts that no longer exist the attendee status will always not be migrated.

Change Conditions: ??

### Exchange 2007 Calendar Timezone <a name="exchange2007cal"></a>
{: .no_toc }
Default Value: GMT Standard Time

The default timezone to use with appointments when migrating from Exchange 2007 when the timezone is not identified by other means.

Change Conditions: ??

---
## Public Folders
[Back to Top](#top)

1. [Include Public Folders in User List](#includepublic)
2. [Public Folder User Name](#publicfolderuser)

### Include Public Folders in User List <a name="includepublic"></a>
{: .no_toc }
Default Value: Off

Specifies whether Public Folders will be obtained when getting a user list.

Change Conditions: ??

### Public Folder User Name <a name="publicfolderuser"></a>
{: .no_toc }
Default Value: None

The primary SMTP email address of the user that will be used when migrating Public Folders. This user must have an active mailbox.

Change Conditions: ??

---
## Authentication
[Back to Top](#top)

1. [Direct Exchange EWS URL](#directewsurl)
2. [Use Workstation Credentials](#useworkcreds)
3. [Authentication Method](#authmethod)
4. [Credential Method](#credmethod)

### Direct Exchange EWS URL <a name="directewsurl"></a>
{: .no_toc }
Default Value: None

The optional direct Exchange EWS server URL if the server for all users is known and constant. Used in preference of the Exchange URL if present. Usually, autodiscovery should be used.

Change Conditions: Required value for hosted EWS URL. 

### Use Workstation Credentials <a name="useworkcreds"></a>
{: .no_toc }
Default Value: None

Use the credentials of the logged in user of the workstation to perform migrations rather than the provided username and password. The admin username and password is still required for auto-discovery.

Change Conditions: Required value for hosted EWS URL. 

### Authentication Method <a name="authmethod"></a>
{: .no_toc }
Default Value: Modern

Choose the authetication type that will be used with the server. For Office 365 this should be set to 'Modern'.

Change Conditions: ??

### Credential Method <a name="credmethod"></a>
{: .no_toc }
Default Value: Impersonation

Choose whether to use Impersonation (recommended) or the user credentials when Impersonation cannot be used.

Change Conditions: Recommend to use Impersonation. 

---
## User
[Back to Top](#top)

1. [Migrate Account Delegates](#migrateaccountdel)
2. [Migrate Out Of Office](#workcred)
3. [Migrate Signature](#exchangever)

### Migrate Account Delegates <a name="migrateaccountdel"></a>
{: .no_toc }
Default Value: On

Migrate user account delegation.

Change Conditions: ??

### Migrate Out Of Office <a name="exchangever"></a>
{: .no_toc }
Default Value: On

Migrate user Out Of Office settings.

Change Conditions: ??

### Migrate Signature <a name="exchangever"></a>
{: .no_toc }
Default Value: On

Migrate user signature settings.

Change Conditions: ??

---
## Transfer and Performance
[Back to Top](#top)

1. [Retry Count](#retrycount)
2. [Timeout](#trantimeout)
3. [Max Wait Time](#maxwaittime)
4. [Use X-AnchorMailbox Header](#usexachor)

### Retry Count <a name="retrycount"></a>
{: .no_toc }
Default Value: 10

The number of times an operation will be attempted before failing.

Change Conditions: ??

### Timeout <a name="trantimeout"></a>
{: .no_toc }
Default Value: 1200000

The timeout that will apply to communications with the Exchange server.

Change Conditions: ??

### Max Wait Time <a name="maxwaittime"></a>
{: .no_toc }
Default Value: 1200000

Specify the maximum time that a wait operation can wait between exponential backoff retry attempts.

Change Conditions: ??

### Use X-AnchorMailbox Header <a name="usexachor"></a>
{: .no_toc }
Default Value: On

When using application impersonation, use the X-AnchorMailbox header to improve performance.

Change Conditions: ??

---
## PowerShell
[Back to Top](#top)

1. [PowerShell Variables](#psvariable)
2. [PowerShell Get User Init Script](#psuserinit)

### PowerShell Variables <a name="psvariable"></a>
{: .no_toc }
Default Value: [!ps-url]:https://ps.outlook.com/PowerShell-LiveID;[!o365-location]:GB;[!o365-subscription-sku]:ENTERPRISEPACK;

The collection of user-defined substitution variables that can be used in PowerShell scripts.

Change Conditions: ??

### PowerShell Get User Init Script <a name="psuserinit"></a>
{: .no_toc }
Default Value: # Set this so that errors are thrown from Cmdlets

The PowerShell script that will be run to obtain the user list.

Change Conditions: ??

---
## Archive2Anywhere
[Back to Top](#top)

1. [Archive Type](#archivetype)
2. [API Key](#apikey)
3. [Timeout](#archtimeout)
4. [Server URL](#serverurl)
5. [Retry Count](#aretrycount)

### Archive Type <a name="archivetype"></a>
{: .no_toc }
Default Value: Enterprise Vault

The type of the archive that will be processed from Archive2Anywhere.

Change Conditions: ??

### API Key <a name="apikey"></a>
{: .no_toc }
Default Value: None

The API key required for calling the Archive2Anywhere endpoint.

Change Conditions: ??

### Timeout <a name="archtimeout"></a>
{: .no_toc }
Default Value: 120000

The time (in milliseconds) before a connection will fail.

Change Conditions: ??

### Server URL <a name="serverurl"></a>
{: .no_toc }
Default Value: None

The URL that will be used to make requests to re-hydrate email stubs from Archive2Anywhere.

Change Conditions: ??

### Retry Count <a name="aretrycount"></a>
{: .no_toc }
Default Value: 3

The number of times to retry rehydrating a stub before failing.

Change Conditions: ??
