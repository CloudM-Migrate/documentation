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

**Install the Google Cloud SDK**
1. Download and install the <a href="https://cloud.google.com/sdk/docs/install">Google Cloud CLI</a>.
2. Run PowerShell as Administrator and initilize the Google Cloud SDK with `gcloud init`.
3. Enter 1 to choose `Re-initialize this configuration [default] with new settings`
4. Enter 2 to choose `Log in with a new account` and login with a Super Admin account. 
5. Select **Allow** to give permissions the SDK permissions to access the Super Admin account. The website will close, return to the PowerShell instance. 
6. Enter Y to create a new project. 
7. Enter a Project Name between 6-30 all lowercase letters. 

>Note: An error `Operation failed: 7: Permission 'resourcemanager.projects.create' denied on parent resource` is returned if not using a Super Admin. 

**Create the Key**
1. Right click and save the <a href="https://bitbucket.org/cloudsols/cloudm-public/raw/9b4bf82a3ff82572e61a1fea877f6d9091958b1d/Migrate/PowerShell/GCP_Configuration.ps1">GCP Configuration script</a> to a working directory.
2. Execute the script in PowerShell as Administrator. 
3. You'll be prompted to enter a Project ID which is the Project Name created previously. 
4. You'll be prompted to enter a Service Account ID which is a new account that will be created and used in GCP. The Service Account ID must between 6-30 all lowercase letters.
5. You'll be prompted to enter the Scope, choose one of the following:
  - All - Recommended for Google to Google
  - Standard (default)
  - SourceLimited
  - DestinationLimited
  - Vault
  - Storage
6. You'll be prompted for the key type, enter P12 or JSON. 
7. You'll be prompted to continue the process by navigating to a URL to Configure OAuth Consent. Do not close PowerShell. 
8. On the OAuth consent page, set the **User Type** to Internal and select Create.
9. Set the **App name** to CloudM Migrate, and add a User Support email and a Developer Contact email address.
10. Navigate to Security > API Controls > Domain-wide Delegation page, select **Add New**.
11. The PowerShell script will have output the ClientID and OAuth Scopes to copy and paste in the Add New dialog. 
12. Select **Authorize**. 
13. You can now add the Service Account email to CloudM Migrate. 
14. The P12 or JSON Access key will be located under C:\CloudM\GCPConfig and can be uploaded into CloudM Migrate. 

> Note: Replication can cause a delay of 2 hours before these can be used to migrate data. 
