---
title: "configuration"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/configuration.html"
last_updated: "10/22/2025"
product_version: "7.0.0.47"
---


In this article

To start working with Veeam Backup for Google Cloud, perform a number of steps for its configuration:

1. [Add backup appliances to the backup infrastructure](managing_appliances.md).
2. [Add repositories that will be used to store backed-up data](managing_repositories.md).
3. Configure the added backup appliances:

1. [Add service accounts to authorize requests to Google Cloud APIs](managing_service_accounts.md).
2. [Add projects and folders to get access to Google Cloud resources that you want to protect](managing_projects.md).
3. [[Optional] Add users to control access to Veeam Backup for Google Cloud](managing_permissions.md).
4. [Create worker configurations](managing_workers.md).
5. [[Optional] Configure global retention, email notification and Google authentication settings](configuring_general_settings.md).

|  |
| --- |
| Note |
| Even after you add projects that manage your Google Cloud resources and configure all the necessary settings, Veeam Backup for Google Cloud will not populate the lists of VM, Cloud SQL and Cloud Spanner instances on the [Resources page](viewing_resources.md) — unless you create backup policies and specify regions in which the instances reside, as described in sections [Performing VM Backup](performing_vm_backup.md), [Performing SQL Backup](performing_sql_backup.md) and [Performing Spanner Backup](performing_spanner_backup.md). |

Page updated 10/22/2025

Page content applies to build 7.0.0.47
