---
layout: default
title: Google Cloud Storage
parent: Other Source Endpoints
grand_parent: Endpoint Configuration Guides
nav_order: 10
---

## Google Cloud Storage Endpoint Configuration
{: .no_toc }

This guide will show how to configure Google Cloud Storage as a source or destination endpoint. 

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

If using CloudM Migrate Hosted, upon receipt of the license for CloudM Migrate you'll have a link to access the application. When selecting the link a prompt will come up asking to choose which region of the world the migration will be performed for the purpose of landing the VM. Select the region closest to the destination. 

### Prerequisites

- An account in GCP with permissions to create a project (resourcemanager.projects.create role) or owner on existing project.
- The ability to run Powershell Script as Administrator.
- A browser window open and authenticated into the GCP tenant. This must be the last browser tab you have used.

### Service Account and P12 or JSON Access Key for Google Cloud Storage

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
1. Right click and save the <a href="https://bitbucket.org/cloudsols/cloudm-public/src/main/Archive/PowerShell/GCP_Storage_Configuration.ps1">GCP Configuration script</a> to a working directory.
2. Execute the script in PowerShell as Administrator. 
3. You'll be prompted to enter a Project ID which is the Project Name created previously. 
4. You'll be prompted to enter a Service Account ID which is a new account that will be created and used in GCP. The Service Account ID must between 6-30 all lowercase letters.
5. You'll be prompted to enter a region. Enter either us-central1 or europe-west1, depending on the region that you want to store your data in.
6. You'll be prompted to enter a BucketName. enter a name for your storage bucket, adhering to the naming conventions outlined in <a href="https://cloud.google.com/storage/docs/naming-buckets">this article</a> from Google. 
7. The Powershell script will now create the Service Account and Bucket. This may take a few minutes.
8. Once the Powershell has stopped, you can add a KeyName. This step is optional, but, if you do enter a Key Name, it must be between 6 and 30 letters, digits, hyphens or underscores. It must start with a lower case letter, followed by one or more alphanumerical characters that can be separated by hyphens or underscores. It cannot have a trailing hyphen or underscore. 
9. Optionally, set the StorageClass for the Bucket Storage. It must be one of ‘STANDARD’, ‘NEARLINE’, ‘COLDLINE’ or ‘ARCHIVE’.
10. Optionally, set the ServiceAccountKeyType. It must be either ‘json’ or ‘p12’.
11. Now, on the Output Path line, specify where the JSON Key and Log will be exported to on your computer (e.g. C:\\CloudM GCPConfig). The path will default to USERHOME GCPConfig.
12. The Powershell will run and provide the following details (that you should note down)
- Service Account Email Address
- Path to Service Account Json key
- Bucket Url
- KMS Key Path

> Note: Replication can cause a delay of up to 2 hours before these can be used to migrate data. 
