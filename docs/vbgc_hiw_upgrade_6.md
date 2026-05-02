---
title: "How Upgrade Works"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/vbgc_hiw_upgrade_6.html"
last_updated: "12/16/2025"
product_version: "7.0.0.47"
---

# How Upgrade Works


When you upgrade the backup appliance from version 6 to version 7, Veeam Backup & Replication performs the following steps:

1. Instructs Veeam Backup for Google Cloud to create a cloud-native snapshot of the original appliance. If the upgrade process fails, the appliance will be reverted to the created snapshot.

This snapshot will be automatically removed by Veeam Backup & Replication from Google Cloud after the upgrade operation completes successfully.

1. Stops all running backup and restore sessions on the original backup appliance.
2. Checks for updates using the Veeam Updater service and installs them on the backup appliance
3. Initializes the backup appliance services.
4. Removes the temporary cloud-native snapshot.


