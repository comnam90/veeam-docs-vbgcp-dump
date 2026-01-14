---
title: "schedule_monthly"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/schedule_monthly.html"
last_updated: "11/11/2025"
product_version: "7.0.0.47"
---


In this article

To create a monthly schedule for the backup policy, at the Schedule step of the wizard, do the following:

1. Set the Monthly schedule toggle to On and click Edit Monthly Settings.
2. In the Choose monthly backup target section, select months when the backup policy will create cloud-native snapshots and image-level backups. Use the Create restore points at and Run on drop-down lists to schedule a specific time and day for the backup policy to run.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not create image-level backups independently from cloud-native snapshots. That is why when you select months for image-level backups, the same months are automatically selected for cloud-native snapshots. To learn how Veeam Backup for Google Cloud performs backup, see [VM Backup](backup_vm.md). |

1. In the Configure monthly retention section, configure retention policy settings for the monthly schedule:

* For cloud-native snapshots, specify the number of restore points that you want to keep in a snapshot chain.

If the restore point limit is exceeded, Veeam Backup for Google Cloud removes the earliest restore point from the chain. For more information, see [Retention Policy for Snapshots](snapshot_retention_vm.md).

* For image-level backups, specify the number of days (or months) for which you want to keep restore points in a backup chain.

If a restore point is older than the specified time limit, Veeam Backup for Google Cloud removes the restore point from the chain. For more information, see [Retention Policy for Backups](backup_retention_vm.md).

1. To save changes made to the backup policy settings, click Apply.

|  |
| --- |
| Tip |
| If you have enabled backup archiving at the Targets step of the wizard, and want to store monthly backups in an archive backup repository, set the Send backups to archive toggle to On, and follow the instructions provided in section [Enabling Backup Archiving](backup_archiving.md). |

[![Adding Backup Policy](images/policy_monthly_schedule.webp)](images/policy_monthly_schedule.webp "Adding Backup Policy")

Page updated 11/11/2025

Page content applies to build 7.0.0.47
