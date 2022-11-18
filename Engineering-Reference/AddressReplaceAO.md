---
layout: default
title: Address Replacement
parent: Project Advanced Options
grand_parent: Engineering Reference 
nav_order: 7
---

## Project Advanced Options Reference

## Address Replacement Advanced Options

1. [Replace Usernames](#replaceuser)
2. [Address Replacements (.csv)](#addreplacecsv)
3. [Non-Matched Address Replacement Behaviour <](#nonmatchreplace)
4. [Replace CSV Addresses Only](#replacecsvonly)

### Replace Usernames <a name="replaceuser"></a>
Default Value: On

Replace any remapped usernames from the users page, when migrating the items specified in 'Domain Replacement Types' tab. If this option is disabled and replacements are required, explicit mappings for email addresses and domain names should be provided.

Change Conditions: 

### Address Replacements (.csv) <a name="addreplacecsv"></a>
Default Value: None

Specify a path to a CSV file containing replacement values to modify email addresses for appointments and contacts during migration. To perform no replacements, do not specify a file.

-	User A owns a file
-	User B has access to the file
-	User A isn’t being migrated to the destination domain
-	User B is being migrated to to the destination domain and will need to be able to access the file

During the course of the migration the ACL for the file is amended adding user B new destination address. Which will allow User B to continue to access the file that’s still in the source platform. 

### Non-Matched Address Replacement Behaviour <a name="nonmatchreplace"></a>
Default Value: Retain Original Address

When 'Replace Usernames' is enabled, and a CSV has been provided for address replacement, set the behaviour when an address has not been matched. Either replace the domain name of the address, or leave the original address.

Change Conditions: ??

### Replace CSV Addresses Only <a name="replacecsvonly"></a>
Default Value: Off

Perform email addresses and domain replacements from the CSV file specified in 'Address Replacements' and do not attempt to perform replacements using any other method.

Change Conditions: Turn on to only change address of users specified in the CSV under Address Replacements (.csv)


