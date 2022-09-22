---
layout: default
title: Zimbra
grand_parent: Engineering Reference
parent: Endpoint Options
nav_order: 6
---

## Zimbra Endpoint Options
{: .no_toc }

---

This document will give an overview on all the Zimbra Endpoint Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/ZimbraSourceAO.html">Zimbra Source Advanced Options</a>

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
### Server Address

The hostname or IP address of a Zimbra server.

### REST Connection Protocol

Choose whether to use a secure, HTTPS encrypted connection, or a default unsecure HTTP connection for REST requests.

### SOAP Connection Protocol

Choose whether to use a secure, HTTPS encrypted connection, or a default unsecure HTTP connection for SOAP requests.

### REST Port
Default Value: 443

The port number that Zimbra will accept REST requests to (normally 443 for HTTPS).

### SOAP Port

The port number that Zimbra will accept SOAP requests to (normally 7071 for HTTPS).

### Admin Username

The name of a domain or system administator. Specify the name or email address.

### Admin Password

The administrator password

### Test Username

The full email address of a user within the system other than the admin user (used for testing connections).

### Domain Name

If your Zimbra system contains multiple domains, specify the domain to limit the migration to. Leave empty for all domains.



