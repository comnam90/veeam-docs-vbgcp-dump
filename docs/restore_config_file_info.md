---
title: "restore_config_file_info"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_config_file_info.html"
last_updated: "11/20/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup & Replication will analyze the content of the selected backup file and display the following information:

* Backup file — the date and time when the backup file was created, the size of the file, the file location and so on.
* [Applies If the configuration backup file selected at [step 2](restore_config_file.md) is not stored on the backup server] Downloaded backup file — the temporary location of the configuration backup file on the backup server.
* Product — the name of the product and its version that was installed on the initial appliance.
* Catalogs — configuration data saved in the file (such as the number of configured backup policies, added user accounts, created repositories, logged session records and so on).

At the Backup Contents step of the wizard, review the provided information and click Next to confirm that you want to use the selected file to restore the configuration data.

![Step 3. Review Backup File Info](images/config_restore_file_info.webp)

Page updated 11/20/2025

Page content applies to build 7.0.0.47
