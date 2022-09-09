---
layout: default
title: Google
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 1
---

## Google Source Advanced Options
{: .no_toc }

---
This document will give an overview on all the Google Source Advanced Options in CloudM Migrate. 

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

1. [Use Limited Scopes](#limitedscope)
2. [Enable Gmail Discovery throttle](#gmaildiscoverythrottle)
3. [Gmail Discovery request per 100 seconds limit](#gmaildiscoveryper100)
4. [Gmail API Filter Override](#gmailapifilter)
5. [Gmail Discovery request per second limit](#gmailrequestper)

### Use Limited Scopes <a name="limitedscope"></a>
{: .no_toc }
Default Value: Off

Use Limited Scopes requires the following scopes to be enabled: 'https://www.googleapis.com/auth/gmail.labels' and 'https://www.googleapis.com/auth/gmail.readonly'.

Change Conditions: ??

### Enable Gmail Discovery throttle <a name="gmaildiscoverythrottle"></a>
{: .no_toc }
Default Value: Off

Enable request per second/minute limits for Gmail Discovery Service.

Change Conditions: ??

### Gmail Discovery request per 100 seconds limit <a name="gmaildiscoveryper100"></a>
{: .no_toc }
Default Value: 1000

Gmail Discovery maximum requests per 100 seconds before throttling.

Change Conditions: ??

### Gmail API Filter Override <a name="gmailapifilter"></a>
{: .no_toc }
Default Value: None

When using the Gmail API to export email, use the provided filter to override other tool settings. Leave empty to auto generate the filter. Note: this will override the following settings: Date Ranges, Folders and Excluded Folders.

Change Conditions: ??

### Gmail Discovery request per second limit <a name="gmailrequestper"></a>
{: .no_toc }
Default Value: 10

Gmail Discovery maximum requests per second before throttling

Change Conditions: ??
