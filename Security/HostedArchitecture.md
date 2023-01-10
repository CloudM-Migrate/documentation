---
layout: default
title: Hosted Architecture
parent: Security
nav_order: 2
---

## CloudM Migrate Hosted Architecture & Security

1. [Introduction](#introduction)
2. [Architecture](#architecture)
3. [User Interface](#userinterface)
4. [Endpoints](#endpoints)
5. [Data Storage](#datastorage)
6. [Certification](#certification)
7. [GDPR](#GDPR)
8. [Penetration Testing](#penetrationtesting)

### Introduction <a name="introduction"></a>
The purpose of this document is to provide an overview of the technical architecture of CloudM Migrate Hosted and the security measures used within the software.

### Server Architecture & Security <a name="architecture"></a>

CloudM Migrate Hosted is provided as a SaaS solution. Primary and Secondary servers are automatically provisioned based on migration size. It is useful to understand the architecture and how CloudM Migrate Hosted operates to highlight the security measures implemented.

![image](/Security/dataflowsecurityhosted.png)
        
### User Interface <a name="userinterface"></a>

The user interface is the central point of administration for CloudM Migrate Hosted. Migrations are started and stopped from the interface, and feedback on the progress of the migration is provided through the interface. The user interface is always installed to the same server as the primary server.

### Source and Destination Endpoints <a name="endpoints"></a>

The source and destination endpoints are the platforms that data is being migrated from (Source) and to (Destination). CloudM Migrate Hosted supports a wide range of source endpoints migrating to Google Workspace or Microsoft 365. Communication between secondary servers and source/destination endpoints is encrypted using a combination of HTTPS and native API encryption provided by the endpoints in question.

See below an overview for each source endpoint:

| Source Endpoint | HTTPS Encryption | Native Encryption |
| --- | --- | --- |
| Microsoft Exchange 2000-2019 | Y | NA |
| Microsoft Office 365 | Y | NA |
| Exchange Online Archives | Y | NA |
| OneDrive for Business | Y | NA |
| SharePoint 2007+ | Y | NA |
| Scalix 11 or higher | Y | NA |
| Zimbra 7.2.2 or higher | Y | NA |
| Generic IMAP | NA | Y |
| Google Workspace for Business/Education | Y | NA |
| Box | Y | NA |
| Dropbox for Business | Y | NA |

See below an overview for each destination endpoint:

| Destination Endpoint | HTTPS Encryption | Native Encryption |
| --- | --- | --- |
| Google Workspace for  Business/Enterprise and Google Drive | Y | NA |
| Google Vault | Y | NA |
| Google Cloud Storage | Y | NA |
| Microsoft Office 365 and SharePoint Online | Y | NA |
| Azure Storage | Y | NA |
| Microsoft Exchange 2010 SP2+ | Y | NA |
| Exchange Online Archives | Y | NA |

For details on native encryption please refer to the native API documentation for the endpoint in question.

### Data Storage <a name="datastorage"></a>

Both primary and secondary servers use the following components to temporarily store migration data during a migration.

- Encrypted SQLite databases (AES256)
- Encrypted temporary file storage (AES256)

Other project related data is provided by:

- SQLite databases
- SQL Server - Server 2019 Express is installed by default.
- Redis - Installed as part of the CloudM Migrate installation process.

All of these store non-sensitive data such as item IDs in order to provide reporting on migrations.

Where CloudM Migrate requires a username or password to interact with a system, and stores sensitive data like this, that data is stored encrypted within SQL Server (AES256). SQL Server 2019 Express is installed by default. 

### Certification <a name="certification"></a>
CloudM is an ISO 27001 and Cyber Essentials certified organization.

### GDPR <a name="GDPR"></a>
There is a dedicated Data Protection Manager in-place. The business has the relevant systems to comply with its obligations as a data controller and processor and the requirements around data processing principles, rights of the data subject and security of processing.

### Penetration Testing <a name="penetrationtesting"></a>
Regular third party penetration testing is conducted on the product to verify this protection is in place. Testing takes place every 12 - 18 months by a Crest accredited provider.
