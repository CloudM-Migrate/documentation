---
layout: default
title: Box
parent: Endpoint Configuration Guides
nav_order: 17
---

## Box Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Box as a source endpoint. 

For Box this is defined by the following requirements:

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

### Creating a Box Application for a Client ID and Client Secret Key

1. Log into your Box account as an administrative user for your organization: https://app.box.com/developers/console
2. Navigate to **Dev Console**.
3. Navigate to **My Apps**.
4. Select Create **New App**.
5. Select **Enterprise Integration**.
6. On the **Authentication Method** screen, select **Standard OAuth 2.0 (User Authentication)**.
7. Give your application a name such as 'CloudM Migration'.
8. In the section OAuth 2.0 Credentials copy the Client ID and Client Secret Key values.
9. Update the Redirect URI field with the below URL: https://oauth.pingone.com/ocs/ppm/rest/v1/oauth/oastempcredresponse/
10. Select **Save Changes**. 

---
### Migrating to Google Drive
 

To migrate files to Google Drive, check the Drive checkbox for each user. Please refer to the 
<a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">GoogleTenant</a>


Click on Add items to migrate and select ‘Add Shared Drive' from the dropdown menu.
Specify the ID of the Shared Drive you wish to migrate from in Export Name.
Also specify any folder within a Shared Drive. This is done by specifying the folder ID in the 'Documents Path' field. 
Make sure the migrating account has Manager permissions for any Shared Drives that are being migrated.
To migrate files to a Google Workspace Shared Drive: 

Either select the item you wish to migrate and select 'Migrate as Shared Drive' from the actions menu, or specify the import type as 'Shared Drive' when adding an item. Specify the ID of the Shared Drive in the ‘Import Name’ field or the name of the Team Drive in the ‘Given Name’ field. If the Shared Drive specified doesn't exist, then it will be created. 
Enter a unique ID in the 'Import Name' field to identify the Shared Drive across multiple migrations. 
Enter a specify a specific folder to migrate from in the 'Documents Path' field, and this will migrate only the specified folder and all subfolders. 
Enter specify a specific folder to migrate to in the 'Documents Destination Path' field. Documents will be migrated to the specific subfolder in the Shared Drive.
Finally, you must make sure your migrating account has Manager permissions for any Shared Drives that are being migrated.
To improve performance to Shared Drives: 

Configure multiple Managers to perform the migration with the configuration settings.

---

### Migrating to Microsoft OneDrive/SharePoint

If Micosoft is the destination Please follow the <a href= https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html/a>0365Tenant 

Migrating files to Microsoft 365, Only use the Sharepoint Admin URL. The URL will look similar to the URL below:

https://tenant-admin.sharepoint.com. 

To input the URL, click Advanced Settings and locate Sharepoint Admin URL under the OneDrive for Business/SharePoint settings.

Once you have configured the Platform settings, click on Next. CloudM Migrate will now perform a small connection test to verify that the details you have entered are correct which check in green.

If this fails,something has been entered something incorrectly.


### Address replacement section reminder ###

If changing email addresses as part of the migration verify that the domain names are correct. Also specify <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ProjectAdvancedOptions.htmll">Address Replacement</a> in the respective section of the advanced settings.

Target Audience permissions can also be migrated but must be replaced using Address Replacements in order to migrate successfully. If present on the source but not migrated to the destination platform, any items shared with it will be shared back to the source Target Audience.
