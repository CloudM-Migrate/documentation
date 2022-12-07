---
layout: default
title: GroupWise
grand_parent: Endpoint Configuration Guides
parent: Self Hosted Guides
nav_order: 2

---

## GroupWise Endpoint Configuration
{: .no_toc }

---

This guide will show how to configure GroupWise as a source endpoint. 

For GroupWise this is defined by the following requirements:

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

### Server Details 

Following the steps are required to effectively set up GroupWise in the source endpoint configuration. 

- GroupWise Version select the version from the drop down. 
- Server Address is required when entering this information in to the source endpoint
- The Hostname or IP address is required of the GroupWise server. 
- Provide or enter the Admin Password for the GroupWise server. 

Additional information as Groupwise as a source can be located at the <a href="https://cloudm-migrate.github.io/documentation/Engineering-Reference/GroupWiseSourceAO.html">GroupWise Source Advanced Options</a>.

---
### Creating Application Key and Trusted Name. 

- Open the GroupWise Administration Console in the web browser.
- Go to **System - Trusted Applications**
- Select **New** in the **Trusted Applications** window.
- A popup for a **New Trusted App Key** will appear. Type GroupWise Mailbox Management in the Name field.
- Select **OK**
- You can either copy the key or select **Export** to save it as a TXT file to make sure you do not lose the key.
