---
title: "performing_spanner_backup"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_spanner_backup.html"
last_updated: "11/13/2023"
product_version: "7.0.0.47"
---


In this article

One backup policy can be used to process one or more Cloud Spanner instances within one Google Cloud project or folder. The scope of data that you can protect in a project or folder is limited by permissions of a service account that is specified in the backup policy settings.

Before you create a Cloud Spanner backup policy, check the following prerequisites:

* If you plan to create image-level backups of Cloud Spanner instances, backup infrastructure components that will take part in the backup process must be added to the backup infrastructure and configured properly. These include [backup repositories](managing_repositories.md) and [worker instances](managing_workers.md).
* If you plan to receive email notifications on the backup policy results, configure SMTP server settings first. For more information, see [Configuring Global Notification Settings](configuring_global_notification_settings.md).

To schedule data protection tasks to run automatically, [create backup policies](creating_spanner_backup_policies.md). For each protected Cloud Spanner instance, you can also [take a cloud-native snapshot manually](creating_manual_snapshots_spanner.md) when needed.

Page updated 11/13/2023

Page content applies to build 7.0.0.47
