---
title: "Instance Restore"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_entire_instance_sql.html"
last_updated: "3/11/2026"
product_version: "7.0.0.47"
---

# Instance Restore


To restore a Cloud SQL instance from a cloud-native snapshot, Veeam Backup for Google Cloud first creates a Cloud SQL instance in the target location and then uses [native Google Cloud capabilities](https://cloud.google.com/sql/docs/mysql/backup-recovery/restore) to revert the instance to the snapshot. Restore of Cloud SQL instances from cloud-native snapshots is supported only to a new location or with different settings.

To restore a Cloud SQL instance from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Creates a Cloud SQL instance in the target location (that is, the project and region specified for the restore operation).
2. Deploys a worker instance within the worker project in the Google Cloud region in which the restored Cloud SQL instance will reside.

|  |
| --- |
| Note |
| Every time before creating a Cloud SQL instance, Veeam Backup for Google Cloud checks whether the total size of the instance breaches the zone quota for the project in which the worker instance is deployed. If the total instance size is less than 1000 GB, Veeam Backup for Google Cloud temporarily attaches an additional empty disk to the worker instance — but only for the duration of the restore process and if the quota allows attaching the disk. This allows Veeam Backup for Google Cloud to speed up the data transfer to reduce your restore costs. |

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Uses the worker instance to retrieve database files, triggers, views, stored procedures and users of the processed Cloud SQL instance from the backup file, and then imports this data to the created Cloud SQL instance.
2. Removes the worker instance from Google Cloud.

To learn how to restore a Cloud SQL instance from a cloud-native snapshot or an image-level backup, see [Performing SQL Instance Restore](performing_sql_instance_restore_ui.md).


