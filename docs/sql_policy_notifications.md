---
title: "sql_policy_notifications"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/sql_policy_notifications.html"
last_updated: "11/11/2025"
product_version: "7.0.0.47"
---


In this article

At the Settings step of the wizard, you can enable automatic retries, schedule health checks and specify notification settings for the backup policy.

Automatic Retry Settings

To instruct Veeam Backup for Google Cloud to run the backup policy again if it fails on the first try, do the following:

1. In the Retries section of the step, select the Automatically retry failed policy check box.
2. In the field to the right of the check box, specify the maximum number of attempts to run the backup policy. The time interval between retries is 15 minutes.

When retrying backup policies, Veeam Backup for Google Cloud processes only those Cloud SQL instances that failed to be backed up during the previous attempt.

|  |
| --- |
| Note |
| The automatic retry settings apply only to backup policies that run according to specific schedules — these settings do not apply to policies [started manually](starting_stopping_backup_policies.md). |

Health Check Settings

If you have enabled creation of image-level backups at [step 5](sql_policy_target.md), you can instruct Veeam Backup for Google Cloud to periodically perform a health check for backup restore points created by the backup policy. During the health check, Veeam Backup for Google Cloud performs an availability check for data blocks in the whole regular backup chain, and a cyclic redundancy check (CRC) for metadata to verify its integrity. The health check helps you ensure that the restore points are consistent and that you will be able to restore data using these restore points. For more information on the health check, see [How Health Check Works](how_health_check_works_sql.md).

|  |
| --- |
| Note |
| During a health check, Veeam Backup for Google Cloud does not verify archived restore points created by the policy. |

To instruct Veeam Backup for Google Cloud to perform a monthly health check, do the following:

1. In the Health check section of the step, set the Enable health check toggle to On.
2. Use the Run on drop-down lists to schedule a specific day for the health check to run.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud performs the health check during the last policy session that runs on the day when the health check is scheduled. If another backup policy session runs on the same day, Veeam Backup for Google Cloud will not perform the health check during that session. For example, if the backup policy is scheduled to run multiple times on Saturday, and the health check is also scheduled to run on Saturday, the health check will only be performed during the last policy session on Saturday. |

Notification Settings

To instruct Veeam Backup for Google Cloud to send email notifications for the backup policy, do the following:

1. In the Notifications section of the step, set the Enable notifications toggle to On.

If you set the toggle to Off, Veeam Backup for Google Cloud will send notifications according to the configured [global notification settings](configuring_global_notification_settings.md).

1. In the Email field, specify an email address of a recipient. Use a semicolon to separate multiple recipient addresses.

1. Use the Notify on list to choose whether you want Veeam Backup for Google Cloud to send email notifications in case the backup policy completes successfully, completes with warnings or completes with errors.
2. Select the Suppress notifications until the last retry check box to receive a notification about the final backup policy result.

If you do not select the check box, Veeam Backup for Google Cloud will send a notification for every backup policy retry.

|  |
| --- |
| Note |
| If you specify the same email recipient in both backup policy notification and [global notification settings](configuring_global_notification_settings.md), Veeam Backup for Google Cloud will send each notification to this recipient twice. |

[![Adding Backup Policy](images/sql_policy_notifications.webp)](images/sql_policy_notifications.webp "Adding Backup Policy")

Page updated 11/11/2025

Page content applies to build 7.0.0.47
