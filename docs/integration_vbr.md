---
title: "Integration with Veeam Backup & Replication"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/integration_vbr.html"
last_updated: "11/21/2024"
product_version: "7.0.0.47"
---

# Integration with Veeam Backup & Replication


Starting from Veeam Backup for Google Cloud 5.0, Veeam Plug-in for Google Cloud became part of the Veeam Backup for Google Cloud solution. Veeam Backup for Google Cloud extends the Veeam Backup & Replication functionality and allows you to add backup appliances to Veeam Backup & Replication. With Veeam Plug-in for Google Cloud, you can manage data protection and recovery operations for all these appliances from a single Veeam Backup & Replication console.

Version 5.0 came with a major feature — the ability to protect Cloud Spanner resources — that is available only for those backup appliances managed by a Veeam Backup & Replication server. To unlock the full functionality, you must [install Veeam Plug-in for Google Cloud](deployment.md) on the server and [add your appliances](adding_appliances.md) to the backup infrastructure.

|  |
| --- |
| Important |
| * If you remove a backup appliance from the backup infrastructure, you will no longer be able to add, enable and start Spanner backup policies. Creating Cloud Spanner snapshots manually will also be unavailable.  * If the connection between a backup appliance and the backup server is lost for more than 31 days, the appliance will enter the standalone mode, and you will no longer be able to protect Cloud Spanner instances. |

Related Topics

[Protecting Cloud Spanner Instances](overview_spanner.md)


