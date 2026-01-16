---
title: "restore_database"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_database.html"
last_updated: "1/26/2024"
product_version: "7.0.0.47"
---


In this article

To restore a Cloud SQL database from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Creates a temporary snapshot of the Cloud SQL instance that will host the restored database.
2. Deploys a worker instance within the worker project in the Google Cloud region in which the target Cloud SQL instance resides.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. [Applies only to restore points of MySQL instances protected by Veeam Backup for Google Cloud version 4.0 and earlier] Uses native Google Cloud capabilities to import the exported data to the target Cloud SQL instance.
2. Uses the worker instance to retrieve database files, triggers, stored procedures and users of the processed Cloud SQL instance from the backup file, and then imports this data to the target Cloud SQL instance.
3. Removes the worker instance from Google Cloud.
4. Deletes the temporary snapshot.

|  |
| --- |
| Note |
| If Veeam Backup for Google Cloud fails to restore the database, the temporary snapshot will not be deleted automatically. You can either delete the snapshot manually or use it to revert the Cloud SQL instance to its initial state. Consider that if the target instance hosts other databases and any write operations to these databases occur during the restore process, the revert operation will result in data loss. |

To learn how to restore a Cloud SQL database from an image-level backup, see [Performing Database Restore](performing_database_restore_ui.md).

Page updated 1/26/2024

Page content applies to build 7.0.0.47
