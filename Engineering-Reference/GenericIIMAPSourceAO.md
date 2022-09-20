---
layout: default
title: Generic IMAP
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 8
---

## Generic IMAP Source Advanced Options
{: .no_toc }

---

This document will give an overview on all the Generic IMAP Source Advanced Options in CloudM Migrate. 

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

Specify a test email address or username to test connections to the IMAP server when using Admin Credentials as the authentication method.

Change Conditions: ??

### Test Password <a name="testpass"></a>
{: .no_toc }
Default Value: None

Specify the password for the test user to test connections to the IMAP server if user passwords are to be used.

Change Conditions: ??

---
## Server Details

1. [Start TLS](#starttls)
2. [Authentication Type](#authtype)

### Start TLS <a name="starttls"></a>
{: .no_toc }
Default Value: None

Set to true to attempt to use secure communications with the IMAP server.

Change Conditions: ??

### Authentication Type <a name="authtype"></a>
{: .no_toc }
Default Value: None

Choose whether to use admin or user credentials to authenticate to the IMAP server. When using admin credentials auth PLAIN with the authentication identity (authzid) as the admin username.

Change Conditions: ??

---
## Email

1. [IMAP Special Folder Names](#imapspecfol)
2. [Remove Label Prefix](#removelabpre)
3. [Auto Generate Missing Message IDs](#autogenmiss)
4. [Ignore Search Date Range](#ignoresearcdate)

### IMAP Special Folder Names <a name="imapspecfol"></a>
{: .no_toc }
Default Value: Inbox:INBOX;Drafts:Drafts;SentItems:Sent Items;Deleted:Trash;

The names of the special IMAP folders. Leave a folder name empty to exclude it from the migration, or if it does not exist.

Change Conditions: ??

### Remove Label Prefix <a name="removelabpre"></a>
{: .no_toc }
Default Value: None

Remove the specified text from the beginning of all folder names/label. Leave empty to perform no text removal.

Change Conditions: ??

### Auto Generate Missing Message IDs <a name="autogenmiss"></a>
{: .no_toc }
Default Value: Off

Use automatically generated message IDs for any messages that do not contain a message ID.

Change Conditions: ??

### Ignore Search Date Range <a name="ignoresearcdate"></a>
{: .no_toc }
Default Value: Off

Ignore the configured mail date range and search for ALL messages. This can help with retrieving messages on restricted IMAP servers.

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
