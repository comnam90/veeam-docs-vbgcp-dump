---
title: "performing_flr"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_flr.html"
last_updated: "12/2/2025"
product_version: "7.0.0.47"
---


In this article

In case a disaster strikes, you can recover corrupted or missing files of a VM instance from a cloud-native snapshot or image-level backup. Veeam Backup for Google Cloud allows you to download the necessary files and folders to a local machine or to their original location using the [file-level recovery browser](flr_items.md).

|  |
| --- |
| Important |
| * File-level recovery is supported for FAT, FAT32, NTFS, ext2, ext3, ext4, XFS and Btrfs file systems only. However, attributes of files and folders stored in FAT and FAT32 file systems cannot be restored to the original location. * Restore of NTFS links (hard links, junction points, symbolic links) to the original location is not supported. * Worker instances deployed during file-level restore operations access the file-level recovery browser through a public network. To enable access to the browser through private networks, you need to [configure private network deployment](appendix_private_deployment.md). |

To recover files and folders of a protected VM instance, do the following:

1. [Launch the File-Level Recovery wizard](flr_wizard.md).
2. [Select a restore point](flr_restore_point.md).
3. [Choose a restore mode](flr_restore_mode.md).
4. [Run configuration and permission checks](flr_permissions.md).
5. [Specify a recovery reason](flr_reason.md).
6. [Finish working with the wizard — start a recovery session](flr_open_session.md).
7. [Choose files and folders to recover](flr_items.md).
8. [Stop the recovery session](flr_stop_session.md).

|  |
| --- |
| Important |
| Before you start file-lever recovery, check the following prerequisites:   * Make sure that network settings are configured for each region where worker instances will be deployed during the recovery process. For information on how to configure network settings, see [Adding Worker Configurations](worker_network_settings.md).  * Make sure that the machine where you plan to open the file-level recovery browser is allowed to access the worker instances over the internet. To enable internet access for a worker instance, update the firewall rule specified in the instance network settings to add an inbound rule for HTTPS traffic on the port 443. For information on how to update firewall rules, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/using-firewalls). |

Page updated 12/2/2025

Page content applies to build 7.0.0.47
