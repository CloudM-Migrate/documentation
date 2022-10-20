---
layout: default
title: Lotus Notes
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 1
has_toc: false

---

## Lotus Notes Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Lotus Notes as a source endpoint. Lotus Notes requires a Self-Hosted install of CloudM Migrate in your environment. See 

For Lotus Notes this is defined by the following requirements:

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

### Self Hosted Install

For Lotus Notes migrations a Self Hosted install of CloudM Migrate is required. 

**NOTE:** Only the x86 version is compatible. 
  
### Lotus Notes Client 

A Lotus Notes client that can connect to the current environment will need to be install on the same server as CloudM Migate. It's recommended the client 6.0.2 or higher and validate it's connectivity to the Domino server. 

In CloudM Migate enter the valid Windows Account that will be used to access the Lotus Notes client. 

### Authentication Method 

In CloudM Migrate under Step 1 enter the IP or hostname of the Domino Server. An Admin account and password that has access to read all databases in Domino. 

The Lotus Notes Admin ID file will need to be uploaded into CloudM Migrate. 
