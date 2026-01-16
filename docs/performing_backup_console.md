---
title: "performing_backup_console"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_backup_console.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---


In this article

To produce cloud-native snapshots and image-level backups of VM, Cloud SQL and Cloud Spanner instances, Veeam Backup for Google Cloud runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where backups must be stored, when the backup process must start and so on.

One backup policy can be used to process multiple VM, Cloud SQL or Cloud Spanner instances within different regions, but you can back up each VM, Cloud SQL or Cloud Spanner instance with one backup policy at a time. If an instance is added to more than one backup policy, it will be processed only by a backup policy that has the highest priority. Other backup policies will skip this instance from processing. For information on how to set a priority for a backup policy, see [Settings Backup Policy Priority](backup_policy_priority.md).

After you install Veeam Plug-in for Google Cloud and add backup appliances to the backup infrastructure, you can manage backup policies directly from the Veeam Backup & Replication console.

In This Section

* [Creating Backup Policies](add_policy.md)
* [Editing Backup Policy Settings](editing_policies_settings.md)
* [Enabling and Disabling Backup Policies](disabling_and_enabling_policies.md)
* [Starting and Stopping Backup Policies](starting_and_stopping_policies.md)
* [Deleting Backup Policies](deleting_policies.md)
* [Creating Backup Copy Jobs](backup_copy.md)
* [Copying Backups to Tapes](copy_to_tape.md)

Page updated 6/13/2025

Page content applies to build 7.0.0.47
