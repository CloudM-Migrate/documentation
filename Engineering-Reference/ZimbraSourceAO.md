---
layout: default
title: Zimbra
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 6
---

## Zimbra Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Zimbra Source Advanced Options in CloudM Migrate. 

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

1. [Migrate Incoming Shared Folders](#migincomshare)
2. [Use Metadata Date](#usemetadate)
3. [Convert RTF To MIME](#zcategories)

### Migrate Incoming Shared Folders <a name="migincomshare"></a>
{: .no_toc }
Default Value: Off

Migrate folders that have been shared with the user being migrated.

Change Conditions: ??

### Use Metadata Date <a name="usemetadate"></a>
{: .no_toc }
Default Value: Off

Use the metadata date supplied by the Zimbra server for the email date. Use when date headers are not standard RFC822 headers.

Change Conditions: ??

### Categories <a name="zcategories"></a>
{: .no_toc }
Default Value: On

Migrate tags to Categories or Labels from Zimbra 8 and above (not supported on version 7).

Change Conditions: ??

---
## Contact
[Back to Top](#top)

1. [Migrate All Group Members](#migallgroup)
2. [Migrate Incoming Shared Folders](#migincomsharef)

### Migrate All Group Members <a name="migallgroup"></a>
{: .no_toc }
Default Value: Off

Migrate folders that have been shared with the user being migrated.

Change Conditions: ??

### Migrate Incoming Shared Folders <a name="migincomsharef"></a>
{: .no_toc }
Default Value: Off

Migrate folders that have been shared with the user being migrated.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Migrate All Group Members](#cmigallgroup)

### Migrate Incoming Shared Folders <a name="cmigallgroup"></a>
{: .no_toc }
Default Value: Off

Migrate folders that have been shared with the user being migrated.

Change Conditions: ??

---
## Task
[Back to Top](#top)

1. [Migrate All Group Members](#cmigallgroup)

### Migrate Incoming Shared Folders <a name="cmigallgroup"></a>
{: .no_toc }
Default Value: Off

Migrate folders that have been shared with the user being migrated.

Change Conditions: ??

---
## Other
[Back to Top](#top)

1. [Migrate All Group Members](#cmigallgroup)

### Unavailable Wait <a name="cmigallgroup"></a>
{: .no_toc }
Default Value: 250

If the server responds with 503 Unavailable when making a REST request, wait for this many milliseconds before retrying.

Change Conditions: ??

###  Direct Mailbox Connection <a name="cmigallgroup"></a>
{: .no_toc }
Default Value: 250

Use a direct connection the mailbox server for each user rather than connecting through the main proxy address.

Change Conditions: ??
