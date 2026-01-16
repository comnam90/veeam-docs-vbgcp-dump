---
title: "rescanning_appliances"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/rescanning_appliances.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---


In this article

If a backup appliance becomes unavailable, for example, due to connectivity problems, you can rescan the appliance:

1. In the Veeam Backup & Replication console, open the Backup Infrastructure view.
2. Navigate to Managed Servers.
3. Select the necessary backup appliance and click Rescan appliance on the ribbon.

Alternatively, you can right-click the appliance and select Rescan.

1. In the opened window, click Yes.

Veeam Backup & Replication will remove all data collected from the appliance configuration database. Then, Veeam Backup & Replication will recollect session results for the past 24 hours, as well as information on all snapshots, backups and policies.

|  |
| --- |
| Note |
| The rescan operation cannot be performed for available backup appliances and appliances that require upgrade. To learn how to upgrade backup appliances, see [Upgrading Appliances](updating_vb.md). |

[![Rescan appliance](images/appliance_sync.webp)](images/appliance_sync.webp "Rescan appliance")

Page updated 11/14/2025

Page content applies to build 7.0.0.47
