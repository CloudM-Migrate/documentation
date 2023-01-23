---
layout: default
title: M365
parent: Endpoint Configuration Guides
tag: M365
nav_order: 1
---

## Microsoft 365 Endpoint Configuration
{: .no_toc }

This guide will show how to configure Microsoft 365 as a source or destination endpoint. 

For M365 this is defined by the following requirements:

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

### What Region for the Virtual Machine

Upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the Virtual Machine. Select the region closest to the desintation. 

### Authentication Method

ClouldM Migrate uses Modern Authentication as a default. If Multi-Factor Authentication (MFA) is enabled on the endpoint it'll need to be disabled temporarily or a Personal Exchange Format (PFX) certificate has to be generated for access. As a destination it's recommended to disable MFA. 

If M365 is the source and MFA can not be disabled the Azure Application used to perform migrations can be created with a PowerShell script <a href="https://bitbucket.org/cloudsols/cloudm-public/raw/9b4bf82a3ff82572e61a1fea877f6d9091958b1d/Migrate/PowerShell/CreateAzureADApplication.ps1">CreateAzureADApplication</a>. This script will output a PFX Certificate that will need to be uploaded to CloudM Migate.

During script execution you will be prompted to authenticate, be sure to leave the PowerShell instance running and keep it open to reference the output. 

Once the Azure Application is created, MFA can be renabled. 

### Account Used

In M365 the Global Admin account is needed to grant CloudM Migrate access to the data in scope for migration. Once the Global Admin account is used to create the Azure AD application it can be removed from CloudM Migrate. 

### M365 Tenant ID

When you specify the domain CloudM Migrate can auto populate the Tenant ID. If it doesn't auto populate the Tenant ID can be found in the <a href="https://learn.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id">Tenant Properties</a>.

### Test Account

CloudM Migrate will test the connectivity with a Test Mailbox. Specify a typical mailbox within the migration scope. 

### The Country of the Destination

If M365 is the destination it's important to set the country of the destination M365 tenant for ClouldM Migrate as Azure blocks connections from outside the country. Go to Step 2 on the left and select Platform Configuration and Provisioning. Under the Usage Location select the country that will host the M365 tenant, this is defaulted to the United Kingdom. 

### M365 to SaaS Access

After completing the configuration of the M365 as source and/or destination endpoint(s) a prompt to create the Azure AD Application will be available. Select this to begin the application creation and the connectivity testing to the tenant. Any errors can be resolved by referencing the <a href="https://cloudm-migrate.github.io/documentation/Troubleshooting/O365Endpoint.html">Troubleshooting section</a>.

For reference purposes, here is what the application will give itself access to:

| GUID | Description | 
|---|---|
| 75359482-378d-4052-8f01-80520e7db3cd | Read and write files in all site collections |
5b567255-7703-4780-807c-7be8301ae99b | Read all groups    
62a82d76-70ea-41e2-9197-370581804d09 | Read and write all groups 
e2a3a72e-5f79-4c64-b1b1-878b674786c9 | Read and write mail in all mailboxes   
3aeca27b-ee3a-4c2b-8ded-80376e2134a4 | Read all notes 
9492366f-7969-46a4-8d15-ed1a20078fff | Read and write all Sites
df021288-bdef-4463-88db-98f22de89214 | Read all users' full profiles   
913b9306-0ce1-42b8-9137-6a7df690a760 | Read all place
35930dcf-aceb-4bd1-b99a-8ffed403c974 | Read and write all ChannelMember
7ab1d382-f21e-4acd-a863-ba3e13f7da61 | Read directory data                                   
294ce7c9-31ba-490a-ad7d-97a7d075e4ed | Read and write all Chat 

When both your endpoints are ready our <a href="https://cloudm-migrate.github.io/documentation/Migration-Project-Guides/MigrationProjectGuides.html">Project Migration Guides</a> for your endpoint combination can fill in the next steps toward project completion. 

- <a href="https://cloudm-migrate.github.io/documentation/Migration-Project-Guides/GoogleToM365.html">Google to M365</a>
- <a href="https://cloudm-migrate.github.io/documentation/Migration-Project-Guides/M365ToM365.html">M365 to M365</a>
- <a href="https://cloudm-migrate.github.io/documentation/Migration-Project-Guides/TeamstoTeams.html">Teams to Teams</a>
