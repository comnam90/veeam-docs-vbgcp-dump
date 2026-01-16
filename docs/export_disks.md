---
title: "export_disks"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/export_disks.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup & Replication allows you to export disks, that is, to restore disks of VM instances from image-level backups created by Veeam Backup for Google Cloud and to convert them to the VMDK, VHD or VHDX format. You can save the converted disks to any server added to the backup infrastructure or place the disks on a datastore connected to an ESXi host (for the VMDK disk format only). For more information, see the Veeam Backup & Replication User Guide, section [Disk Export](https://helpcenter.veeam.com/docs/vbr/userguide/disk_export.html?ver=13).

|  |
| --- |
| Important |
| Disk export can be performed only using backup files stored in backup repositories for which you have specified HMAC keys associated with the service accounts that are used to access the repositories. To learn how to specify credentials for repositories, see sections [Creating New Repositories](add_repo_service_account.md) and [Connecting to Existing Appliances](connect_appliance_repo.md). |

To export disks of a VM instance, do the following:

1. In the Veeam Backup & Replication console, open the Home view.
2. Navigate to Backups > External Repository.
3. Expand the backup policy that protects a VM instance whose disks you want to restore, select the necessary instance and click Export Disk on the ribbon.
4. Complete the Export Disk wizard as described in the Veeam Backup & Replication User Guide, section [Exporting Disks](https://helpcenter.veeam.com/docs/vbr/userguide/disk_export_machine.html?ver=13).

[![Export disks](images/export_disks.webp)](images/export_disks.webp "Export disks")

Page updated 11/18/2025

Page content applies to build 7.0.0.47
