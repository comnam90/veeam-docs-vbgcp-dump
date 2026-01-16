---
title: "database_restore_spanner"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/database_restore_spanner.html"
last_updated: "12/19/2025"
product_version: "7.0.0.47"
---


In this article

To restore a Cloud Spanner database from a cloud-native snapshot, Veeam Backup for Google Cloud copies database snapshots from the source instance, and then uses [native Google Cloud capabilities](https://cloud.google.com/spanner/docs/backup/restore-backup-overview) to revert the databases to their snapshots.

To restore a Cloud Spanner database from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Creates default databases on the target Cloud Spanner instance.
2. Deploys a worker instance within the worker project in the Google Cloud region closest to the region where the target Cloud Spanner instance resides.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Uses the worker instance to retrieve database schema and data of the processed Cloud Spanner instance from the backup file, and then transfers this data to the target Cloud Spanner instance.

If the processed instance contains databases with foreign keys, Veeam Backup for Google Cloud will first restore the database schema without foreign keys, then transfer the database data, and then restore the foreign keys. The restore process in this case can take a lot of time to complete due to [Google Cloud limitations](https://docs.cloud.google.com/spanner/docs/schema-updates?_ga=2.124597578.-1374893166.1657536691#frequency).

|  |
| --- |
| Tip |
| You can track the progress of the restore operation in the Operations tab of the target Cloud Spanner instance UI in [Google Cloud Console](https://console.cloud.google.com/). |

1. Removes the worker instance from Google Cloud.

To learn how to restore a Cloud Spanner database from an image-level backup or a cloud-native snapshot, see [Performing Database Restore](performing_spanner_database_restore_ui.md).

Page updated 12/19/2025

Page content applies to build 7.0.0.47
