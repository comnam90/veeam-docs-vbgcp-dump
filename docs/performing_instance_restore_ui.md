---
title: "performing_instance_restore_ui"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_instance_restore_ui.html"
last_updated: "8/30/2023"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore an entire VM instance from a cloud-native snapshot or image-level backup. Veeam Backup for Google Cloud allows you to restore one or more VM instances at a time, to the original location or to a new location.

|  |
| --- |
| Important |
| When restoring a VM instance, Veeam Backup for Google Cloud recovers data from all zonal and regional persistent disks (standard, balanced, extreme and SSD) attached to the instance. However, when it comes to local SSDs (SCSI and NVMe), Veeam Backup for Google Cloud is able to recover only the configuration of these disks due to [technical reasons](https://cloud.google.com/compute/docs/disks/local-ssd#data_persistence). |

To restore a protected VM instance, do the following:

1. [Launch the VM Instance Restore wizard](vm_restore_wizard.md).
2. [Select a restore point](vm_restore_point.md).
3. [Choose a restore mode](vm_restore_mode.md).
4. [Select a service account](vm_restore_service_account.md).
5. [Select a project](vm_restore_project.md).
6. [Select a region and an availability zone](vm_restore_region.md).
7. [Enable encryption](vm_restore_encryption.md).
8. [Specify a new name and machine type for the instance](vm_restore_type.md).
9. [Configure network settings](vm_restore_network.md).
10. [Run configuration and permission checks](vm_restore_checks.md).
11. [Specify a restore reason](vm_restore_reason.md).
12. [Finish working with the wizard](vm_restore_finish.md).

|  |
| --- |
| Important |
| Before you start VM instance restore, make sure that network settings are configured for each region where worker instances will be deployed during the restore process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md). |

Page updated 8/30/2023

Page content applies to build 7.0.0.47
