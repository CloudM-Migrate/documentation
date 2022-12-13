---
layout: default
title: Self Hosted Architecture & Security
parent: Security
nav_order: 1
---

## CloudM Migrate Self Hosted Architecture & Security

1. [Introduction](#introduction)
2. [Architecture](#architecture)
3. [User Interface](#userinterface)
4. [Servers](#servers)
5. [Endpoints](#endpoints)
6. [Data Storage](#datastorage)
7. [Certification](#certification)
8. [GDPR](#GDPR)
9. [Penetration Testing](#penetrationtesting)

### Introduction <a name="introduction"></a>

The purpose of this document is to provide an overview of the technical architecture of CloudM Migrate Self Hosted and the security measures used within the software.

Our Migration servers are configured in a way that you DO NOT have to open any inbound ports for our tool to work. If you do expose the server to inbound traffic on the internet we are not responsible for your network's security.

### Server Architecture & Security <a name="architecture"></a>

CloudM Migrate Self Hosted can be installed and used in a single or multi-server environment, it is useful to understand the architecture and how CloudM Migrate Self Hosted operates to highlight the security measures implemented.

![image](/Security/dataflowsecurity.png)
          
### User Interface <a name="userinterface"></a>

The user interface is the central point of administration for CloudM Migrate Self Hosted in both single and multi-server modes. Migrations are started and stopped from the interface, and feedback on the progress of the migration is provided through the interface. The user interface is always installed to the same server as the primary server.

### Primary & Secondary Servers <a name="servers"></a>

The primary server is the main point of control for the migration processes. The user interface communicates with the primary to start and stop migrations. The primary server allocates individual data items to secondary servers and provides control and load balancing of migrations.

Secondary servers perform the actual migration of data from the source endpoint to the destination endpoint. They are controlled by the primary server. Multiple secondary servers can be incorporated to provide scalability for migrations requiring additional threads to increase throughput or migrate large numbers of items. Secondary servers are installed within the same network as the Primary server, whether that be on a migration farm built within your own network infrastructure or built on Google Cloud Compute, Microsoft Azure or Amazon EC2.

Communication between primary and secondary servers is not encrypted as they should be built within the same network infrastructure. The communication between primary and secondary servers contains no user data and is only used to provide command and control.

Both primary and secondary servers communicate with the CloudM Migrate Self Hosted licensing server using HTTPS (TLS 1.2) encryption.

It is recommended that both primary and secondary servers meet the following requirements:

- 64 bit Operating system: Windows 10/Windows Server 2016+ (Clean build recommended)

- NET Framework 4.8

- Primary Server - recommended system specification:
  - 3GHz 8 Core Processor or better 
  - 200+GB Disk space
  - 16+GB Memory

- Secondary Server - recommended system specification:
  - 3GHz 4 Core Processor or better
  - 100GB Disk space
  - 8+GB Memory

CloudM Migrate Self Hosted migrates data over HTTPS, and therefore, outbound port 443 can be used on the primary server and secondary servers.

### Source and Destination Endpoints <a name="endpoints"></a>

The source and destination endpoints are the platforms that data is being migrated from (Source) and to (Destination). CloudM Migrate Self Hosted supports a wide range of source and destination endpoints for migration from almost any platform. Communication between secondary servers and source/destination endpoints is encrypted using a combination of HTTPS and native API encryption provided by the endpoints in question.

See below an overview for each source endpoint:

| Source Endpoint | HTTPS Encryption | Native Encryption |
| --- | --- | --- |
| Novell GroupWise 6.5.6 to 2012 | NA | Y |
| Novell GroupWise 2014 or higher | Y | Y |
| Lotus Notes 6.0.2 or higher | NA | Y |
| Microsoft Exchange 2000-2016 | Y | NA |
| Microsoft Office 365 | Y | NA |
| Exchange Online Archives | Y | NA |
| PST archives | NA | NA |
| OneDrive for Business | Y | NA |
| Scalix 11 or higher | Y | NA |
| Zimbra 7.2.2 or higher | Y | NA |
| Generic IMAP | NA | Y |
| Google Workspace for Business/Education | Y | NA |
| File System | NA | NA |
| Mail Archives (mbox, EML) | NA | NA |
| Box | Y | NA |
| Dropbox for Business | Y | NA |

See below an overview for each destination endpoint:

| Destination Endpoint | HTTPS Encryption | Native Encryption |
| --- | --- | --- |
| Google Workspace for  Business/Enterprise and Google Drive | Y | NA |
| Google Vault | Y | NA |
| Microsoft Office 365 and SharePoint Online | Y | NA |
| Microsoft Exchange 2007+ | Y | NA |
| SharePoint 2007+ | Y | NA |

For details on native encryption please refer to the native API documentation for the endpoint in question.

### Data Storage <a name="datastorage"></a>

Both primary and secondary servers use the following components to temporarily store migration data during a migration.

- Encrypted SQLite databases (AES256)
- Encrypted temporary file storage (AES256)

Other project related data is provided by:

- SQLite databases
- SQL Server - Server 2019 Express is installed by default, or a customer can specify their own SQL Server.
- Redis - Installed as part of the CloudM Migrate installation process.

All of these store non-sensitive data such as item IDs in order to provide reporting on migrations.

Where CloudM Migrate requires a username or password to interact with a system, and stores sensitive data like this, that data is stored encrypted within SQL Server (AES256). SQL Server 2019 Express is installed by default, or a customer can specify their own SQL server.

### Certification <a name="certification"></a>

CloudM is an ISO 27001 and Cyber Essentials certified organization.

### GDPR <a name="GDPR"></a>

There is a dedicated Data Protection Manager in-place. The business has the relevant systems to comply with its obligations as a data controller and processor and the requirements around data processing principles, rights of the data subject and security of processing.

### Penetration Testing <a name="penetrationtesting"></a>

Regular third party penetration testing is conducted on the product to verify this protection is in place. Testing takes place every 12 - 18 months by a Crest accredited provider.
