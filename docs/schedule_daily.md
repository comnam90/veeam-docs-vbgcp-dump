---
title: "schedule_daily"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/schedule_daily.html"
last_updated: "11/11/2025"
product_version: "7.0.0.47"
---


In this article

To create a daily schedule for the backup policy, at the Schedule step of the wizard, do the following:

1. Set the Daily schedule toggle to On and click Edit Daily Settings.
2. In the Create daily schedule section, select hours when the backup policy will create cloud-native snapshots and image-level backups. Use the Run at drop-down list to choose whether you want the backup policy to run every day, on weekdays (Monday through Friday) or on specific days.

If you want to protect VM instance data more frequently, you can instruct the backup policy to create multiple cloud-native snapshots per hour. To do that, click the link to the right of the Snapshots hour selection area, and specify the number of cloud-native snapshots that the backup policy will create within an hour.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not create image-level backups independently from cloud-native snapshots. That is why when you select hours for image-level backups, the same hours are automatically selected for cloud-native snapshots. To learn how Veeam Backup for Google Cloud performs backup, see [VM Backup](backup_vm.md). |

1. In the Configure daily retention section, configure retention policy settings for the daily schedule:

* For cloud-native snapshots, specify the number of restore points that you want to keep in a snapshot chain.

If the restore point limit is exceeded, Veeam Backup for Google Cloud removes the earliest restore point from the chain. For more information, see [Retention Policy for Snapshots](snapshot_retention_vm.md).

* For image-level backups, specify the number of days (or months) for which you want to keep restore points in a backup chain.

If a restore point is older than the specified time limit, Veeam Backup for Google Cloud removes the restore point from the chain. For more information, see [Retention Policy for Backups](backup_retention_vm.md).

1. To save changes made to the backup policy settings, click Apply.

[![Adding Backup Policy](images/policy_daily_schedule.webp)](images/policy_daily_schedule.webp "Adding Backup Policy")

Page updated 11/11/2025

Page content applies to build 7.0.0.47
