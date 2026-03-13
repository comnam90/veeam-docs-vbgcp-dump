---
title: "Specifying Weekly Schedule"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/sql_schedule_weekly.html"
last_updated: "3/11/2026"
product_version: "7.0.0.47"
---

# Specifying Weekly Schedule


To create a weekly schedule for the backup policy, at the Schedule step of the wizard, do the following:

1. Set the Weekly schedule toggle to On and click Edit Weekly Settings.
2. In the Create weekly schedule section, select days when the backup policy will create cloud-native snapshots and image-level backups. Use the Create restore points at drop-down list to schedule a specific time for the backup policy to run.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not create image-level backups independently from cloud-native snapshots. That is why when you select days for image-level backups, the same days are automatically selected for cloud-native snapshots. To learn how Veeam Backup for Google Cloud performs backup, see [How Backup Works](backup_sql.md). |

1. In the Configure weekly retention section, configure retention policy settings for the weekly schedule:

* For cloud-native snapshots, specify the number of restore points that you want to keep in a snapshot chain.

If the restore point limit is exceeded, Veeam Backup for Google Cloud removes the earliest restore point from the chain. For more information, see [Retention Policy for Snapshots](snapshot_retention_sql.md).

|  |
| --- |
| Important |
| Snapshots of Cloud SQL instances are taken using [native Google Cloud capabilities](https://cloud.google.com/sql/docs/mysql/backup-recovery/backups), and therefore, if you delete a Cloud SQL instance from Google Cloud, all cloud-native snapshots created by the backup policy for the removed instance will be automatically deleted from Google Cloud Storage as well, despite the retention settings configured at the Schedule step of the wizard. |

* For image-level backups, specify the number of days (or months) for which you want to keep restore points in a backup chain.

If a restore point is older than the specified time limit, Veeam Backup for Google Cloud removes the restore point from the chain. For more information, see [Retention Policy for Backups](backup_retention_sql.md).

1. To save changes made to the backup policy settings, click Apply.

[![Adding Backup Policy](images/sql_policy_weekly_schedule.webp)](images/sql_policy_weekly_schedule.webp "Adding Backup Policy")


