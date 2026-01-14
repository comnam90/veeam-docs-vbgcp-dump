---
title: "instance_restore_spanner"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/instance_restore_spanner.html"
last_updated: "12/19/2025"
product_version: "7.0.0.47"
---


In this article

To restore a Cloud Spanner instance from a cloud-native snapshot, Veeam Backup for Google Cloud first creates a Cloud Spanner instance in the target location, copies database snapshots from the source instance, and then uses [native Google Cloud capabilities](https://cloud.google.com/spanner/docs/backup/restore-backup-overview) to revert the databases to their snapshots. Restore of Cloud Spanner instances from cloud-native snapshots is supported only to a new location or with different settings.

To restore a Cloud Spanner instance from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Creates a Cloud Spanner instance with default databases in the target location (that is, the project and region specified for the restore operation).
2. Deploys a worker instance within the worker project in the Google Cloud region in which the target instance resides or the region in which the read-write replicas are located.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Uses the worker instance to retrieve database schema and data of the processed Cloud Spanner instance from the backup file, and then imports this data to the created Cloud Spanner instance.

If the processed instance contains databases with foreign keys, Veeam Backup for Google Cloud will first restore the database schema without foreign keys, then import the database data, and then restore the foreign keys. The restore process in this case can take a lot of time to complete due to [Google Cloud limitations](https://docs.cloud.google.com/spanner/docs/schema-updates?_ga=2.124597578.-1374893166.1657536691#frequency).

|  |
| --- |
| Tip |
| You can track the progress of the restore operation in the Operations tab of the target Cloud Spanner instance UI in [Google Cloud Console](https://console.cloud.google.com/). |

1. Removes the worker instance from Google Cloud.

To learn how to restore a Cloud Spanner instance from a cloud-native snapshot or an image-level backup, see [Performing Spanner Instance Restore](spanner_restore_instance.md).

Page updated 12/19/2025

Page content applies to build 7.0.0.47
