---
title: "restore_config_file"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_config_file.html"
last_updated: "11/20/2025"
product_version: "7.0.0.47"
---


In this article

At the Configuration Backup step of the wizard, do the following:

1. From the Backup repository list, select a repository where the configuration backup file is stored.

For a repository to be displayed in the Backup repository list, it must be added to the backup infrastructure as described in the Veeam Backup & Replication User Guide, section [Adding Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/repo_add.html?ver=13).

1. Click Browse and select the necessary file.

|  |
| --- |
| Note |
| If the selected configuration backup file is not stored on the backup server, Veeam Backup & Replication will copy the file to a temporary folder on the server and automatically delete it from the folder as soon as the restore process completes. |

![Step 2. Choose Backup File](images/config_restore_file.webp)

Page updated 11/20/2025

Page content applies to build 7.0.0.47
