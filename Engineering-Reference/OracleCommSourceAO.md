---
layout: default
title: Oracle Communications
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 10
---

## Oracle Communications Source Advanced Options
{: .no_toc }

---

This document will give an overview on all the Oracle Communications Source Advanced Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/OracleCommSource.html">Oracle Communications Source Options</a>

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
## Test Details

1. [Test Username](#testuser)
2. [Test Password](#testpass)

### Test Username <a name="testuser"></a>
{: .no_toc }
Default Value: None

Specify a test email address or username to test connections to the Oracle Communications server when using Admin Credentials as the authentication method.

Change Conditions: ??

### Test Password <a name="testpass"></a>
{: .no_toc }
Default Value: Off

Specify the password for the test user to test connections to the Oracle Communications server if user passwords are to be used.

Change Conditions: ??

---
## Server Details

1. [Start TLS](#starttls)
2. [Authentication Type](#authtype)

### Start TLS <a name="starttls"></a>
{: .no_toc }
Default Value: Off

Set to true to attempt to use secure communications with the IMAP server.

Change Conditions: ??

### Authentication Type <a name="authtype"></a>
{: .no_toc }
Default Value: User Credentials

Choose whether to use admin or user credentials to authenticate to the Oracle Communications server. When using admin credentials auth PLAIN with the authentication identity (authzid) as the admin username.

Change Conditions: ??

---
## Email

1. [Special Folder Names](#specfoldn)
2. [Remove Label Prefix](#removlabpre)
3. [Replace Folder Strings](#replfoldst)
4. [Auto Generate Missing Message IDs](#autogenmiid)
5. [Ignore Search Date Range](#ignoseadate)

### Special Folder Names <a name="specfoldn"></a>
{: .no_toc }
Default Value: Inbox:Inbox;Drafts:Drafts;SentItems:Sent;Deleted:Trash;

The names of the special folders. Leave a folder name empty to exclude it from the migration, or if it does not exist.

Change Conditions: ??

### Remove Label Prefix <a name="removlabpre"></a>
{: .no_toc }
Default Value: None

Remove the specified text from the beginning of all folder names/label. Leave empty to perform no text removal.

Change Conditions: ??

### Replace Folder Strings <a name="replfoldst"></a>
{: .no_toc }
Default Value: None

Specify name/value pairs to be replaced in folder/label names. Specify the value to be replaced and the replacement.

Change Conditions: ??

### Auto Generate Missing Message IDs <a name="autogenmiid"></a>
{: .no_toc }
Default Value: Off

Use automatically generated message IDs for any messages that do not contain a message ID.

Change Conditions: ??

### Ignore Search Date Range <a name="ignoseadate"></a>
{: .no_toc }
Default Value: Off

Ignore the configured mail date range and search for ALL messages. This can help with retrieving messages on restricted Oracle Communications servers.

Change Conditions: ??

---
## Contact

1. [Contact Server Address](#contseradd)
2. [Contact Server Username](#contservuse)
3. [Batch size](#batchsiz)
4. [Contact Server Password](#contactserpass)

### Contact Server Address <a name="contseradd"></a>
{: .no_toc }
Default Value: Inbox:Inbox;Drafts:Drafts;SentItems:Sent;Deleted:Trash;

Url for the contact server.

Change Conditions: ??

### Contact Server Username <a name="contservuse"></a>
{: .no_toc }
Default Value: None

Username credentials for the contact server.

Change Conditions: ??

### Batch size <a name="batchsiz"></a>
{: .no_toc }
Default Value: 10

Number of address book contacts to process per batch.

Change Conditions: ??

### Contact Server Password <a name="contactserpass"></a>
{: .no_toc }
Default Value: None

Contact Server Password

Change Conditions: ??

---
## Calendar

1. [Calendar Server Address](#contseraddc)
2. [Calendar Server Username](#contservusec)
3. [Calendar Exclusions](#calexclu)
4. [Calendar Server Password](#calserpassc)

### Calendar Server Address <a name="contseraddc"></a>
{: .no_toc }
Default Value: Inbox:Inbox;Drafts:Drafts;SentItems:Sent;Deleted:Trash;

Url for the calendar server.

Change Conditions: ??

### Calendar Server Username <a name="contservusec"></a>
{: .no_toc }
Default Value: None

Username credentials for the calendar server.

Change Conditions: ??

### Calendar Exclusions <a name="calexclu"></a>
{: .no_toc }
Default Value: /calendar-inbox/;/calendar-outbox/;/sharing-inbox/;/sharing-outbox/;/dropbox/

List of excluded internal calendar urls that will not be exported.

Change Conditions: ??

### Calendar Server Password <a name="calserpassc"></a>
{: .no_toc }
Default Value: None

Password credentials for the calendar server.

Change Conditions: ??

---
## Timeout

1. [Connect Timeout](#conntime)
2. [Read Timeout](#readtime)

### Connect Timeout <a name="conntime"></a>
{: .no_toc }
Default Value: 30

The server connect timeout in seconds.

Change Conditions: ??

### Read Timeout <a name="readtime"></a>
{: .no_toc }
Default Value: 30

The server read timeout in seconds.

Change Conditions: ??

