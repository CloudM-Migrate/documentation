---
layout: default
title: Teams to Teams
grand_parent: Migration Project Guides
parent: O365
nav_order: 3
has_children: false
has_toc: false

---

## Teams to Teams
{: .no_toc }

Before starting your migration project, make sure you have setup both <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> endpoints using the configuration guides. Be sure to validate both tenants have passed their connectivity tests with no errors. 

When doing a Teams to Teams migration it's recommend to have already created the users on the destination tenant. If this is not done it's possible for a channel to be created without the correct Team Owner. 

<a name="top"></a>
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Graph API
{: .no_toc }

In order to get all messages from all chats that a user is a participant in, including one-on-one chats, channel chats, and meeting chats the Graph API will be required to use. This is a <a href="https://learn.microsoft.com/en-us/graph/teams-protected-apis">protected API</a> and will require <a href="https://learn.microsoft.com/en-us/graph/teams-licenses">licensing and billing</a> information provided to Microsoft. 

To <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/O365DestinationAO.html#rehydrate-teams-private-chats-">Rehydrate Teams Private Chats</a> it is required to use the Graph API. The majority of 1 to 1 chats are migrated to the users mailbox in a folder, only recent 1 to 1 chats are rehydrated into Teams if this option is enabled. 

By default, CloudM Migrate uses the EWS protocol to migrate Teams data which has no additional cost. 

## Delegated Permissions
{: .no_toc }

In order to migrate Private Chat or 1 on 1 chats with **Rehydrate Teams Private Chats** enabled to your Office 365 environment using modern authentication, you must install an Azure Active Directory application to grant API permissions. 

CloudM Migrate can create this application for you. Select the **Create Azure AD Delegated Application** button to create the application. Once the application has been created successfully a new button will be displayed, select **Consent Delegated Application** to add the specific scopes for delegating permissions to the specified admin account.

If the Azure AD Application is being created by the <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/CreateAzureADApplication.ps1">CreateAzureADApplication.ps1</a> PowerShell script a second script, <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/CreateAzureADDelegatedApplication.ps1">CreateAzureADDelegatedApplication.ps1</a>, can be used for the Delegate permissions scope.

---

## Standard Migration 
{: .no_toc }
[Back to Top](#top)

This process assumes that the destination tenant contains all the users and have already had mailboxes provisioned. A first migration pass is performed followed by a Delta with a Finalize Migration switch to make the Teams instance available to end users.

### First Migration Pass
[Back to Top](#top)

In CloudM Migrate go to **Step 3** and use the **Filter** option to select **Microsoft Teams** under Export Type. Select the selection column header and choose **Select All From Filter**. Select **Create Batch** and name it MS Teams under **Configuration Name**.

To validate only Teams are in the batch, select Export and verify the ExportObjectType column only lists Microsoft Teams. 

To migrate Teams data, validate the following item columns are selected:

- Mail 
- Calendar 
- OneDrive
- Conversations

Select **Step 1** for the **Source Configuration** and then select **Advanced Settings**. Navigate to **Microsoft Teams/Groups** and turn on the option **Migrate Team Channel Tabs**. 

Select **Step 2** for the **Destination Configuration** and then select **Advanced Settings**. Navigate to **Microsoft Teams/Groups** and turn on the option **Teams Direct Migration**. Validate that the **Rehydrate Teams Private Chats** is off as these are done in the Delta Pass to avoid duplication. 
**NOTE:** The **Teams Direct Migration** option will create the Teams on the destination in MigrationMode. This restricts visibility and access to the Team on the destination. If the Team already exists and this option in enabled, the migration will fail as an existing Team can't be set to MigrationMode. To migrate to an existing Team disable the Team Direct Migration option. 

Validate the **Finalize Teams Direct Migration** is set to Disabled. 

Execute the migration by selecting the paper airplane on the left and then selecting **Start**. 

### Delta Pass and Finalizing 
[Back to Top](#top)

After the first pass is completed you can set a date for the destination Teams to go live for your users. To do so, go to the batch previously created for the first pass and then go to **Step 2**. Select **Advanced Settings** and set the option **Finalize Teams Direct Migration** to Enabled. 

CloudM Migrate has the option to rehydrate the last ten messages of users 1 to 1 chats. It's recommended to do this during the Delta Pass to avoid duplication. To set this feature go to **Step 2** and expand the **Advanced Settings**. Navigate to **Microsoft Teams/Groups** and enable the **Rehydrate Teams Private Chats** option. 

Execute the migration by selecting the paper airplane on the left and then selecting Start. When this pass is completed, the Teams will be live on the destination.




