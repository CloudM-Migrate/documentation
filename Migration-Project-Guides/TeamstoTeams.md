---
layout: default
title: Teams to Teams
parent: Migration Project Guides
nav_order: 3
has_children: false
has_toc: false

---

## Teams to Teams
{: .no_toc }

Before starting your migration project, make sure you have setup both <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> endpoints using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

When doing a Teams to Teams migration it's recommmend to have already created the users on the destination tenant. If this is not done it's possible for a channel to be created without the correct Team Owner. 

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

### Standard Migration 

This process assumes that the destinaton tenant contains all the users and have already had mailboxes provisioned. A first migration pass is performed followed by a Delta with a Finalize Migration switch to make the Teams instance available to end users.

### First Migration Pass


