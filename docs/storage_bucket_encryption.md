---
title: "storage_bucket_encryption"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/storage_bucket_encryption.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud encrypts backups stored in storage buckets the same way Veeam Backup & Replication encrypts backups stored in backup repositories. To learn what algorithms Veeam Backup & Replication uses to encrypt backups, see the Veeam Backup & Replication User Guide, section [Encryption Standards](https://helpcenter.veeam.com/docs/vbr/userguide/data_encryption.html?ver=13).

To enable encryption for a backup repository added to Veeam Backup for Google Cloud, configure the repository settings as described in section [Adding Backup Repositories](repository_encryption.md). After you create a backup policy and specify the backup repository as a target location for image-level backups, as described in sections [Performing VM Backup](backup_policy_target.md),  [Performing SQL Backup](sql_policy_target.md), and [Performing Spanner Backup](spanner_policy_target.md), Veeam Backup for Google Cloud performs the following steps:

1. Generates an encryption key to protect backups stored in the backup repository, and stores the key in the configuration database on the backup appliance.
2. Uses the generated key to encrypt backed-up data transferred to the backup repository when running the backup policy.

Page updated 11/18/2025

Page content applies to build 7.0.0.47
