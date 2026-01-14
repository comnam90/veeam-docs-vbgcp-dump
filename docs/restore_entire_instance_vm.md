---
title: "restore_entire_instance_vm"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_entire_instance_vm.html"
last_updated: "9/5/2024"
product_version: "7.0.0.47"
---


In this article

To restore a VM instance from a cloud-native snapshot, Veeam Backup for Google Cloud uses [native Google Cloud capabilities](https://cloud.google.com/compute/docs/disks/restore-and-delete-snapshots). To restore a VM instance from an image-level backup, Veeam Backup for Google Cloud performs the following steps:

1. Deploys a worker instance within the worker project in the Google Cloud region in which the restored VM instance will reside.

For more information on how to specify a project for worker instances, see [Managing Worker Configurations](managing_worker_configurations.md).

1. Creates empty persistent disks and attaches them to the worker instance.

The number of empty persistent disks equals the number of persistent disks attached to the backed-up VM instance.

1. Restores backed-up data to the empty persistent disks on the worker instance.
2. Takes cloud-native snapshots of the persistent disks with the restored data.
3. Creates disks from the snapshots in the target location (that is, the project and region specified for the restore operation).
4. Removes the worker instance from Google Cloud.
5. Removes all the created snapshots from Google Cloud Storage.
6. Creates a VM instance in the target location and attaches the created persistent disks with the restored data to the VM instance.
7. [Applies only if you perform restore to the original location and if the source VM instance is still present in the location] Powers off the source VM instance, removes the source VM instance from Google Cloud and then renames the restored VM instance.

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to perform restore to the original location while source VM instances still exist there, the [deletion protection](https://cloud.google.com/compute/docs/instances/preventing-accidental-vm-deletion#:~:text=Setting%20deletion%20protection%20during%20instance%20creation,-By%20default%2C%20deletion&text=In%20the%20Google%20Cloud%20console,the%20Create%20an%20instance%20page.&text=Expand%20the%20Networking%2C%20disks%2C%20security,the%20Enable%20deletion%20protection%20checkbox.) setting must be disabled for the source instance. |

To learn how to restore an entire VM instance from a cloud-native snapshot or an image-level backup, see [Performing VM Instance Restore](performing_instance_restore_ui.md).

Page updated 9/5/2024

Page content applies to build 7.0.0.47
