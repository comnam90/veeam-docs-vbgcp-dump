---
title: "backup_repositiories"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_repositiories.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

A backup repository is a subdirectory in a Google Cloud storage bucket where Veeam Backup for Google Cloud stores backups of protected VM instances, Cloud SQL instances and Cloud Spanner instances.

To communicate with a backup repository, Veeam Backup for Google Cloud uses Veeam Data Mover — a service that runs on a [worker instance](overview_worker_instances.md) and that is responsible for data processing and transfer. When a backup policy addresses the backup repository, Veeam Data Mover establishes a connection with the repository to enable data transfer. To learn how Veeam Backup for Google Cloud communicates with backup repositories, see [Managing Backup Repositories](managing_repositories.md).

|  |
| --- |
| Important |
| Backups are stored in backup repositories in the native Veeam format and must be modified neither manually nor by 3rd party tools, including native Google Cloud capabilities (for example, the [Autoclass feature](https://cloud.google.com/storage/docs/autoclass)). Otherwise, Veeam Backup for Google Cloud may fail to restore the backed-up data. |

Encryption on Repositories

For enhanced data security, Veeam Backup for Google Cloud allows you to enable encryption at the repository level. Veeam Backup for Google Cloud uses the same encryption standards as Veeam Backup & Replication to encrypt backups stored in backup repositories. To learn what encryption standards Veeam Backup & Replication uses to encrypt its data, see the Veeam Backup & Replication User Guide, section [Encryption Standards](https://helpcenter.veeam.com/docs/vbr/userguide/data_encryption.html?ver=13).

To learn how to enable encryption at the repository level, see [Data Encryption](storage_bucket_encryption.md).

Limitations for Repositories

To use a storage bucket as a target location for backups, you must connect to a project to which this bucket belongs as described in section [Adding Backup Repositories](repository_project.md).

Veeam Backup for Google Cloud allows you to store backups in the Standard, Nearline and Archive storage classes. The Coldline storage class is not supported. For more information on storage classes offered by Cloud Storage, see [Google Cloud documentation](https://cloud.google.com/storage/docs/storage-classes).

Page updated 11/18/2025

Page content applies to build 7.0.0.47
