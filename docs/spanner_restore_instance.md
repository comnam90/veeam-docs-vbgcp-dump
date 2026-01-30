---
title: "Performing Spanner Instance Restore"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/spanner_restore_instance.html"
last_updated: "1/17/2024"
product_version: "7.0.0.47"
---

# Performing Spanner Instance Restore


In case a disaster strikes, you can restore an entire Cloud Spanner instance from a cloud-native snapshot or image-level backup. Veeam Backup for Google Cloud allows you to restore one or more Cloud Spanner instances at a time, to the original location or to a new location.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not support restore to the original location if the source Cloud Spanner instance is still present in the location or if its name is reserved. You can delete the instance; however, keep in mind that you must delete all its cloud-native snapshots first — due to [technical limitations in Google Cloud](https://cloud.google.com/spanner/docs/create-manage-instances#delete-instance). |

To restore a protected Cloud Spanner instance, do the following:

1. [Launch Cloud Spanner instance restore wizard](spanner_restore_wizard.md)
2. [Select a restore point](spanner_restore_point.md).
3. [Choose a restore mode](spanner_restore_mode.md).
4. [Select a service account](spanner_restore_service_account.md).
5. [Select a project](spanner_restore_project.md).
6. [Select a region and an availability zone](spanner_restore_region.md).
7. [Specify a new name and machine type for the instance](spanner_restore_type.md).
8. [Configure encrytion settings](spanner_restore_encryption.md).
9. [Run configuration and permission checks](spanner_restore_checks.md).
10. [Specify a restore reason](spanner_restore_reason.md).
11. [Finish working with the wizard](spanner_restore_finish.md).

|  |
| --- |
| Important |
| Before you start Cloud Spanner instance restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |


