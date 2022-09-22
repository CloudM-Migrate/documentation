---
layout: default
title: Dropbox
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 17
---

## Dropbox Endpoint Options
{: .no_toc }

---
This document will give an overview on all the Dropbox Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/DropBoxSourceAO.html">Dropbox Source Advanced Options</a>
         
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
### Admin Email

Team Admin Email Address

### Authorisation Code

Authorisation Code returned from Dropbox when authorising CloudM Migrate.

### Test User Name

The login email address of a non-admin user within the system to test. This user must have the active status in Dropbox.

### Team Folder Owner

The email address of the user who will take ownership of 'Team Folders' in the destination (see documentation).

### Retry Count
Default Value: 10

The number of times an operation will be attempted before failing.

### Timeout
Default Value: 1800000

The timeout that will apply to communications with the Dropbox server.
