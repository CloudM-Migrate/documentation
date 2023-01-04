---
layout: default
title: PST Archive
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 4

---

## PST Archive Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure a PST Archive as a source endpoint. 

For PST Archive this is defined by the following requirements:

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

### File Locations 

In order to migrate PST archives successfully that the profile runs under the SYSTEM user. When performing this type of migration and select a drive letter and keep in mind mapping a drive as a regular windows user in the file explorer will not work. 

### Access to Mapped Drives using PSEXEC 

If using clustering then ensure the CloudM Migrate service has access to mapped drives. Confirm you are logged in as nt authority\system. whoami. 
Run the command to map the drive as system. Launch command prompt as SYSTEM user using psexec - psexec -i -s cmd.exe.

- Replace \\servername\sharedfolder with the UNC path of the folder you wish to map.
- net use z: \\servername\sharedfolder /persistent:yes
- Run the below command and take another screenshot.
- net use
- Run the below command.
- z:
- Run the below command and take another screenshot.
- dir



