---
layout: default
title: PST Archive
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 11
---

## PST Archive Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the PST Source Advanced Options in CloudM Migrate. 

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
## MAPI Properties

1. [SharePoint Migration API](#sharepointapi)

### Extended MAPI Properties <a name="sharepointapi"></a>
{: .no_toc }
Default Value: Archive ID:String;Saveset ID:String;ExMD5:String;ExShortcut:Integer;PR_MSGID2:String;

Specify the list of custom MAPI properties to migrate (valid when migrating to Exchange/Office 365 only).

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
