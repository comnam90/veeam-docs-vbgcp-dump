---
title: "restore_file_level"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_file_level.html"
last_updated: "11/28/2024"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud allows you to recover the files and folders of a backed-up VM instance to a local machine or to the original location.

File-Level Recovery to Local Machine

To recover files and folders of a backed-up VM instance, Veeam Backup for Google Cloud performs the following steps:

1. Deploys a worker instance within the worker project in either of the following Google Cloud regions.

* To recover files and folders from a cloud-native snapshot, the worker instance is deployed in the region in which the VM instance resides.
* To recover files and folders from an image-level backup, the worker instance is deployed in the region in which the storage bucket with backed-up data resides.

1. When recovering files and folders from a cloud-native snapshot, Veeam Backup for Google Cloud copies the persistent disks of the VM instance from the snapshot and attaches them to the worker instance.

When recovering files and folders from an image-level backup, the disks are not physically extracted from the backup — Veeam Backup for Google Cloud emulates their presence on the worker instance. The source backup itself remains in the read-only state.

1. Launches the file-level recovery browser.

The file-level recovery browser displays the directory structure of the backed-up VM instance. In the browser, you select the necessary files and folders to recover.

1. Saves the selected files and folders to the local machine.
2. Removes the worker instance from Google Cloud.

File-Level Recovery to Original Location

To recover files and folders of a backed-up VM instance to the original location, Veeam Backup for Google Cloud performs the following steps:

1. When recovering files and folders from a cloud-native snapshot, Veeam Backup for Google Cloud copies the persistent disks of the VM instance from the snapshot and attaches them to the worker instance.

When recovering files and folders from an image-level backup, the disks are not physically extracted from the backup — the source backup itself remains in the read-only state.

1. Deploys a worker instance within the worker project in either of the following Google Cloud regions.

* To recover files and folders from a cloud-native snapshot, the worker instance is deployed in the region in which the target VM instance resides.
* To recover files and folders from an image-level backup, the worker instance is deployed in the region in which the storage bucket with backed-up data resides.

1. When recovering files and folders from a cloud-native snapshot, Veeam Backup for Google Cloud attaches the copied persistent disks to the worker instance.

When recovering files and folders from an image-level backup, Veeam Backup for Google Cloud emulates disk presence on the worker instance.

1. [For Linux-operated instances] Generates an SSH key for veeam\_restore\_user and uploads the key to the target VM instance using Compute Engine API.

[For Windows-operated instances] Creates credentials for veeam\_restore\_user on the target VM instance using Compute Engine API.

1. Establishes an [encrypted IAP tunnel](https://cloud.google.com/iap/docs/using-tcp-forwarding) between the backup appliance and the target VM instance to enable administrative access to the instance.
2. Creates a storage bucket with the veeam-transfer-files-{GUID} name in the region where the target VM instance resides, which is required to copy and launch the restore utilities.

Veeam Backup for Google Cloud will use the storage bucket created during the first file-level recovery session for all the subsequent recovery sessions — unless you delete the bucket from Google Cloud manually.

1. Launches the file-level recovery browser.

The file-level recovery browser displays the directory structure of the backed-up VM instance. In the browser, you select the necessary files and folders to recover.

1. Recovers the selected items to the target VM instance using the [Pub/Sub service](https://cloud.google.com/pubsub/docs/pubsub-basics).
2. Removes the restore utilities from the storage bucket.
3. Removes the worker instance from Google Cloud.

To learn how to recover individual files and folders of a VM instance from a cloud-native snapshot or an image-level backup, see [Performing File-Level Recovery](performing_flr.md).

Page updated 11/28/2024

Page content applies to build 7.0.0.47
