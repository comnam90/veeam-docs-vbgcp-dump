---
title: "How Upgrade Works"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/vbgc_hiw_upgrade_5.html"
last_updated: "12/16/2025"
product_version: "7.0.0.47"
---

# How Upgrade Works


When you upgrade the backup appliance from version 5 to version 7, Veeam Backup & Replication performs the following steps:

1. Instructs Veeam Backup for Google Cloud to create a cloud-native snapshot of the original appliance. If the upgrade process fails, the appliance will be reverted to the created snapshot.

This snapshot will be automatically removed by Veeam Backup & Replication from Google Cloud after the upgrade operation completes successfully.

1. Stops all running backup and restore sessions on the original backup appliance.
2. Upgrades the appliance configuration database to PostgreSQL 16.
3. Saves the following configuration files and settings to the data disk: the appliance configuration file (/etc/veeam/gcpbackup/veeam-gcp-backup.conf), nginx configuration files (/etc/nginx/nginx.conf, /etc/nginx/proxy\_params), users, MFA and time zone settings, and Linux environment (/etc/ssh/, /root/, /home/).
4. Deploys a temporary VM instance from the Ubuntu 22.04 LTS image.
5. Installs a version 7 of the backup appliance to the temporary VM.
6. Detaches the boot disk from the newly created VM instance.
7. Detaches the outdated boot disk and attaches the new boot disk to the original appliance.
8. Removes the outdated boot disk from Google Cloud.
9. Restores the configuration files and settings saved at step 4 to the new boot disk.
10. Removes the temporary VM instance.


