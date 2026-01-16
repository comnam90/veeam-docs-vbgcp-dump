---
title: "performing_backup_ui"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_backup_ui.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---


In this article

To produce cloud-native snapshots and image-level backups of VM, Cloud SQL and Cloud Spanner instances, Veeam Backup for Google Cloud runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where to store backups, when to start the backup process and so on.

One backup policy can be used to process multiple instances within different regions, but you can back up each instance with one backup policy at a time. If an instance is added to more than one backup policy, it will be processed only by a backup policy that has the highest priority. Other backup policies will skip this instance from processing. For information on how to set a priority for a backup policy, see [Setting Backup Policy Priority](backup_policy_priority.md).

In This Section

* [Performing VM Backup](performing_vm_backup.md)
* [Performing SQL Backup](performing_sql_backup.md)
* [Performing Spanner Backup](performing_spanner_backup.md)
* [Managing Backup Policies](managing_backup_policies.md)

Page updated 6/13/2025

Page content applies to build 7.0.0.47
