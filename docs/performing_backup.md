---
title: "performing_backup"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_backup.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

With Veeam Backup for Google Cloud, you can protect Google Cloud resources in the following ways:

* Create cloud-native snapshots of VM instances

A cloud-native snapshot includes point-in-time snapshots of persistent disks attached to the processed VM instance. Snapshots of persistent disks (also referred to as PD snapshots) are taken using [native Google Cloud capabilities](https://cloud.google.com/compute/docs/disks/create-snapshots). By default, cloud-native snapshots are stored in the multi-regional location closest to the region in which the original instance resides, but the location can be changed in the [backup policy settings](backup_policy_target.md).

* Create image-level backups of VM instances

In addition to cloud-native snapshots, you can protect your VM instances with image-level backups. An image-level backup captures the whole image of the processed VM instance (including OS data, application data and so on) at a specific point in time. The backup is saved as multiple files to a storage bucket in the [native Veeam format](backup_chain_vm.md).

* Create cloud-native snapshots of Cloud SQL instances

A cloud-native snapshot is a point-in-time snapshot of the processed Cloud SQL instance. Snapshots of Cloud SQL instances are taken using [native Google Cloud capabilities](https://cloud.google.com/sql/docs/mysql/backup-recovery/backups). Cloud-native snapshots are stored in the multi-regional location closest to the region in which the original instance resides.

|  |
| --- |
| Note |
| Cloud-native snapshots of Cloud SQL instances are referred to as backups in Google Cloud documentation. However, since all 'backups' of a Cloud SQL instance are automatically deleted after you remove the instance itself, 'backups' of Cloud SQL instances are referred to as snapshots in this guide. In terms of Veeam logic, backups are independent files that are stored in backup repositories and that are not affected by any actions performed with the original instances whatsoever. |

* Create image-level backups of Cloud SQL instances

In addition to cloud-native snapshots, you can protect your Cloud SQL instances with image-level backups. An image-level backup captures the whole image of the processed Cloud SQL instance (including the instance configuration, databases, triggers, stored procedures and users) at a specific point in time. The backup is saved as multiple files to a storage bucket in the [native Veeam format](backup_chain_sql.md).

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud allows you to protect MySQL and PostgreSQL instances. SQL Server instances are not supported. For more information on types of Cloud SQL instances, see [Google Cloud documentation](https://cloud.google.com/sql/docs/features). |

* Create cloud-native snapshots of Cloud Spanner instances

A cloud-native snapshot is a point-in-time snapshot of the processed Cloud Spanner instance. Snapshots of Cloud Spanner instances are taken using [native Google Cloud capabilities](https://cloud.google.com/spanner/docs/backup). Cloud-native snapshots are stored in the location that depends on the [regional configuration](https://cloud.google.com/spanner/docs/backup#key-features) of the processed instance.

* Create image-level backups of Cloud Spanner instances

In addition to cloud-native snapshots, you can protect your Cloud Spanner instances with image-level backups. An image-level backup captures the whole image of the processed Cloud Spanner instance (including databases schema, data, views, foreign keys) at a specific point in time. The backup is saved as multiple files to a storage bucket in the [native Veeam format](backup_chain_spanner.md).

To schedule data protection tasks to run automatically, create backup policies. For VM, Cloud SQL and Cloud Spanner instances residing in any of the regions added to the backup policies, you can also take cloud-native snapshots manually when needed — for more information, see [Creating VM Snapshots Manually](creating_manual_snapshots_vms.md), [Creating SQL Snapshots Manually](creating_manual_snapshots_sql.md) and [Creating Spanner Snapshots Manually](creating_manual_snapshots_spanner.md).

|  |
| --- |
| Tip |
| You can perform advanced data protection operations with image-level backups using the Veeam Backup & Replication console. For more information, see the Veeam Backup & Replication User Guide, section [External Repository](https://helpcenter.veeam.com/docs/vbr/userguide/external_repository.html?ver=13). |

In This Section

* [Performing Backup Using Console](performing_backup_console.md)
* [Performing Backup Using Web UI](performing_backup_ui.md)

Page updated 11/18/2025

Page content applies to build 7.0.0.47
