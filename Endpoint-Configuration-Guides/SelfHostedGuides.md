---
layout: default
title: Self Hosted Guides
parent: Endpoint Configuration Guides
has_children: true 
nav_order: 3

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

### Binary for x64

<a href="https://storage.googleapis.com/cloudmigrator/CloudM-Migrate-3.37.6.0-x64.exe">CloudM Migrate x64</a>

**NOTE:** Not compatibable with GroupWise or Lotus Notes.

SHA1 - f8a2d54bc2aa4d2572094e2501c53b6f74fa8094

MD5 - a2a44382fe1c69cabd386d6552d4916f

### Binary for x86

<a href="https://storage.googleapis.com/cloudmigrator/CloudM-Migrate-3.37.6.0.exe">CloudM Migrate x86</a>

SHA1 - 1e8ba97b49a1f7fc05851d05603bf6daf24c77c1

MD5 - 11cf29adb69ede490fd63a1ab242dc9c

### Clustering

For higher migration velocity mutiple CloudM Migrate servers can be deployed. Clustering is done using <a href="https://redis.io/docs/manual/scaling/">Redis</a> and will require the following ports to be open. 

- Redis (Clustering) port 6379
- SQL server runs on TCP port 1433 and UDP port 1434 
- Microsoft Messaging Queue on port 80

### Ports and Firewall

Both primary and secondary CloudM Migrate servers communicate with source and destination endpoints over port 80 and 443. The CloudM Migrate licensing endpoint uses port 443.

Depending on firewall restrictions it maybe nessecary to whitelist the licensing server portal.thecloudmigrator.com.
  
### GDPR

All logs, project configuration and migration reports are autodeleted after 30 days on inactivty in the self-hosted CloudM Migrate. This is done to ensure that personally indentifable meta data is not stored to as required under GDPR regulations. 

### Self Hosted Only Endpoints

Several endpoints can only be used a source with the self-hosted install. 
