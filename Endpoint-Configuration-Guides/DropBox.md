---
layout: default
title: DropBox
parent: Endpoint Configuration Guides
nav_order: 16
---

## DropBox Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure DropBox as a source endpoint. 

For DropBox this is defined by the following requirements:

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

### Dropbox Authorization Process

When setting up Dropbox as source migration platform you will need to perform the following process.
Click the key icon next to the 'Authorization Code' field or the 'Get Authorization Code' button.
A window will appear with instructions then proceed by clicking 'Continue' which redirect a login to Dropbox.


- Enter the Dropbox 'Team Admin' email address and password and click 'Sign in' or click 'Sign in with Google' (Team Admin email address is required).
- Once signed in a redirect will occur.
- Click 'Allow', copy the authorization code  then enter it into the 'Authorization Code' area.
- Click 'Next' to test connections, this will ensure everything is working correctly which will pass in all gree.
-  If this does not pass in all green please re-confirm proper credentials have been provided.

---
### Migrating to Google Workspace Section 
 
To migrate files to Google Drive, check the Drive checkbox for each user. Please refer to the 
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">GoogleTenant</a>

*To migrate files to a Google Workspace Team Drive, either select the item you wish to migrate and select 'Migrate as Team Drive' from the actions menu or specify the import type as 'TeamDrive' when adding an item.*

- Enter the ID of the Team Drive in the 'Given Name' field. If the Team Drive specified doesn't exist then it will be created. 
- Use a unique ID in the 'Import Name' field to identify the Team Drive across multiple migrations. 
- Specify a specific folder to migrate from in the 'Documents Path' field, this will migrate only the specified folder and all subfolders. 
- Make sure the migrating account has organizer permissions for any Team Drives that are being migrated.

*To improve performance to Team Drives, configure multiple managers to perform the migration with the configuration setting: Destination Platform Migration Settings > Google Workspace > Team Drive Options > Team Drive Default Organizers*



---

### Migrating to Microsoft 0365 Section  

If Micosoft is the destination Please follow the <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">0365Tenant</a>

Enter your user's full email address within the Export Name field. If you have already created your Office 365 users then you will just need to enter their username.

*If this fails information has been entered incorrectly and will need to be corrected.*

---
### Dropbox Teamspaces

*Dropbox has recently made changes where Team Spaces folder structure may not appear in purple as previously used too. Dropbox support should be able to confirm if this is being used in a client's Dropbox enviroment if encountering errors when moving folders during a migration.*


