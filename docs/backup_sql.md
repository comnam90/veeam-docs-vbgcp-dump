---
title: "SQL Backup"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_sql.html"
last_updated: "3/11/2026"
product_version: "7.0.0.47"
---

# SQL Backup


When processing a Cloud SQL instance added to a backup policy, Veeam Backup for Google Cloud can create a restore point for the instance and transfer the point directly to a backup repository, or can copy the instance to a staging server first, create a restore point and then transfer it to a repository.

Veeam Backup for Google Cloud performs Cloud SQL instance backup in the following way:

1. Creates a cloud-native snapshot of the processed Cloud SQL instance.
2. If you enable image-level backup for the backup policy, Veeam Backup for Google Cloud performs the following operations:

1. If you choose to perform backup using a staging server:

1. Launches a staging server instance in a Google Cloud region in which the source Cloud SQL instance resides.
2. Reverts the staging server instance to the cloud-native snapshot created at step 1.

Note that the cloud-native snapshot used as a source for image-level backup is not a temporary snapshot — when the backup session completes, this snapshot remains in the snapshot chain and is deleted later according to the specified [policy scheduling settings](sql_policy_schedule.md).

|  |
| --- |
| Important |
| Veeam Backup for Google Cloud launches staging server instances without public IP addresses. To allow backup operations to complete successfully, you must configure private services access for these instances manually as described in [Google Cloud documentation](https://cloud.google.com/vpc/docs/configure-private-services-access). |

1. Deploys a worker instance within the worker project in the Google Cloud region in which the processed Cloud SQL instance resides.

By default, Veeam Backup for Google Cloud deploys worker instances with private IP addresses regardless of the network configurations specified for the processed Cloud SQL instances (that is, if a Cloud SQL instance has either a public IP address or both a public and a private IP address, the worker instance will still have a private IP address). However, you can add specific worker configurations. For more information, see [Managing Worker Instances](managing_worker_configurations.md).

|  |
| --- |
| Important |
| If you plan to back up Cloud SQL instances, you must configure network access between the subnets of the worker instances and the subnets of the processed Cloud SQL instances. Alternatively, you can configure the worker instances to allow public IP access as described in section [Configuring Deployment Mode](appendix_private_deployment.md). |

1. Uses the worker instance to retrieve databases, views, triggers, stored procedures and users of the processed Cloud SQL instance, transfers the retrieved data to the target backup repository and stores the data in the native Veeam format.

1. Removes the staging server instance (if launched at step 2a).
2. Removes the worker instance from Google Cloud when the backup session completes.

1. If you enable the [backup archiving mechanism](sql_backup_archiving.md), Veeam Backup for Google Cloud performs the following operations:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the target standard or nearline repository is located.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Retrieves data from the target standard or nearline repository, and transfers it to the target archive repository.
2. Removes the worker instance when the archive session completes.

Related Topics

* [Snapshot Chain](snapshot_chain_sql.md)
* [Backup Chain](backup_chain_sql.md)
* [SQL Backup Retention](backup_retention_sql.md)


