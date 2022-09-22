---
layout: default
title: Lotus Notes
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 5
---

## Lotus Notes Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Lotus Notes Source Advanced Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/LotusNotes.html">Lotus Notes Endpoint Options</a>

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
## Email

1. [Name Resolution](#nameres)
2. [Migrate Non-Standard Views](#mignonstand)
3. [Convert RTF To MIME](#conrtfmime)
4. [Sent Items Destination](#sentitemdes)
5. [Remove X-Headers](#removex)

### Name Resolution <a name="nameres"></a>
{: .no_toc }
Default Value: Destination System

Resolve canonical Notes Names to match addresses in the destination system, or to the original Internet Address within Notes.

Change Conditions: ??

### Migrate Non-Standard Views <a name="mignonstand"></a>
{: .no_toc }
Default Value: None

Define any views to be migrated outside of the normal email folder structure. Specify the full view name and the folder to which they will be migrated.

Change Conditions: ??

### Convert RTF To MIME <a name="conrtfmime"></a>
{: .no_toc }
Default Value: On

Convert Notes RTF Documents to MIME. Requires extra local disk space for temporary cache.

Change Conditions: ??

### Sent Items Destination <a name="sentitemdes"></a>
{: .no_toc }
Default Value: Folder Within Sent Items

Specify the destination in the destination system for Sent messages.

Change Conditions: ??

### Remove X-Headers <a name="removex"></a>
{: .no_toc }
Default Value: Off

Remove any 'X-Notes-Item' headers from messages before transferring to the destination system.

Change Conditions: ??

---
## Contact
[Back to Top](#top)

1. [Address Book Processing](#addbookpro)
2. [Migrate All Group Members](#migallmem)
3. [Groups View Name](#groupview)
4. [Name Resolution](#namereso)
5. [People View Name](#peopleview)

### Address Book Processing <a name="addbookpro"></a>
{: .no_toc }
Default Value: Personal and Frequent

Choose the combination of address books to migrate to user's personal contacts.

Change Conditions: ??

### Migrate All Group Members <a name="migallmem"></a>
{: .no_toc }
Default Value: On

Migrate all members of distribution lists from the selected address books, regardless of the actual containing address book.

Change Conditions: ??

### Groups View Name <a name="groupview"></a>
{: .no_toc }
Default Value: Groups

The name of the Notes view containing contact group information.

Change Conditions: ??

### Name Resolution <a name="namereso"></a>
{: .no_toc }
Default Value: Destination System

Resolve canonical Notes Names to match addresses in the destination system, or to the original Internet Address within Notes.

Change Conditions: ??

### People View Name <a name="peopleview"></a>
{: .no_toc }
Default Value: $VIMPeople

The name of the Notes view containing contact information.

Change Conditions: ??

---
## Calendar
[Back to Top](#top)

1. [Name Resolution](#nameresol)
2. [Ignore Unresolvable Resource Appointment Owners](#ignoreunres)
3. [Resource Appointments View Name](#resourceview)

### Name Resolution <a name="nameresol"></a>
{: .no_toc }
Default Value: Destination System

Resolve canonical Notes Names to match addresses in the destination system, or to the original Internet Address within Notes.

Change Conditions: ??

### Ignore Unresolvable Resource Appointment Owners <a name="ignoreunres"></a>
{: .no_toc }
Default Value: Off

When migrating resource appointments, ignore those without a resolvable owner resource.

Change Conditions: ??

### Resource Appointments View Name <a name="resourceview"></a>
{: .no_toc }
Default Value: #Calendar

The name of the view within the resource database containing resource appointment information.

Change Conditions: ??

---
## Form Type
[Back to Top](#top)

1. [Mail Form Types](#mailtypes)
2. [Group Form Types](#grouptypes)
3. [Resource Appointment Form Types](#resourcetype)
4. [Appointment Form Types](#appformtypes)
5. [Contact Form Types](#conformtype) 
 
### Mail Form Types <a name="mailtypes"></a>
{: .no_toc }
Default Value: memo;reply;return reciept;return receipt

Specify a list of form type names that will be used for the specified items.

Change Conditions: ??

### Group Form Types <a name="grouptypes"></a>
{: .no_toc }
Default Value: group

Specify a list of form type names that will be used for the specified items.

Change Conditions: ??

### Resource Appointment Form Types <a name="resourcetype"></a>
{: .no_toc }
Default Value: reservation

Specify a list of form type names that will be used for the specified items.

Change Conditions: ??

### Appointment Form Types <a name="appformtypes"></a>
{: .no_toc }
Default Value: appointment

Specify a list of form type names that will be used for the specified items.

Change Conditions: ??

### Contact Form Types <a name="conformtype"></a>
{: .no_toc }
Default Value: person

Specify a list of form type names that will be used for the specified items.

Change Conditions: ??

---
## Database Details
[Back to Top](#top)

1. [User Database](#userdata)
2. [Import Name Attribute](#importnameatt)
3. [Resource Views](#resourceview)
4. [User View](#userview)
5. [Resource Database](#resourcedata) 
 
### User Database <a name="userdata"></a>
{: .no_toc }
Default Value: names.nsf

The name of the Notes user database on the server. Specify just the name and not the path (usually just 'names.nsf').

Change Conditions: ??

### Import Name Attribute <a name="importnameatt"></a>
{: .no_toc }
Default Value: InternetAddress

The name of the Domino attribute used to generate the import name within the user list. Falls back on 'ShortName' if empty.

Change Conditions: ??

### Resource Views <a name="resourceview"></a>
{: .no_toc }
Default Value: $Resources;$Rooms;$OnlineMeetingPlaces

The names of the views within the resource database that contains resource information.

Change Conditions: ??

### User View <a name="userview"></a>
{: .no_toc }
Default Value: $VIMPeople

The name of the view within the user database that contains user information (usually '$VIMPeople').

Change Conditions: ??

### Resource Database <a name="resourcedata"></a>
{: .no_toc }
Default Value: None

The name of the Notes resource database on the server. Specify just the name and not the path. If there are no resources, leave this empty.

Change Conditions: ??

---
## System
[Back to Top](#top)

1. [Startup Delay](#startdelay)
2. [Server Address Mapping](#serveraddmap)
3. [Domain Replacement](#domainrep)
4. [Account Processing](#accountproc)
 
### Startup Delay <a name="startdelay"></a>
{: .no_toc }
Default Value: 10000

The time delay to wait when starting up migrations (required to prevent errors in the Notes client - do not change without advice).

Change Conditions: ??

### Server Address Mapping <a name="serveraddmap"></a>
{: .no_toc }
Default Value: None

Define any Server to IP mappings e.g. USERS08/SRV/COMPANY => 123.43.3.34.

Change Conditions: ??

### Domain Replacement <a name="domainrep"></a>
{: .no_toc }
Default Value: None

Use the specified domain when using 'Name Resolution' set to 'Destination System'. If empty, the destination domain will be used.

Change Conditions: ??

### Account Processing <a name="accountproc"></a>
{: .no_toc }
Default Value: Account Only

Choose the combination of accounts and archives to migrate.

Change Conditions: ??
