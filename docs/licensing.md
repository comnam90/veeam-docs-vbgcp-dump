---
title: "Licensing"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/licensing.html"
last_updated: "11/28/2024"
product_version: "7.0.0.47"
---

# Licensing


Veeam Backup for Google Cloud is licensed by the number of protected instances. An instance is defined as a single Google Cloud resource — a VM, Cloud SQL or Cloud Spanner instance. An instance is considered to be protected if it has a restore point (snapshot or backup) created by a backup policy during the past 31 days. Each protected instance consumes one license unit from the license scope. However, if an instance has only snapshots created manually, it does not consume any license units.

Veeam Backup for Google Cloud is available in 2 editions:

* Free —  allows you to protect up to 10 instances free of charge. This edition applies only to backup appliances that are no longer managed by Veeam Backup & Replication servers.

* Paid — allows you to protect the number of instances equivalent to the number of units specified in your license. This edition is licensed using the Veeam Universal License (VUL) installed on the Veeam Backup & Replication server. For more information on Veeam licensing terms and conditions, see [Veeam Licensing Policy](https://www.veeam.com/legal/licensing-policy.html#instance-conversion).

When the license expires, Veeam Backup for Google Cloud offers a grace period to ensure a smooth license update and to provide sufficient time to install a new license file. The duration of the grace period is 31 days after the expiration of the license. During this period, you can perform all types of data protection and disaster recovery operations. After the grace period is over, Veeam Backup for Google Cloud stops processing all instances and disables all scheduled backup policies. You must update your license before the end of the grace period.

|  |
| --- |
| Note |
| Veeam Backup & Replication licensing is applied to backup appliances managed by standalone Veeam Backup & Replication servers. For more information, see [Scenarios](license_integration.md). |

In This Section

* [Limitations](license_limitations.md)
* [Scenarios](license_integration.md)
* [Viewing License Information](viewing_license_information.md)
* [Revoking License Units](revoking_license_units.md)


