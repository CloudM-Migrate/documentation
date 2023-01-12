---
layout: default
title: Google
parent: Endpoint Configuration Guides
nav_order: 2
---

## Google Workspace Endpoint Configuration
{: .no_toc }

This guide will show how to configure Google Workspace as a source or destination endpoint. 

For Google this is defined by the following requirements:

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

Upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the VM. Select the region closest to the destination. 

### Authentication Method

Google endpoints are accessed by a Super Admin account. 

### Service Account and P12 or JSON Access Key for Google to SaaS Access

A Service Account needs to be created with the correct scopes for the data access and an associated P12 or JSON key. This account is entered in the endpoint configuration and the P12 or JSON key file is uploaded into CloudM Migrate. 

The whole process can be performed via a PowerShell script. 

1. Download and install the <a href="https://cloud.google.com/sdk/docs/install">Google Cloud CLI</a>.
2. Right click and save the <a href="[https://bitbucket.org/cloudsols/cloudm-public/src/main/Migrate/PowerShell/GCP_Configuration.ps1](https://bitbucket.org/cloudsols/cloudm-public/raw/9b4bf82a3ff82572e61a1fea877f6d9091958b1d/Migrate/PowerShell/GCP_Configuration.ps1)">GCP Configuration script</a> to a working directory.
3. Run PowerShell as Administrator and execute the script. 
4. You'll be prompted to enter a Project ID and a Service Account ID.
5. You'll be prompted to enter the Scope, choose one of the following:
  - All - Recommended for Google to Google
  - Standard
  - SourceLimited
  - DestinationLimited
  - Vault
  - Storage
6. You'll be prompted for the key type, enter P12 or JSON. 
7. You'll be prompted to continue the process by navigating to a URL to Configure OAuth Consent. Do not close PowerShell. 
8. On the OAuth consent page, set the User Type to Internal and select Create.
9. Set the App name to CloudM Migrate, and add a User Support email and a Developer Contact email address.
10. Navigate to Security > API Controls > Domain-wide Delegation page, select Add New.
11. The PowerShell script will have output the ClientID and OAuth Scopes to copy and paste in the Add New dialog. 
12. Select Authorize. 
13. You can now add the Service Account email to CloudM Migrate. 
14. The P12 or JSON Access key will be located under C:\CloudM\GCPConfig and can be uploaded into CloudM Migrate. 

> **Note**: Replication can cause a delay of 2 hours before these can be used to migrate data. 
