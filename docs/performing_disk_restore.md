---
title: "performing_disk_restore"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_disk_restore.html"
last_updated: "8/30/2023"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore corrupted persistent disks of a VM instance from a cloud-native snapshot or image-level backup. Veeam Backup for Google Cloud allows you to restore persistent disks to the original location or to a new location.

|  |
| --- |
| Important |
| You can restore zonal and regional persistent disks of all types: standard (pd-standard), balanced (pd-balanced), extreme (pd-extreme) and SSD (pd-ssd). Restore of local SSDs (SCSI and NVMe) is not supported due to [technical reasons](https://cloud.google.com/compute/docs/disks/local-ssd#data_persistence). |

To restore persistent disks attached to a protected VM instance, do the following:

1. [Launch the Disk Restore wizard](disk_restore_wizard.md).
2. [Select a restore point](disk_restore_point.md).
3. [Choose a restore mode](disk_restore_mode.md).
4. [Select a service account](disk_restore_service_account.md).
5. [Select a project](disk_restore_project.md).
6. [Select a region and an availability zone](disk_restore_region.md).
7. [Enable encryption](disk_restore_encryption.md).
8. [Specify new names for the disks](disk_restore_names.md).
9. [Run configuration and permission checks](disk_restore_checks.md).
10. [Specify a restore reason](disk_restore_reason.md).
11. [Finish working with the wizard](disk_restore_finish.md).

|  |
| --- |
| Important |
| Before you start disk restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |

Page updated 8/30/2023

Page content applies to build 7.0.0.47
