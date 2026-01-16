---
title: "disk_restore_point"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/disk_restore_point.html"
last_updated: "11/4/2025"
product_version: "7.0.0.47"
---


In this article

At the Instances step of the wizard, select a restore point that will be used to restore persistent disks of the selected VM instance. By default, Veeam Backup for Google Cloud uses the most recent valid restore point. However, you can restore the disks to an earlier state.

To select a restore point, do the following:

1. Select the VM instance and click Restore Point.
2. In the Select restore point window, select the necessary restore point and click Apply.

To help you choose a restore point, Veeam Backup for Google Cloud provides the following information on each available restore point:

* Creation Time — the date when the restore point was created.
* Destination — the type of the restore point:

* Snapshot — a cloud-native snapshot created by a backup policy.
* Manual Snapshot — a cloud-native snapshot created manually.

* Backup — an image-level backup created by a backup policy.

* State — the result of the latest health check performed for the restore point.

* Storage Class — the storage class of a backup repository where the restore point is stored (applies only to image-level backups).
* Project — a project that manages the protected VM instance.
* Region — a region in which the protected VM instance resides.
* Retention — a retention configured for the backup policy that created the restore point.

|  |
| --- |
| Tip |
| If you want to restore only specific persistent disks of the selected VM, you can exclude the unnecessary disks from the restore process. To do that, click Exclusions to open the Exclude disks from restore window, select check boxes next to the disks that you do not want to restore, and click Apply. |

[![Restoring VM Disks](images/disk_restore_point.webp)](images/disk_restore_point.webp "Restoring VM Disks")

Page updated 11/4/2025

Page content applies to build 7.0.0.47
