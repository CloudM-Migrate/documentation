---
layout: default
title: SharePoint
grand_parent: Engineering Reference
parent: Source Advanced Options
nav_order: 18
---

## SharePoint Source Advanced Options
{: .no_toc }

---

This document will give an overview on all the SharePoint Source Advanced Options in CloudM Migrate. 

<a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/SharePointSource.html">SharePoint Source Options</a>

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
## Document

1. [Document Sharing/Permissions](#docsharperm)
2. [Document Library BaseTemplate IDs](#doclibbase)
3. [Batch Size](#batchsize)

### Document Sharing/Permissions <a name="docsharperm"></a>
{: .no_toc }
Default Value: Share Documents

Choose whether the document should be shared as per the source file ACLs if they can be resolved to email addresses (see documentation).

Change Conditions: ??

### Document Library BaseTemplate IDs <a name="doclibbase"></a>
{: .no_toc }
Default Value: None

Additional document library BaseTemplate IDs to export. BaseTemplate IDs 101, 109 and 700 are exported by default.

Change Conditions: ??

### Batch Size <a name="batchsize"></a>
{: .no_toc }
Default Value: 500

The maximum number of items to return per OneDrive batch file/folder request.

Change Conditions: ??

---
## Transfer and Performance

1. [Trace Folder Requests](#tracefold)

### Retry Count<a name="tracefold"></a>
{: .no_toc }
Default Value: 10

The number of times an operation will be attempted before failing.

Change Conditions: ??

### Time Out <a name="tracefold"></a>
{: .no_toc }
Default Value: 1800000

The timeout that will apply to communications with the SharePoint server.

Change Conditions: ??
