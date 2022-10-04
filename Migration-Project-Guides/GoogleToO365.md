---
layout: default
title: Google to O365
parent: Migration Project Guides
nav_order: 1
has_children: True
has_toc: false

---

## Google to O365
{: .no_toc }

Before starting your migration project, make sure you have have setup <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/GoogleTenant.html">Google</a> and <a href="https://cloudm-migrate.github.io/documentation/Endpoint-Configuration-Guides/O365Tenant.html">O365</a> using their repective configuration guides. Both have passed their connectivity tests with no errors. 

This guide will present the steps nessescary to perform a migration with relating child documents on each data type. There are many options for customizing the migration but for the purposes of this guide it's assumed this is a typical full migration. 

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

### Adding Users

On Step 3 on the left, select the Add items to migrate for options on how to collect targeted items to migrate from Google. The following options will be avilable:

- Get items from source - This is fetch where CloudM Migrate will attempt to list all supported items within scope. 
- Bulk add/import items - Provide CloudM Migrate a <a href="https://github.com/CloudM-Migrate/documentation/blob/main/assets/bulkimport.csv">CSV</a> of targeted items. 
- Add User - Add a specific user to the project. 
- Add Resource -  
- Add Shared Drive - Add a file share to the project.
- Add Group - 

### Scanning the Source 

Go to Step 5. do the scan. open the file info, look for red users and solve the issues that are found. trncate long folder paths, dead users objects, external file shares. 

### Purchasing Licensing for O365

Number of users based on scan. Type isup to them. 

If it's using the same domain, you can place the vanity domain in the destination. 

### Setting the domain on the O365 tenant

Technet Article 

### Create Users in Desitnation

Technet article

### Provision OneDrive

Technet article

### Provision Archives for users 
 
Technet Article 

### Address Replacement for different alias 

If you want to change the alias on destination. Change in the user list, step 3. 

Also change in advance project settings, stop getting confused, this is only alias. 

## Start Migration

### Creating the first Batch

It's recommended to do email and documents in your first batch after waiting 24 hours after provisioning them. 

Link to sub document for the settings

#### Date Ranges First Batch

We also recommend specifiy the date range of every older then the last 30 days. 

Link to sub document for the settings

### Second Batch Shared Drive to Sharepoint 

Use filter to select the shared drives. 

### Cutover 

#### Delta Sync

### Statistics and Summary
