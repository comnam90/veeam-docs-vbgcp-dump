---
title: "managing_repositories"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_repositories.html"
last_updated: "2/15/2024"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud uses Google Cloud storage buckets as target locations for image-level backups of VM, Cloud SQL and Cloud Spanner instances, and for backups of the configuration database. To store backups in storage buckets, configure backup repositories. A repository is a specific subdirectory created by Veeam Backup for Google Cloud in a storage bucket.

|  |
| --- |
| Important |
| A backup repository must not be managed by multiple backup appliances simultaneously. Retention sessions running on different appliances may corrupt backups stored in the repository, which may result in unpredictable data loss. |

In This Section

* [Adding Backup Repositories Using Console](add_repository.md)
* [Adding Backup Repositories Using Web UI](adding_repositories.md)
* [Editing Backup Repositories](editing_repositories.md)
* [Removing Backup Repositories](removing_repositories.md)

Page updated 2/15/2024

Page content applies to build 7.0.0.47
