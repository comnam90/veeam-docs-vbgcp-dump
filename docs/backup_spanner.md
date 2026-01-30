---
title: "Spanner Backup"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_spanner.html"
last_updated: "7/30/2024"
product_version: "7.0.0.47"
---

# Spanner Backup


When processing a Cloud Spanner instance added to a backup policy, Veeam Backup for Google Cloud creates a restore point for the instance and transfers the point directly to a backup repository.

Veeam Backup for Google Cloud performs Cloud Spanner instance backup in the following way:

1. Creates a cloud-native snapshot of each database of the processed Cloud Spanner instance.
2. If you enable image-level backup for the backup policy, Veeam Backup for Google Cloud performs the following operations:

1. Deploys a worker instance within the worker project in the Google Cloud region depending both on the target backup repository location and the region where read-write and read-only replicas reside.
2. Uses the worker instance to retrieve database schema, views, keys and data of the processed Cloud Spanner instance, transfers the retrieved data to the target backup repository and stores the data in the native Veeam format.
3. Removes the worker instance from Google Cloud when the backup session completes.

1. If you enable the [backup archiving mechanism](spanner_backup_archiving.md), Veeam Backup for Google Cloud performs the following operations:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the target standard or nearline repository is located.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Retrieves data from the target standard or nearline repository, and transfers it to the target archive repository.
2. Removes the worker instance when the archive session completes.

Related Topics

* [Snapshot Chain](snapshot_chain_spanner.md)
* [Backup Chain](backup_chain_spanner.md)
* [Spanner Backup Retention](backup_retention_spanner.md)


