---
title: "performing_database_restore_ui"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_database_restore_ui.html"
last_updated: "8/30/2023"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore corrupted databases of a Cloud SQL instance from an image-level backup. Veeam Backup for Google Cloud allows you to restore databases to the original location or to a new location.

|  |
| --- |
| Note |
| Due to [technical limitations in Google Cloud](https://cloud.google.com/sql/docs/troubleshooting#managing-instances), Veeam Backup for Google Cloud does not support restore to the original location if the source database is still present in the location. |

To restore databases of a protected Cloud SQL instance, do the following:

1. [Launch the Database Restore wizard](database_restore_wizard.md).
2. [Select databases](database_restore_point.md).
3. [Select a project](database_restore_project.md).
4. [Configure target instance settings](database_restore_instance.md).
5. [Check required permissions](database_restore_checks.md).
6. [Specify a restore reason](database_restore_reason.md).
7. [Finish working with the wizard](database_restore_finish.md).

|  |
| --- |
| Important |
| Before you start Cloud SQL database restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |

Page updated 8/30/2023

Page content applies to build 7.0.0.47
