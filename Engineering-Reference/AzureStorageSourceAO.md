---
layout: default
title: Azure Storage
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 14
---

## Azure Storage Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Azure Storage Source Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/AzureStorage.html">Azure Storage Endpoint Options</a>
         
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
## Azure Cloud Storage

1. [Page Size](#pagesi)

### Page Size <a name="pagesi"></a>
{: .no_toc }
Default Value: 1000

Page size to use when listing objects in cloud storage

Change Conditions: ??

---
## Azure Key Vault Decryption

1. [Key Vault Decryption Key Url](#keyvalurl)
2. [Client Secret](#clisec)
3. [Client ID](#cliid)

### Key Vault Decryption Key Url <a name="keyvalurl"></a>
{: .no_toc }
Default Value: None

Url of the decryption key in Azure Key Vault e.g. https://contosokeyvault.vault.azure.net/keys/TestRSAKey1..

Change Conditions: ??

### Client Secret <a name="clisec"></a>
{: .no_toc }
Default Value: None

Client Secret used to access Azure Key Vault.

Change Conditions: ??

### Client ID <a name="cliid"></a>
{: .no_toc }
Default Value: None

Client ID used to access Azure Key Vault.

Change Conditions: ??

---
## Customer-Supplied Key Decryption

1. [Decryption Key File Path (.akey)](#deckefilde)

### Decryption Key File Path (.akey) <a name="deckefilde"></a>
{: .no_toc }
Default Value: None

The location of your decryption key file. File extension (.akey)

Change Conditions: ??
