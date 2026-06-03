---
title: "Performing Configuration Backup Using Console"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_configuration_backup_console.html"
last_updated: "6/2/2026"
product_version: "7.0.0.47"
---

# Performing Configuration Backup Using Console


When Veeam Backup & Replication performs configuration backup, it backs up the configuration of the backup server and also configurations of all backup appliances added to the backup infrastructure.

You can perform configuration backup manually or instruct Veeam Backup & Replication to do it automatically on a regular basis:

* To perform configuration backup manually, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Running Configuration Backups Manually](https://helpcenter.veeam.com/docs/vbr/userguide/vbr_config_manually.html?ver=13).
* To instruct Veeam Backup & Replication to perform configuration backup automatically, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Scheduling Configuration Backups](https://helpcenter.veeam.com/docs/vbr/userguide/vbr_config_schedule.html?ver=13).

|  |
| --- |
| Important |
| For Veeam Backup & Replication to be able to back up configurations of managed backup appliances, you must enable backup file encryption in the configuration backup settings. |

Before You Begin

If you plan to back up the configuration of a managed backup appliance, keep in mind the following limitations and considerations:

* You must enable backup file encryption in the configuration backup settings. Otherwise, Veeam Backup & Replication will back up only the backup server configuration.

To learn how to create encrypted configuration backups, see the Veeam Backup & Replication User Guide, section [Creating Encrypted Configuration Backups](https://helpcenter.veeam.com/docs/vbr/userguide/config_backup_encrypted.html?ver=13).

* You cannot store configuration backups in scale-out backup repositories and external repositories.
* For Veeam Backup & Replication to be able to back up the appliance configuration, the backup appliance must be available and must run a Veeam Backup for Google Cloud version that is compatible with the Veeam Backup & Replication version.

For the list of compatible versions, see [System Requirements](system_requirements.md).

* During configuration backup, Veeam Backup & Replication can process only 3 appliances at a time — the appliances exceeding this limit are queued.
* To enable data loss protection in case you lose or forget the password used for data encryption, you can use Veeam Backup Enterprise Manager to decrypt backup files.

To learn how to let Veeam Backup & Replication encrypt and decrypt data with Enterprise Manager, see the Veeam Backup Enterprise Manager Guide, section [Managing Encryption Keys](https://helpcenter.veeam.com/docs/backup/em/em_manage_keys.html?ver=120).

Configuration Backup Location

Veeam Backup & Replication stores configuration backups of backup appliances in a repository specified in the configuration backup settings. Backups are saved to the \\VeeamConfigBackup\GCP folder.

|  |
| --- |
| Notes |
| * It is not recommended to store configuration backups in any folder on the backup server. Otherwise, you will not be able to restore the configurations of managed backup appliances in case the backup server goes down. * If the name of an appliance contains unsupported characters, these characters are replaced with the '\_' underscore symbol in the names of subfolders and backup files. |


