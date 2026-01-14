---
title: "snapshot_chain_spanner"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/snapshot_chain_spanner.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---


In this article

During every backup session, Veeam Backup for Google Cloud creates a 'backup' of each database of a Cloud Spanner instance added to a backup policy. The set of 'backups' is a single cloud-native snapshot that Veeam Backup for Google Cloud creates using native Google Cloud capabilities.

|  |
| --- |
| Note |
| Cloud-native snapshots of Cloud Spanner instances are referred to as backups in Google Cloud documentation. However, since all 'backups' of a Cloud Spanner instance are stored in the instance itself, and you cannot delete an instance without deleting its snapshots first, 'backups' of Cloud Spanner instances are referred to as snapshots in this guide. In terms of Veeam logic, backups are independent files that are stored in backup repositories and that are not affected by any actions performed with the original instances whatsoever. |

A sequence of cloud-native snapshots created during a set of backup sessions makes up a snapshot chain. Veeam Backup for Google Cloud builds the snapshot chain in the following way:

1. During the first backup session, Veeam Backup for Google Cloud creates snapshots of all the instance databases and saves them in the target location. These snapshots become a starting point in the snapshot chain.

The creation of the first snapshot may take significant time to complete since Veeam Backup for Google Cloud processes all the instance databases.

1. During subsequent backup sessions, Veeam Backup for Google Cloud creates snapshots as described in the [Google Cloud Spanner documentation](https://cloud.google.com/spanner/docs/backup/create-backup).

The creation of subsequent snapshots typically takes less time to complete, compared to the first snapshot in the chain. Note, however, that the completion time still depends on the amount of processed data.

|  |
| --- |
| Note |
| The target location of cloud-native snapshots depends on the regional configuration of the processed instance. For more information, see [Google Cloud documentation](https://cloud.google.com/spanner/docs/backup#key-features). |

Each cloud-native snapshot in the snapshot chain contains metadata. Metadata stores information about the protected instance and the backup policy that created the snapshot. Veeam Backup for Google Cloud uses metadata to identify outdated snapshots, to load the configuration of source instances during recovery operations and so on.

Cloud-native snapshots act as independent restore points for backed-up instances. If you remove any snapshot, it will not break the snapshot chain — you will still be able to roll back instance data to any existing restore point.

![Snapshot Chain](images/snapshot_chain.webp)

The number of cloud-native snapshots kept in the snapshot chain is defined by retention policy settings. For more information, see [Spanner Snapshot Retention](snapshot_retention_spanner.md).

Related Topics

[Spanner Snapshot Retention](snapshot_retention_spanner.md)

Page updated 6/13/2025

Page content applies to build 7.0.0.47
