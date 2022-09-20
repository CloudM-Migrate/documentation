---
layout: default
title: O365
grand_parent: Engineering Reference
parent: Source Options
nav_order: 2
---

## O365 Source Options
{: .no_toc }

---

This document will give an overview on all the O365 Source Options in CloudM Migrate. 

---

1. [Office 365 Plan](#sharepointapi)
2. [Authentication Method](#sharepointadmin)
3. [Admin Username](#sharepointtime)
4. [Admin Password](#includeclassicteam)
5. [Client ID](#retrycount)
6. [Application Password](#docsharingoperm)
7. [Domain Name](#hybridenv)
8. [Test Username](#docsharingoperm)
9. [PFX Certificate Path](#hybridenv)
10. [PFX Certificate Password](#hybridenv)

### Office 365 Plan <a name="off365plan"></a>
{: .no_toc }
Default Value: Office 365

Office 365 Germany is a differentiated option to the Office 365 services already available across Europe. It helps address the needs of the most regulated customers in Germany.

### Authentication Method <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: Modern

Choose the authetication type that will be used with the server. For Office 365 this should be set to 'Modern'.

Change Conditions: ??

### Admin Username <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The email address of an administrator (for Office 365), or an email or username in the form 'domain\\user name' (for on-premise installations), setup to perform migrations.

### Admin Password <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The password for the specified admin account.

### Client ID <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

Client Id can be obtained by registering an application under 'App registrations' in Azure Active Directory (see documentation)

### Application Password <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The pasword for the azure application.

### Domain Name <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The domain name of the Exchange domain. This should be the internet domain of the Exchange system, not the local domain name.

### Test Username <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The email of a non-admin user within the system to test Impersonation or Delegation. Specify a primary SMTP email address or just the part before the '@' symbol and the domain name will be appended. This user must have an active mailbox.

### PFX Certificate Path <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The location of your pfx certificate. Please provide the full path.

### PFX Certificate Password <a name="sharepointadmin"></a>
{: .no_toc }
Default Value: None

The pasword for the pfx certificate (leave blank if there is no password).
