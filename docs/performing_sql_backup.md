---
title: "Performing SQL Backup"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_sql_backup.html"
last_updated: "7/21/2023"
product_version: "7.0.0.47"
---

# Performing SQL Backup


One backup policy can be used to process one or more Cloud SQL instances within one Google Cloud project or folder. The scope of data that you can protect in a project or folder is limited by permissions of a service account that is specified in the backup policy settings.

Before you create a Cloud SQL backup policy, check the following prerequisites:

* If you plan to create image-level backups of Cloud SQL instances, backup infrastructure components that will take part in the backup process must be added to the backup infrastructure and configured properly. These include [backup repositories](managing_repositories.md) and [worker instances](managing_workers.md).
* If you plan to receive email notifications on the backup policy results, configure SMTP server settings first. For more information, see [Configuring Global Notification Settings](configuring_global_notification_settings.md).

|  |
| --- |
| Note |
| Veeam Backup for Google Cloud allows you to protect MySQL and PostgreSQL instances. SQL Server instances are not supported. For more information on types of Cloud SQL instances, see [Google Cloud documentation](https://cloud.google.com/sql/docs/features). |

To schedule data protection tasks to run automatically, [create backup policies](creating_sql_backup_policies.md). For each protected Cloud SQL instance, you can also [take a cloud-native snapshot manually](creating_manual_snapshots_sql.md) when needed.


