---
title: "backup_retention_sql"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_retention_sql.html"
last_updated: "8/28/2024"
product_version: "7.0.0.47"
---


In this article

For image-level backups, Veeam Backup for Google Cloud retains restore points for the number of days defined in backup scheduling settings as described in section [Creating SQL Policies](sql_policy_schedule.md).

The forever forward incremental backup method is not fully implemented for Cloud SQL instances — during every backup session Veeam Backup for Google Cloud creates a full backup in the regular backup chain (that is, every incremental backup contains the full instance data set). If Veeam Backup for Google Cloud detects an outdated restore point in a backup repository, it removes this restore point from the backup chain.

Related Topics

[Retention Policy for Archived Backups](archive_backup_retention_sql.md)

Page updated 8/28/2024

Page content applies to build 7.0.0.47
