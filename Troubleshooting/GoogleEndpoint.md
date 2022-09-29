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
{: .no_toc }

### The remote server returned an error: (403) Forbidden


You should ensure that the <a href="https://developers.google.com/workspace/guides/configure-oauth-consent">Configure the OAuth consent screen</a> and the API Scopes added in the admin console.

- 403 error: The user does not have sufficient permissions for file {fileId}
A insufficientFilePermissions error occurs when the user doesn't have write access to a file, and your app is attempting to modify the file.
To fix this error, instruct the user to contact the file's owner and request edit access. You can also check user access levels in the metadata retrieved by files.get and display a read-only UI when permissions are missing.

An error 403 occurs when a usage limit has been exceeded or the user doesn't have the correct privileges. To determine the specific type of error. This error occurs for the following situations:

- The daily limit was exceeded.
- The user rate limit was exceeded.
- The project rate limit was exceeded.
- The sharing rate limit was exceeded.
- The user hasn't granted your app rights to a file.
- The user doesn't have sufficient permissions for a file.
- Your app can't be used within the signed in user's domain.
- Number of items in a folder was exceeded.
- For information on Drive API limits, refer to Usage limits. For information on Drive folder limits, refer to Folder limits in Google Drive.

---

### 404 error: File not found

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
### 400 Bad Request or 400 Invalid Sharing 

400 Bad Request a Google error and is typically caused by data that cannot be imported into Gmail for one of the following reasons:

- Blocked attachment types which are not allowed in Gmail per https://support.google.com/mail/answer/6590
- Emails containing virus attachments
- Emails not conforming to RFC 822 per https://www.ietf.org/rfc/rfc2822.txt

**Also focusing on 400 Invalid Sharing**

Resolve a 400 error: Invalid sharing request
This error can occur for several reasons. To determine the limit that has been exceeded, evaluate the reason field of the returned JSON. This error most commonly occurs because:

- Sharing succeeded, but the notification email was not correctly delivered.
- The Access Control List (ACL) change is not allowed for this user.
- The message field indicates the actual error.
-  Sharing succeeded, but the notification email was not correctly delivered

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

---

### 429 error: Too many requests

A rate LimitExceeded error occurs when the user has sent too many requests in a given amount of time

To fix this error, use exponential backoff to retry the request.

---

### 500 error internal server errors 

This error can occur when migrating to or from G Suite and the API requests being made by CloudMigrator are exceeding Google's rate limits.  

This error can occur when migrating to or from Google Workspace and the API requests being made by CloudM Migrate are exceeding Google's rate limits. This is the most likely scenario for a Backend Error [500], but there may be other causes. CloudM Migrate uses exponential backoff to minimise these errors, but on the rare occasion they do cause a failure in migration.

Other Examples of 500 errors can include 

- 500 Backend error
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Timeout

These errors occur when an unexpected error arises while processing the request. This can be caused by various issues, including a request's timing overlapping with another request or a request for an unsupported action, such as attempting to update permissions for a single page in a Google Site instead of the site itself.
The best course of action is the wait a 24 hours period for this to reset. 
