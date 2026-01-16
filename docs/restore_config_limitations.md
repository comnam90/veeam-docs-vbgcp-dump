---
title: "restore_config_limitations"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_config_limitations.html"
last_updated: "11/23/2023"
product_version: "7.0.0.47"
---


In this article

Before you restore configuration of a backup appliance, consider the following:

* Configuration restore of backup appliances that run Veeam Backup for Google Cloud version 2.0 is not supported.
* Make sure that there are no sessions currently running on the backup appliance. Also, make sure that there are no backup policies scheduled to run during restore. Otherwise, backups created by these policies may be corrupted.
* If the backup appliance requires an upgrade, perform it before you start configuration restore. Otherwise, Veeam Backup & Replication will not be able to perform the restore operation. To learn how to upgrade appliances, see [Upgrading Appliances](updating_vb.md).
* If you remove the backup appliance from the backup infrastructure, you will not be able to restore its configuration. However, you will be able to restore the configuration to another appliance currently added to the backup infrastructure.
* If you want to restore the configuration of the backup appliance to another one, you must remove the initial appliance from the backup infrastructure beforehand.

* Make sure that repositories added to the backup appliance are not managed by any other appliances. Otherwise, retention sessions running on different appliances may corrupt backup files stored in the repositories, which may result in unpredictable data loss.

* The backup appliance to which you restore the configuration preserves its TLS certificate.

* During configuration restore, Veeam Backup & Replication will overwrite custom settings of the Linux configuration file on the backup appliance with the settings saved in the configuration backup file.

Page updated 11/23/2023

Page content applies to build 7.0.0.47
