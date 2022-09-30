---
layout: default
title: Google
parent: Endpoint Configuration Guides
nav_order: 2
---

## Google Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Google as a source or destination endpoint. 

If you are planning a migration the approach matters and prepping your source and destination tenants is fundamental to project success. 

CloudM Migrate will need to have the right settings to successfully connect to both the source and destination and those settings differ by endpoint type. All endpoints require the following basics: 

- An account that can access the data
- The source or destination location of that data
- Environment to SaaS access rights for the transfer
- What region should host the VM used to facilate the migration

For Goolge this is defined by the following requirements:

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

### What Region for the Virtual Machine

Upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the VM. Select the region closest to the desintation. 

### Authentication Method

Google endpoints are accessed by a Super Admin account. 

### Service Account and P12 Access Key for Google to SaaS Access

A Service Account needs to be created with the correct scopes for the data access and an associated P12 key. This account is entered in the endpoint configuration and the P12 key file is uploaded into CloudM Migrate. 

The whole process can be performed via a PowerShell script. 

1. Download and install the <a href="https://cloud.google.com/sdk/docs/install">Google Cloud CLI</a>.
2. Download the <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/GCP_Configuration.ps1">GCP Configuration script<a/>.
3. Run PowerShell as Admininstrator and execute the script. 
4. You'll be prompted to enter a Project ID and a Service Account ID which are arbitrary names. 
5. You'll be prompted to enter the Scope, choose one of the following:
  - All - Recommended for Google to Google
  - Standard
  - SourceLimited
  - DestinationLimited
  - Vault
  - Storage
6. You'll be prompted to continue the process by navigating to a URL to Configure OAuth Consent. Do not close PowerShell. 
7. On the OAuth consent page, set the User Type to Internal and select Create.
8. Set the App name to CloudM Migrate, and add a User Support email and a Developer Contact email address.
9. Navigate to Security > API Controls > Domain-wide Delegation page, select Add New.
10. The PowerShell script will have output the ClientID and OAuth Scopes to copy and paste in the Add New dialog. 
11. Select Authorize. 
12. You can now add the Service Account email to CloudM Migrate. 
13. The P12 Access key will be located under C:\CloudM\GCPConfig and can be uploaded into CloudM Migrate. 

### Service Account Scopes

### Service Account P12 Access Key

