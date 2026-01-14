---
title: "understanding_retention_policy"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/understanding_retention_policy.html"
last_updated: "8/22/2024"
product_version: "7.0.0.47"
---


In this article

Cloud-native snapshots and image-level backups created by backup policies are not kept forever — they are removed according to retention policy settings specified while creating the policies as described in sections [Creating VM Policies](backup_policy_schedule.md), [Creating SQL Policies](sql_policy_schedule.md) and [Creating Spanner Policies](spanner_policy_schedule.md).

Depending on the data protection scenario, retention policies can be specified:

* In restore points — for cloud-native snapshots.

The snapshot chain can contain only the allowed number of restore points. If the number of allowed restore points is exceeded, Veeam Backup for Google Cloud removes the earliest restore point from the snapshot chain. For more information, see [VM Snapshot Retention](snapshot_retention_vm.md), [SQL Snapshot Retention](snapshot_retention_sql.md) and [Spanner Snapshot Retention](snapshot_retention_spanner.md).

* In days/months/years — for image-level backups.

Restore points in the backup chain (either regular or archive) can be stored in the backup repository only for the allowed period of time. If a restore point is older than the specified time limit, Veeam Backup for Google Cloud removes it from the backup chain. For more information, see sections [VM Backup Retention](backup_retention_vm.md), [SQL Backup Retention](backup_retention_sql.md) and [Spanner Backup Retention](backup_retention_spanner.md).

You can also specify retention settings for snapshots that become obsolete. For more information, see [Configuring Global Retention Settings](configuring_global_retention_settings.md#snapshots).

Related Topics

* [Creating VM Backup Policies](creating_vm_backup_policies.md)
* [Creating SQL Backup Policies](creating_sql_backup_policies.md)
* [Creating Spanner Backup Policies](creating_spanner_backup_policies.md)

Page updated 8/22/2024

Page content applies to build 7.0.0.47
