---
title: "overview_sql"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/overview_sql.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---


In this article

To produce cloud-native snapshots and image-level backups of Cloud SQL instances, Veeam Backup for Google Cloud runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process and so on.

Veeam Backup for Google Cloud does not install agent software inside instances to back up Cloud SQL data — it uses native Google Cloud capabilities instead. During every backup session, Veeam Backup for Google Cloud creates a cloud-native snapshot of each Cloud SQL instance added to a backup policy. The cloud-native snapshot is further used to create an image-level backup of the instance. For more information on how Cloud SQL instance backup works, see [SQL Backup](backup_sql.md).

How to Protect Cloud SQL Instances

To create an SQL backup policy, complete the following steps:

1. [Check limitations and prerequisites](limitations.md#backup).
2. [Add service accounts](adding_service_accounts.md).
3. [Connect projects and folders](adding_projects.md).
4. [Add backup repositories](adding_repositories.md).
5. [Configure worker instance settings](adding_worker_configurations.md).
6. [Configure global retention and email notification settings](configuring_general_settings.md).
7. [Complete the Add Cloud SQL Policy wizard.](creating_sql_backup_policies.md)

Related Topics

[SQL Restore](restore_sql.md)

Page updated 6/13/2025

Page content applies to build 7.0.0.47
