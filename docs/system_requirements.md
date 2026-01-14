---
title: "system_requirements"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/system_requirements.html"
last_updated: "11/21/2025"
product_version: "7.0.0.47"
---


In this article

When you plan to install Veeam Backup for Google Cloud, consider the following hardware and software requirements.

Veeam Plug-in for Google Cloud

The machine where Veeam Plug-in for Google Cloud will run must meet system requirements described in the Veeam Backup & Replication User Guide, section [System Requirements](https://helpcenter.veeam.com/docs/vbr/userguide/system_requirements.html?ver=13). Additionally, the following software must be installed:

* Microsoft .NET Core Runtime 8.0 or later
* Microsoft ASP.NET Core Shared Framework 8.0 or later

Backup Server

Veeam Plug-in for Google Cloud version 7 supports integration with Veeam Backup & Replication version 13.0.1.

Backup Appliance

Veeam Plug-in for Google Cloud version 7 supports integration with Veeam Backup for Google Cloud version 7.0.0.47.

Google Cloud APIs

The backup appliance and worker instances must have outbound internet access to a number of Google Cloud APIs. For more information, see [Google Cloud APIs](google_cloud_apis.md).

Web Browsers

Internet Explorer is not supported. To access the Veeam Backup for Google Cloud Web UI, use Microsoft Edge (latest version), Mozilla Firefox (latest version) or Google Chrome (latest version).

Version Compatibility

The following table lists compatible versions of Veeam Backup & Replication, Veeam Plug-in for Google Cloud and Veeam Backup for Google Cloud.

| Veeam Backup & Replication Build | Veeam Plug-in for Google Cloud Version | Veeam Backup for Google Cloud Build | Backup Appliance OS Version |
| --- | --- | --- | --- |
| 13.0.1.180 | 13.7.0.281 | 7.0.0.47 | Ubuntu 22.04 LTS |
| 12.3.0.310 | 12.6.1.10 | 6.0.1.2 |
| 12.3.0.310 | 12.6.0.153 | 6.0.0.21 |
| 12.1.0.2131 | 12.5.0.1257 | 5.0.0.1297 | Ubuntu 20.04 LTS |
| 12.0.0.1420 | 12.0.4.907 | 4.0.0.1082 |
| 4.0.0.1072 |
| 11.0.1.1261 | 11.0.3.616 | 3.0.0.868 |
| 3.0.0.859 |
| 11.0.1.1261 | 11.0.2.331 | 2.0.0.535 |
| 2.0.0.530 |

Page updated 11/21/2025

Page content applies to build 7.0.0.47
