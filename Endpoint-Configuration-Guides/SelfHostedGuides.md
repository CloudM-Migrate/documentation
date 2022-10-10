---
layout: default
title: Self Hosted Guides
parent: Endpoint Configuration Guides
has_children: true 
nav_order: 23

---

## Self Hosted Guides
{: .no_toc }

CloudM Migrate can be installed on server(s) in your environment or your own Azure instance. 

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

### A More Secure Implementation

CloudM Migrate already has end to end encryption between migration endpoints. The option to Self Host CloudM Migrate will complete isolate your migration data to your source environment to the destination cloud tenant. 

Licenses for Self Hosted migrations are discounted from Cloudm Migrat SaaS option. 

### Server Basic Requirements

- 64 bit Operating system: Windows Server 2016+ (Clean build recommended)
  - Microsoft .NET Framework 4.8
- Recommended system specification - Primary Server:
  - 3GHz 8 Core Processor or better
  - 200+ GB Disk space
  - 16+ GB Memory
- Recommended system specification - Secondary Server(s):
  - 3GHz 4 Core Processor or better
  - 100 GB Disk space
  - 8+ GB Memory

Any available Windows updates should be installed and the machine rebooted prior to installation, and a full system administrator is recommended for installation.

### GDPR

All logs, project configuration and migration reports are autodeleted after 30 days on inactivty in the self-hosted CloudM Migrate. This is done to ensure that personally indentifable meta data is not stored to as required under GDPR regulations. 

### Self Hosted Only Endpoints

Several endpoints can only be used a source with the self-hosted install. 
