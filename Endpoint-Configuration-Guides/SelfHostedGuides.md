---
layout: default
title: Self Hosted Guides
parent: Endpoint Configuration Guides
has_children: true 
nav_order: 5

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

CloudM Migrate already has end to end encryption between migration endpoints. The option to Self Host CloudM Migrate will completely isolate your migration data from your source environment to the destination cloud tenant. 

Licenses for Self Hosted migrations are discounted from the CloudM Migrate SaaS option. 

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

Any available Windows updates should be installed and the machine rebooted prior to installation, a full system administrator is recommended for installation.

### Binary for x64

<a href="https://www.cloudm.io/CloudM-Migrate-Latest-x64.exe">CloudM Migrate x64</a>

**NOTE:** Not compatible with GroupWise or Lotus Notes.

SHA1 - f6f2359def4d5f60f56463899c3d41dcc6424cb9

MD5 - 3281a4d18262d7e43c8e759ceab386d1

### Binary for x86

<a href="https://www.cloudm.io/CloudM-Migrate-Latest.exe">CloudM Migrate x86</a>

SHA1 - 2c0b587d33f1bea25de5e74172073ecca6c52535

MD5 - e3cdf42e741533f2ce51b771aeee7701

### Clustering

For higher migration velocity multiple CloudM Migrate servers can be deployed in a cluster. Clustering is done using <a href="https://redis.io/docs/manual/scaling/">Redis</a> and will require the following ports to be open. 

- Redis (Clustering) port 6379
- SQL server runs on TCP port 1433 and UDP port 1434 
- Microsoft Messaging Queue on port 80

First a Primary node is stood up followed by up to 6 Secondary nodes. When installing a Secondary, select Advanced Options and select **Install Secondary Migration Service**. A restart of the service on the primary node may be required. 

The limit of secondary nodes is mainly limited by throttling limits of destination tenants. If the project has multiple destination tenants then up to 6 nodes per destination can be utilized. 

The Primary node (Primary Service) coordinates execution of migrations on the Secondary nodes (Secondary Service) and can be configured to itself execute migration threads. For best performance it's recommended to not enable the secondary service on the primary node. The Primary Service can only be run on a single server in the same network. 

### SQL Install

By default the Self Hosted install uses SQL Server Express. After installing the Primary node the installation will display details for the SQL Express install that will be needed when configuring the secondary nodes. 

For larger migrations it may require a full SQL install to avoid limitations on SQL Server Express. It's recommend to do a full SQL install on migrations larger than 25,000 mailboxes. To use an existing SQL instance use the Advanced Options when installing. 

### Ports and Firewall

Both primary and secondary CloudM Migrate servers communicate with source and destination endpoints over port 80 and 443. The CloudM Migrate licensing servers use port 443.

Depending on firewall restrictions it maybe necessary to whitelist the licensing server portal.thecloudmigrator.com.

### Updating

To update CloudM Migrate this can be performed from the Primary node using CloudM Migrate Service Manager. Validate the all cluster nodes are inactive and select Upgrade Servers from the Remote Connections tab. 

### Self Hosted Only Endpoints

Several endpoints can only be used as a source with the Self Hosted install: 
