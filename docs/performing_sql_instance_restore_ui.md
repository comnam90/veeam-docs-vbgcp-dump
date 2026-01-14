---
title: "performing_sql_instance_restore_ui"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_sql_instance_restore_ui.html"
last_updated: "1/10/2024"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore an entire Cloud SQL instance from a cloud-native snapshot or image-level backup. Veeam Backup for Google Cloud allows you to restore one or more Cloud SQL instances at a time, to the original location or to a new location.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not support restore to the original location if the source Cloud SQL instance is still present in the location or if its name is reserved. However, note that if you delete an instance from Google Cloud, all its cloud-native snapshots will be deleted as well due to [technical limitations in Google Cloud](https://cloud.google.com/sql/docs/troubleshooting#backups). |

To restore a protected Cloud SQL instance, do the following:

1. [Launch the Cloud SQL Instance Restore wizard](sql_restore_wizard.md).
2. [Select a restore point](sql_restore_point.md).
3. [Choose a restore mode](sql_restore_mode.md).
4. [Select a service account](sql_restore_service_account.md).
5. [Select a project](sql_restore_project.md).
6. [Select a region and an availability zone](sql_restore_region.md).
7. [Specify a new name and machine type for the instance](sql_restore_type.md).
8. [Configure network settings](sql_restore_network.md).
9. [Configure security settings](sql_restore_encryption.md).
10. [Enable flag assignment](sql_restore_flags.md).
11. [Run configuration and permission checks](sql_restore_checks.md).
12. [Specify a restore reason](sql_restore_reason.md).
13. [Finish working with the wizard](sql_restore_finish.md).

|  |
| --- |
| Important |
| Before you start Cloud SQL instance restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |

Page updated 1/10/2024

Page content applies to build 7.0.0.47
