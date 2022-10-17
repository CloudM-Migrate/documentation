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

## Standard Migration 

This process assumes that the destinaton tenant contains all the users and the Teams site and Channels are created in the <a href="https://learn.microsoft.com/en-us/microsoftteams/platform/graph-api/import-messages/import-external-messages-to-teams">Migrate Teams Creation Mode</a>. This essentailly prestages the Team is a special mode that restricts usage until the migration process is completed. 

### First Migration Pass


