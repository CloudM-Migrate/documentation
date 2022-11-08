---
layout: default
title: Google Vault
grand_parent: Endpoint Configuration Guides
parent: Other Source Endpoints
nav_order: 6
---

## Google Vault Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure Google Vault as a source or destination endpoint. 

For Google Vault this is defined by the following requirements:

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

### Throttling 

Google Vault is heavly throttled by default with limits to <a href="https://developers.google.com/vault/limits">20 active</a> export threads per organization. You can <a href="https://cloud.google.com/docs/quota#requesting_higher_quota">request</a> these limits be raised but it takes a few days for the changes to take effect. 

### Authentication

For either source or destination the Google Vault endpoint requires the source/destination Domain and the Super Administrator account. 

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

**NOTE:** Replication can cause a delay of 2 hours before these can be used to migrate data. 

### Google Vault Throttling

Google Vault is heavliy throttled by default. Google has <a href="https://developers.google.com/vault/limits">options</a> for lifiting this throttling for an additional change. 
  
### Chat History
  
By default Classic Chat History is not migrated. To migrate Classic Chat History as email on the destination enable the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/GoogleVaultSourceAO.html#chathist">Migrate Chat History</a> option.
 
### Spam
  
By default SPAM is not migrated however it's possible to include SPAM by enabling the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/GoogleVaultSourceAO.html#export-spam-emails-">Export Spam Emails</a> option.

