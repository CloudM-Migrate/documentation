---
layout: default
title: Migrate a Google Mailbox and MyDrive to O365
parent: Getting Started Guides
nav_order: 5
---

## How to Migrate a Google Mailbox and MyDrive to O365

1. [Overview](#overview)
2. [Google Source](#source)
3. [O365 Destination](#destination)
4. [Creating a Migration Project](#project)

### Overview <a name="overview"></a>

This document will give an overview on to use CloudM Migrate to perform a test mailbox migration with files on MyDrive. Before attempting a migration you'll need to gather some information and prepare the source and destination tenants.

### Google Workspace Source <a name="source"></a>

A Domain Admin account will be needed in the source and a Service Account will need to be created for use in CloudM Migrate. When creating the Service Account a P12 key will need to be generated which you will upload into CloudM Migrate.

[Here are detailed instructions for creating the Service Account and P12 Private Key.](https://support.cloudm.io/hc/en-us/articles/360021526559-Google-Workspace-to-Google-Workspace-migration-self-hosted-#ManualProcess)

### O365 Destination <a name="destination"></a>

You'll need to have an existing O365 tenant with at least one target test mailbox already created. 

A Global Admin account will be needed in the destination and Multi-Factor Authentication will need to be temporarily disabled when creating the migration project within CloudM Migrate. For the MyDrive to OneDrive content you'll need the SharePoint Admin URL.

With this information you are ready to create a CloudM Migrate project.

### Creating a Migration Project <a name="project"></a>

A CloudM sales representative can provide you some testing licenses. When you receive the license it will contain a link to access CloudM Migrate.

Feel free to explore and when ready select the **Orange Plus** symbol in the upper right corner and then **Create a New Project** to begin creating a migration project.

Select source platform as **Google Workspace**. Enter the source **Domain**, **Service Account Email Address, Admin Username** and the **Private Key** you previously created. 

Select **Next** and CloudM Migrate will validate it can access the source.

Select the **Destination Platform** type as **Microsoft Office 365** and enter the **Global Admin Username**, **Global Admin Password** and the **Test Username** which is the precreated test mailbox. At the bottom of the destination detail expand the section labeled **Platform Configuration and Provisioning** and make sure the field labeled **Usage Location** is set to the country the destination is located, by default it will be set to the United Kingdom.

Now is when Multi-Factor Authentication in O365 will need to be disabled so CloudM Migrate can contact the destination tenant. Typically you'll want to set the **Authentication Method** to **Modern**. When MFA is disabled select the **Create Azure AD Application** to generate the PFX Certificate and Tenant ID. 

Under **Advance Settings** validate the **SharePoint Admin URL** is correct. 

Select **Next** and then the destination connection will validated. 

If successful you can now re-enable Multi-Factor Authentication.

Select **Next** and now you are able to select users to migrate. Select **Add items to migrate** and then **Get items from source**.

After the list populates, select a single mailbox to migrate as a test. The license provided to you will be consumed by this test migration.

The **Export Field** column will show the source addresses and the **Import Field** will display the destination address.

On right side of the line that contains your test mailbox unselect all options besides **Mail, Contacts, Calendar, Tasks and Drive**.

Select the **Save** option under the Actions column to save changes

Validate that only your test mailbox has the **slider in orange** under the Migrate column.

On the left select the **Paper Airplane** to view the migration batch summary.

Select **Start** and then **Start Now** to begin the test migration.

CloudM Migrate will now show you the status of the migration. When completed you can see details of the migration by selecting **More Statistics** and you can view the destination mailbox to validate all mailbox items were successfully migrated.
