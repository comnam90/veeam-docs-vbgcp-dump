---
title: "backup_vm"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_vm.html"
last_updated: "12/11/2023"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud performs VM instance backup in the following way:

1. Creates snapshots of persistent disks that are attached to the processed VM instance.

PD snapshots are assigned resource labels upon creation. Keys and values of resource labels contain encrypted metadata that helps Veeam Backup for Google Cloud identify the related PD snapshots and treat them as a single unit — a cloud-native snapshot.

1. If you enable image-level backup for the backup policy, Veeam Backup for Google Cloud performs the following operations:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the processed VM instance resides. For more information, see [Managing Worker Instances](managing_worker_configurations.md).
2. Re-creates the persistent disks from the cloud-native snapshot created at step 1 and attaches them to the worker instance.

Note that the cloud-native snapshot used as a source for image-level backup is not a temporary snapshot — when the backup session completes, this snapshot remains in the snapshot chain and is deleted later according to the specified [policy scheduling settings](backup_policy_schedule.md).

1. Reads data from the persistent disks on the worker instance, transfers the data to the target standard or nearline repository, and stores it in the native Veeam format.

Veeam Backup for Google Cloud encrypts and compresses data saved to storage buckets. For more information, see [Enabling Data Encryption](enabling_data_encryption.md).

1. Removes the worker instance when the backup session completes.

1. If you enable the [backup archiving mechanism](backup_archiving.md), Veeam Backup for Google Cloud performs the following operations:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the processed VM instance resides.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Retrieves data from the target standard or nearline repository, and transfers it to the target archive repository.
2. Removes the worker instance when the archive session completes.

Related Topics

* [Snapshot Chain](snapshot_chain_vm.md)
* [Backup Chain](backup_chain_vm.md)
* [VM Backup Retention](backup_retention_vm.md)

Page updated 12/11/2023

Page content applies to build 7.0.0.47
