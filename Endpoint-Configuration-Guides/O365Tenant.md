---
layout: default
title: Office 365
parent: Endpoint Configuration Guides
nav_order: 1
---

## Office 365 Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Office 365 as a source or destination endpoint. 

If you are planning a migration the approach matters and prepping your source and destination tenants is fundamental to project success. 

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

CloudM Migrate will need to have the right settings to successfully connect to both the source and destination and those settings differ by endpoint type. All endpoints require the following basics: 

- An account that can access the data
- The source or destination location of that data
- Environment to SaaS access rights for the transfer

For O365 this is defined by the following requirements:

- Authenticaton Method
- Account Used
- O365 Tenant ID
- Test Acount
- O365 to SaaS Access
- The Country of the Destination

### Authentication Method

ClouldM Migrate uses Modern Authentication as a default. If Multi-Factor Authentication is enabled on the endpoint it'll need to be disabled temporarily or a PFX certificate has to be generated for access. As a destination it's recommended to disable MFA. 

If O365 is the source and MFA can not be disabled the Azure Application used to perform migration can be created with a PowerShell script <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/CreateAzureADApplication.ps1">CreateAzureADApplication.ps1</a>. This script will output a PFX Certificate that will need to be uploaded to CloudM Migate.

Once the Azure Application is created, MFA can be renabled. 

### Account Used

In O365 the Global Admin account is needed to provide CloudM Migrate access to everything in scope for migration. Once the Global Admin account is used to create the SaaS application it can be removed from CloudM Migrate. 

### O365 Tenant ID

When you specify the domain CloudM Migrate can auto populate the Tenant ID. If it doesn't auto populate the Tenant ID can be found by in the <a href="https://learn.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id">Tenant Properties</a>

### Test Acount

CloudM Migrate will test the connectivity with a Test Mailbox. Specify a typical mailbox within the migration scope. 

### O365 to SaaS Access

After completing the configuration of the source and destination endpoints a prompt to create the Azure AD Application will be avilable. Select this will begin a connectivity test to both endpoints. Any errors can be resolved by referencing the <a href="https://cloudm-migrate.github.io/documentation/Troubleshooting/O365Endpoint.html">Troubleshooting section</a>.

### The Country of the Destination

If O365 is the destination it important to set the country of the destination O365 is ClouydM Migrate as Azure blocks connections from outside the country. Go to Step 2 on the left and select Platform Configuration and Provisioning. Under the Usage Location select the country that will host the O365 tenant, this is defaulted to the United Kingdom. 


When both your endpoints are ready our Project Migration Guide for your endpoint combination can fill in the next steps toward project completion. 
