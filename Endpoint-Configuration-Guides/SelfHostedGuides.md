---
layout: default
title: Self Hosted Guides
parent: Endpoint Configuration Guides
has_children: true 
nav_order: 3

---

## Self Hosted Guides
{: .no_toc }

CloudM Migrate can be installed on server(s) in your environment, <a href="https://learn.microsoft.com/en-us/training/modules/create-windows-virtual-machine-in-azure/">Azure</a>, <a href="https://cloud.google.com/compute/docs/instances/create-start-instance">Google Cloud Platform</a> or <a href="https://aws.amazon.com/getting-started/hands-on/launch-windows-vm/">Amazon</a>.

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
{: .no_toc }

CloudM Migrate already has end to end encryption between migration endpoints. The option to Self Host CloudM Migrate will completly isolate your migration data to your source environment to the destination cloud tenant. 

Licenses for Self Hosted migrations are discounted from the Cloudm Migrate SaaS option. 

### Server Basic Requirements

- 64 bit Operating system: Windows Server 2016+ (Clean build recommended)
  - Microsoft .NET Framework 4.8
- Recommended minimum system specification - Primary Server:
  - 3GHz 8 Core Processor or better
  - 200+ GB Disk space
  - 16+ GB Memory
- Recommended minimum system specification - Secondary Server(s):
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

For higher migration velocity mutiple CloudM Migrate servers can be deployed in a cluster. Clustering is done using <a href="https://redis.io/docs/manual/scaling/">Redis</a> and will require the following ports to be open. 

- Redis (Clustering) port 6379
- SQL server runs on TCP port 1433 and UDP port 1434 
- Microsoft Messaging Queue on port 80

First a Primary node is stood up followed by up to 5 Secondary nodes. The limit of secondary nodes is mainly limited by throttling limits of destination tenants. If the project has multiple destination tenants then up to 6 nodes per destination can be utilized. 

The Primary node (Primary Service) coordinates execution of migrations on the Secondary nodes (Secondary Service) and can be configured to itself execute migration threads. For best performance it's recommended to not enable the secondary service on the primary node. The Primary Service can only be run on a single server in the same network. 

### SQL Install

By default the Self Hosted install uses SQL Server Express. After installing the Primary node the installation will display details for the SQL Express install that will be needed when configuring the secondary nodes. 

For larger migrations it may require a full SQL install to avoid limitations on SQL Server Express. It's recommend to do a full SQL install on migrations larger then 25,000 mailboxes. To use an existing SQL instance use the Advanced Options when installing. 

### Ports and Firewall

Both primary and secondary CloudM Migrate servers communicate with source and destination endpoints over port 80 and 443. The CloudM Migrate licensing endpoint uses port 443.

Depending on firewall restrictions it maybe nessecary to whitelist the licensing server portal.thecloudmigrator.com.

### Updating

To update CloudM Migrate this can be performed from the Primary node using CloudM Migrate Service Manager. Validate the all cluster nodes are inactive and select Upgrade Servers from the Remote Connections tab. 

### Self Hosted Only Endpoints

Several endpoints can only be used as a source with the Self Hosted install. 
