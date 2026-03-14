---
title: "Disk Restore"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_disk.html"
last_updated: "3/11/2026"
product_version: "7.0.0.47"
---

# Disk Restore


To restore persistent disks from a cloud-native snapshot, Veeam Backup for Google Cloud uses [native Google Cloud capabilities](https://cloud.google.com/compute/docs/disks/restore-and-delete-snapshots). To restore persistent disks from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the restored persistent disks will reside.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Creates empty persistent disks and attaches them to the worker instance.

The number of empty persistent disks equals the number of disks you want to restore.

|  |
| --- |
| Note |
| Every time before creating persistent disks, Veeam Backup for Google Cloud checks whether the total size of pd-standard disks breaches the zone quota for the project in which the worker instance is deployed. If the total disk size is less than 1500 GB, Veeam Backup for Google Cloud temporarily attaches an additional empty disk to the worker instance — but only for the duration of the restore process and if the quota allows attaching the disk. This allows Veeam Backup for Google Cloud to speed up the data transfer to reduce your restore costs. |

1. Restores backed-up data to the empty persistent disks on the worker instance.
2. Takes cloud-native snapshots of the persistent disks with the restored data.
3. Creates disks from snapshots in the target location (that is, the project and region specified for the restore operation).
4. Removes the worker instance from Google Cloud.
5. Removes all the created snapshots from Google Cloud Storage.

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud does not attach the restored persistent disks to any VM instances — the disks are placed to the specified location as standalone persistent disks. |

To learn how to restore persistent disks attached to a VM instance from a cloud-native snapshot or an image-level backup, see [Performing Disk Restore](performing_disk_restore.md).


