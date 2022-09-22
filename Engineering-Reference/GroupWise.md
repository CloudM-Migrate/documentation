---
layout: default
title: GroupWise
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 4
---

## GroupWise Endpoint Options
{: .no_toc }

---

This document will give an overview on all the GroupWise Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/GroupWise.html">GroupWise Endpoint Options</a>

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

### GroupWise Version <a name="serverport"></a>
Default Value: Novell GroupWise 7.0.3+

The version of the GroupWise server.

### Server Address <a name="serverport"></a>

The hostname or IP address of the GroupWise server

### Admin Username <a name="serverport"></a>

The name of a mail enabled admin user within the GroupWise system, used to test connections and to obtain user lists.

### Admin Password <a name="serverport"></a>

The password for the admin user.

### Trusted Application Name <a name="serverport"></a>

The trusted application name that has been allocated to this program. The trusted application entry must be created in GroupWise prior to use.

<a name="https://www.novell.com/documentation/groupwise18/gw18_guide_admin/data/adm_sys_tools_trusted_applications.html">Novell Guidance on creating a Trusted Application</a>
  
### Trusted Application Key <a name="serverport"></a>

The trusted application key as provided when registering the trusted application. The key should be entered exactly as provided.

### Account Processing <a name="serverport"></a>

Choose the combination of accounts and archives to migrate.

### GroupWise 2012 Or Less Domain Name <a name="serverport"></a>

The DN of the GroupWise domain object in the following format: dom1.groupwise.server. Either this or the 'Domain Path' below can be used to connect to the GroupWise domain.

### GroupWise 2012 Or Less Domain Path <a name="serverport"></a>

The path to the GroupWise domain. The path can be either a mapped drive or a UNC path. Either this or the 'Domain DN' above can be used to connect to the GroupWise domain.

