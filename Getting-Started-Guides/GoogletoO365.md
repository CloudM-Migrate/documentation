---
layout: default
title: Migrate a Google Mailbox and MyDrive to O365
paremt: Getting Started Guides
nav_order: 1
---


## How to Migrate a Google Mailbox and MyDrive to O365

1. [Overview](#overview)
2. [Google Source](#source)
3. [O365 Destination](#destination)
4. [Creating a Migration Project](#project)

### Overview <a name="overview"></a>

This document will give an overview on to use CloudM Migrate to perform a test mailbox migration with files on MyDrive. Before attempting a migration you'll need to gather some information and prepare the source and destination tenants.

### Google Source <a name="source"></a>

A Domain Admin account will be needed in the source and a Service Account will need to be created for use in CloudM Migrate. When creating the Service Account a P12 key will need to be generated which you will upload into CloudM Migrate.

[Here are detailed instructions for creating the Service Account and P12 Private Key.](https://support.cloudm.io/hc/en-us/articles/360021526559-Google-Workspace-to-Google-Workspace-migration-self-hosted-#ManualProcess)

### O365 Destination <a name="destination"></a>

A Global Admin account will be needed in the destination and Multi-Factor Authentication will need to be temporarily disabled when creating the migration project within CloudM Migrate. The Tenant ID will also be required in the migration project. For the MyDrive to OneDrive content you'll need the SharePoint Admin URL.

With this information you are ready to create a CloudM Migrate project.

### Creating a Migration project <a name="project"></a>

A CloudM sales representative can provide you some testing licenses. When you receive the license it will contain a link to access CloudM Migrate.

Feel free to explore and when ready select the **Orange Plus** symbol in the upper right corner and then **Create a New Project** to begin creating a migration project.

Select the **Destination Platform** type as **Microsoft Office 365** and enter the target **Domain**. The **Configuration Name** is the name of the Batch you are creating, call it Test.

Enter in the **License Key** that was provided to you and select **Continue**.

In the first screen you'll populate the information you previously gathered for the Google source, the domain name, the service account and upload the private key. The **Configuration Name** is the name of the Batch you are creating, call it Test.

Select **Next** and CloudM Migrate will validate it can access the source.

Select **Next** and then select O365 as the destination tenant you'll be migrating too.

At the bottom of the destination detail expand the section labeled **Platform Configuration and Provisioning** and make sure the field labeled **Usage Location** is set to the country the destination is located, by default it will be set to the United Kingdom.

Under **Advance Settings** populate the **SharePoint Admin URL**.

Now is when Multi-Factor Authentication will need to be disabled so CloudM Migrate can contact the destination tenant. Typically you'll want to set the **Authentication Method** to **Modern**.

Select **Create Azure AD Application** and then select it a second time to start the validation of the destination. If successful you can now re-enable Multi-Factor Authentication.

Select **Next** and now you are able to select users to migrate. Select **Add items to migrate** and then **Get items from source**.

After the list populates, select a single mailbox to migrate as a test. The license provided to you will be consumed by this test migration.

The **Export Field** column will show the source addresses and the **Import Field** will display the destination address.

On right side of the line that contains your test mailbox unselect all options besides **Mail, Contacts, Calendar, Tasks and OneDrive**.

Select the **Save** option under the Actions column to save changes

Validate that only your test mailbox has the **slider in orange** under the Migrate column.

On the left select the **Paper Airplane** to view the migration batch summary.

Select **Start** and then **Start Now** to begin the test migration.

CloudM Migrate will now show you the status of the migration. When completed you can see details of the migration by selecting **More Statistics** and you can view the destination mailbox to validate all mailbox items were successfully migrated.
