---
title: "performing_instance_restore_console"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_instance_restore_console.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can restore an entire VM instance from a cloud-native snapshot or an image-level backup. Veeam Backup & Replication allows you to restore one or more VM instances at a time, to the original location or to a new location.

|  |
| --- |
| Important |
| When restoring a VM instance, Veeam Backup for Google Cloud recovers data from all zonal and regional persistent disks (standard, balanced, extreme and SSD) attached to the instance. However, when it comes to local SSDs (SCSI and NVMe), Veeam Backup for Google Cloud is able to recover only the configuration of these disks due to [technical reasons](https://cloud.google.com/compute/docs/disks/local-ssd#data_persistence). |

How Instance Restore Works

To restore VM instances from cloud-native snapshots, Veeam Backup & Replication uses [native Google Cloud capabilities](https://cloud.google.com/compute/docs/disks/create-snapshots#restore-snapshots). To restore VM instances from image-level backups, Veeam Backup & Replication uses different algorithms depending on whether a backup appliance is added to the backup infrastructure:

* If the backup appliance is connected to the backup server, Veeam Backup & Replication uses the restore algorithm described in section [Performing Instance Restore](restore_entire_instance_vm.md).
* If the backup appliance is not connected to the backup server, Veeam Backup & Replication uses the restore algorithm described in the Veeam Backup & Replication User Guide, section [How Restore to Google Compute Engine Works](https://helpcenter.veeam.com/docs/vbr/userguide/restore_google_hiw.html?ver=13).

How to Perform Instance Restore

To restore an entire VM instance, do the following:

1. [Launch the Restore to Google Compute Engine wizard](restore_to_google_launch.md).
2. [Select a restore point](restore_to_google_vm.md).
3. [Choose a restore mode](restore_to_google_mode.md).
4. [Select a project, region and an availability zone](restore_to_google_region.md).
5. [Specify instance type and encryption settings](restore_to_google_type.md).
6. [Specify a new name for the instance](restore_to_google_name.md).
7. [Configure network settings](restore_to_google_network.md).
8. [Specify a restore reason](restore_to_google_reason.md).
9. [Finish working with the wizard](restore_to_google_summary.md).

Page updated 11/18/2025

Page content applies to build 7.0.0.47
