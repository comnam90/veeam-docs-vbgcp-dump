---
title: "how_health_check_works_spanner"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/how_health_check_works_spanner.html"
last_updated: "2/2/2024"
product_version: "7.0.0.47"
---


In this article

When Veeam Backup for Google Cloud saves a new restore point to a backup repository, it calculates CRC values for metadata in the backup chain and saves these values to the chain metadata, together with the Cloud Spanner instance data. When performing a health check, Veeam Backup for Google Cloud verifies availability of data blocks for each restore point and uses the saved values to ensure that the restore points being verified are consistent.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud performs the health check during the last policy session that runs on the day when the health check is scheduled. If another backup policy session runs on the same day, Veeam Backup for Google Cloud will not perform the health check during that session. For example, if the backup policy is scheduled to run multiple times on Saturday, and the health check is also scheduled to run on Saturday, the health check will only be performed during the last policy session on Saturday. |

Veeam Backup for Google Cloud performs the health check in the following way:

1. As soon as the backup policy session completes successfully, Veeam Backup for Google Cloud starts the health check as a new session. For each restore point in the regular backup chain, Veeam Backup for Google Cloud calculates CRC values for backup metadata and compares them to the CRC values that were previously saved to the restore point. Veeam Backup for Google Cloud also checks whether data blocks that are required to rebuild the restore point are available.

If the backup policy session completes with an error, Veeam Backup for Google Cloud tries to run the backup policy again, taking into account the maximum number of retries specified in the [automatic retry settings](spanner_policy_notifications.md). After the first successful retry (or after the last one out of the maximum number of retries), Veeam Backup for Google Cloud starts the health check.

1. If Veeam Backup for Google Cloud does not detect data inconsistency, the health check session completes successfully. Otherwise, the session completes with an error.

Depending on the detected data inconsistency, Veeam Backup for Google Cloud performs the following operations:

* If the health check detects corrupted metadata in a restore point, Veeam Backup for Google Cloud marks the regular backup chain as corrupted in the configuration database. During the next backup policy session, Veeam Backup for Google Cloud copies the full Cloud Spanner instance image, creates a new restore point and starts a new backup chain in the backup repository.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud supports metadata check for encrypted backup chains unless the metadata is corrupted. |

* If the health check detects corrupted data blocks in a restore point, Veeam Backup for Google Cloud marks the restore point that includes the corrupted data blocks as incomplete in the configuration database. During the next backup policy session, Veeam Backup for Google Cloud copies the full Cloud Spanner instance image, creates a new restore point and starts a new backup chain in the backup repository.

Page updated 2/2/2024

Page content applies to build 7.0.0.47
