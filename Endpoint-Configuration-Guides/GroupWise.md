---
layout: default
title: GroupWise
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 2

---

## GroupWise Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure GroupWise as a source endpoint. 

For GroupWise this is defined by the following requirements:

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

###

These are the steps to migrate a single GroupWise mailbox.

1. Default: The active user working currently in GroupWise gets migrated.
2. Login: Credentials required to migrate the GroupWise mailbox
3. Command Line: Without using credentials of the email address or being active on GroupWise

---
### 

Creating Application Key & Trusted Name 

1.	Open the GroupWise Administration Console in the web browser.
2.	Go to 'System - Trusted Applications
3.	Click 'New' in the 'Trusted Applications' window.
4.	A popup for a 'New Trusted App Key' will appear. Type 'GroupWise Mailbox Management' in the 'Name' field.
5.	Click ‘OK’
6.	You can either copy the key or click ‘Export’ to save it as a TXT file to make sure you do not lose the key.

<a href="https://www.novell.com/documentation/groupwise-mailbox-management18/groupwise-mailbox-management/data/fmchapter10.html">Groupwise Application Key Process</a>   - Additional information can be referenced here 
