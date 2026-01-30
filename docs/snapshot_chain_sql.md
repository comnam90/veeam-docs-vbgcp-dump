---
title: "Snapshot Chain"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/snapshot_chain_sql.html"
last_updated: "2/7/2024"
product_version: "7.0.0.47"
---

# Snapshot Chain


During every backup session, Veeam Backup for Google Cloud creates a cloud-native snapshot of each Cloud SQL instance added to a backup policy. The cloud-native snapshot itself is a single 'backup' that Veeam Backup for Google Cloud creates using native Google Cloud capabilities.

|  |
| --- |
| Note |
| Cloud-native snapshots of Cloud SQL instances are referred to as backups in Google Cloud documentation. However, since all 'backups' of a Cloud SQL instance are automatically deleted after you remove the instance itself, 'backups' of Cloud SQL instances are referred to as snapshots in this guide. In terms of Veeam logic, backups are independent files that are stored in backup repositories and that are not affected by any actions performed with the original instances whatsoever. |

A sequence of cloud-native snapshots created during a set of backup sessions makes up a snapshot chain. Veeam Backup for Google Cloud builds the snapshot chain in the following way:

1. During the first backup session, Veeam Backup for Google Cloud creates a snapshot of all instance data, and saves it in the multi-regional location closest to the region in which the original instance resides. This snapshot becomes a starting point in the snapshot chain.

The creation of the first snapshot may take significant time to complete since Veeam Backup for Google Cloud processes all the instance databases.

1. During subsequent backup sessions, Veeam Backup for Google Cloud creates snapshots that contain only those data blocks that have changed since the previous backup session.

The creation of subsequent snapshots typically takes less time to complete, compared to the first snapshot in the chain. Note, however, that the completion time still depends on the amount of processed data.

For more information on how incremental Cloud SQL snapshots work, see [Google Cloud SQL documentation](https://cloud.google.com/sql/docs/mysql/backup-recovery/backups#about_backup_size).

Each cloud-native snapshot in the snapshot chain contains metadata. Metadata stores information about the backup policy that created the snapshot, but does not contain any information about the protected instance. Veeam Backup for Google Cloud uses metadata to identify outdated snapshots only; information about the protected instance is stored separately, in the internal Veeam Backup for Google Cloud database.

Cloud-native snapshots act as independent restore points for backed-up instances. If you remove any snapshot, it will not break the snapshot chain — you will still be able to roll back instance data to any existing restore point.

![Snapshot Chain](images/snapshot_chain.webp)

The number of cloud-native snapshots kept in the snapshot chain is defined by retention policy settings. For more information, see [SQL Snapshot Retention](snapshot_retention_sql.md).


