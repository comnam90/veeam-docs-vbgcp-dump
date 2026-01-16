---
title: "backup_retention_spanner"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_retention_spanner.html"
last_updated: "2/12/2024"
product_version: "7.0.0.47"
---


In this article

For image-level backups, Veeam Backup for Google Cloud retains restore points for the number of days defined in backup scheduling settings as described in section [Creating Spanner Policies](spanner_policy_schedule.md).

The forever forward incremental backup method is not implemented for Cloud Spanner instances — during every backup session Veeam Backup for Google Cloud creates a full backup in the regular backup chain. If Veeam Backup for Google Cloud detects an outdated restore point in a backup repository, it removes this restore point from the backup chain.

Related Topics

[Retention Policy for Archived Backups](archive_backup_retention_spanner.md)

Page updated 2/12/2024

Page content applies to build 7.0.0.47
