---
layout: default
title: Dropbox
grand_parent: Endpoint Configuration Guides
parent: Other Source Endpoints
nav_order: 2
---

## Dropbox Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Dropbox as a source endpoint. 

For Dropbox this is defined by the following requirements:

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

When setting up Dropbox as source migration platform please perform the following process. Click the key icon next to the **Authorization Code** field or the **Get Authorization Code** button. A window will appear with instructions then proceed by clicking **Continue** which redirect to Dropbox.

- Enter the Dropbox **Team Admin** email address and password and click **Sign in** (Team Admin email address is required).
- Once signed in redirect will occur.
- Select **Allow**, copy the authorization code  then enter it into the **Authorization Code** area.
- Select **Next** to test connections, this will ensure everything is working correctly which will pass in all green.

If this fails validate the information has been entered correctly.

---
### Migrating to Google Workspace Section 
 
To migrate files to Google Drive, check the Drive checkbox for each user. For Google as the destination refer to the <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/GoogleTenant.html">Google Tenant Endpoint Configuration</a>

To migrate files to a Google Workspace Team Drive, either select the item you wish to migrate and select **Migrate as Team Drive** from the actions menu or specify the import type as **Team Drive** when adding an item.

- Enter the ID of the Team Drive in the **Given Name** field. If the Team Drive specified doesn't exist then it will be created. 
- Use a unique ID in the **Import Name** field to identify the Team Drive across multiple migrations. 
- Specify a specific folder to migrate from in the **Documents Path** field, this will migrate only the specified folder and all subfolders. 
- Make sure the migrating account has organizer permissions for any Team Drives that are being migrated.

To improve performance to Team Drives, configure multiple managers to perform the migration with the configuration setting: Destination Platform Migration Settings > Google Workspace > Team Drive Options > Team Drive Default Organizers.

---

### Migrating to Microsoft 0365 Section

For Microsoft as the destination refer to to the <a href="https://docs.cloudm.io/Endpoint-Configuration-Guides/O365Tenant.html">0365 Tenant Endpoint Configuration</a>

Enter the users full email address within the Export Name field. If this has already been created please use the Office 365 users you will need to enter their username.

If this fails validate the information has been entered correctly.

---

### Dropbox Teamspaces

Dropbox has recently made changes to the Team Spaces folders structure an may not appear displayed in purple.  Dropbox team spaces can be identified by running the following curl command:

`curl -X POST https://api.dropboxapi.com/2/team/team_folder/list ^ --header "Authorization: Bearer [BearerID] ^ --header "Content-Type: application/json" ^ --data "{\"limit\": 100}"`

Note that some Dropbox Business teams use the <a href="https://www.dropbox.com/developers/documentation/http/teams">Team Space</a>. Accessing its contents requires passing the Dropbox-API-Path-Root header to calls to the <a href="https://www.dropbox.com/developers/documentation/http/teams#documentation">Dropbox User API</a>.


