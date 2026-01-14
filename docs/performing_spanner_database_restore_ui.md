---
title: "performing_spanner_database_restore_ui"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_spanner_database_restore_ui.html"
last_updated: "8/28/2024"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore corrupted databases of a Cloud Spanner instance from an image-level backup or a cloud-native snapshot. Veeam Backup for Google Cloud allows you to restore databases to the original location or to a new location.

|  |
| --- |
| Note |
| Due to [technical limitations in Google Cloud](https://cloud.google.com/spanner/docs/backup/restore-backup-overview), Veeam Backup for Google Cloud does not support restore to the original location if the source database is still present in the location. |

To restore databases of a protected Cloud Spanner instance, do the following:

1. [Launch the Cloud Spanner Database Restore wizard](spanner_database_restore_wizard.md).
2. [Select databases](spanner_database_restore_point.md).
3. [Select a project](spanner_database_restore_project.md).
4. [Configure target instance settings](spanner_database_restore_instance.md).
5. [Check required permissions](spanner_database_restore_checks.md).
6. [Specify a restore reason](spanner_database_restore_reason.md).
7. [Finish working with the wizard](spanner_database_restore_finish.md).

|  |
| --- |
| Important |
| Before you start Cloud Spanner database restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |

Page updated 8/28/2024

Page content applies to build 7.0.0.47
