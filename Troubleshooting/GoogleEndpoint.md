---
layout: default
title: Google
parent: Troubleshooting
has_children: false
nav_order: 2
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

## Google Troubleshooting

### The remote server returned an error: (403) Forbidden


You should ensure that the <a href="https://developers.google.com/workspace/guides/configure-oauth-consent">Configure the OAuth consent screen</a> and the API Scopes added in the admin console.

---

### File Not Found: (404) Forbidden

 404 error is "File not found." This can happen when a file is deleted or there is an error in a hyperlink. It can also happen if a file is copied and the original deleted. The new file will have a new address and previous links will not work.
 
 ---
**Migration failed: Unexpected exception processing import. Message is: Google.Apis.Requests.RequestError,File not found: 1mqirFN7_zXaNCeroDW5pJR7zHsGcOmiZ [404],Errors [, Message[File not found: 1mqirFN7_zXaNCeroDW5pJR7zHsGcOmiZ] Location[file - other]**

This error usually means that after the permissions change the file no longer has permission to be added to one of its parent folders, often due to group membership reason[notFound] Domain[global],],

*Example Scenario*

If a person is the sole owner of a folder and it's erroring out with a 404 error then you need to look at the user that's failing with the 404 error. That folder has more than likely been shared out to that user so there's two paths forward, either remove the share link or create an address replacement for that user that's being hit with the 404 error. 

Following the proper migration steps will help avoid a lot of this:

- Configure the tool based on our recommended steps. 
- Migrate groups and group members. 
- Run a small test migration.
- Then run the bulk migration email and drive
- Delta migration with calendar, contacts

---

### 500 error internal server error

This error can occur when migrating to or from G Suite and the API requests being made by CloudMigrator are exceeding Google's rate limits.  

---

### Insufficient Permission 403 or 401 

This error for example is happening on Google Import, indicating that there is an issue with permissions in either for the service account or API Scopes.  Can you make sure that all the scopes have been added to the service account and that your API's all have been enabled?  Also, check if you have the Admin SDK API enabled. This sometimes causes the issue. For reason in the logs for every failure states " “ Not retrying Forbidden[403] error,”


Not retrying Forbidden[403] error Google.Apis.Requests.RequestError Insufficient Permission [403] Errors [ Message[Insufficient Permission] Location[ - ] Reason[insufficientPermissions] Domain[global] ]


For a 401 That particular error refers to the forwarding setting in a user's mailbox, for example when they are on holiday, to forward their mail to another member of staff. The error simply means there has been no forwarding instructions set up on the account. It can be ignored, but the way to get rid of it would be to set up account forwarding in the destination. 

- Ensure that the admin user you are using to migrate has logged into Google Workspace at least once
- Check you have followed all of the steps in the documentation for configuring the source and destination platforms
- Double check all usernames and password
- Check that OAuth access is setup and enabled correctly
- Ensure that the time on the workstation/server that is running the migration tool is correct
