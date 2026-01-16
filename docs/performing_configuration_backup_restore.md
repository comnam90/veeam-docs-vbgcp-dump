---
title: "performing_configuration_backup_restore"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_configuration_backup_restore.html"
last_updated: "2/7/2024"
product_version: "7.0.0.47"
---


In this article

You can back up and restore the configuration database that stores data collected from Veeam Backup for Google Cloud for the existing backup policies, protected VM, Cloud SQL and Cloud Spanner instances, connected Google Cloud projects, logged session records and so on. If the backup appliance goes down for some reason, you can reinstall it and quickly restore its configuration from a configuration backup. You can also use a configuration backup to migrate the configuration of one backup appliance to another backup appliance in Google Cloud.

It is recommended that you regularly perform configuration backup for every backup appliance present in Google Cloud. Periodic configuration backups reduce the risk of data loss and minimize the administrative overhead costs in case any problems with the backup appliances occur.

You can run configuration backup manually on demand, or instruct Veeam Backup for Google Cloud to do it automatically on a regular basis.

In This Section

* [Performing Configuration Backup](performing_configuration_backup.md)
* [Performing Configuration Restore](performing_configuration_restore.md)

Page updated 2/7/2024

Page content applies to build 7.0.0.47
