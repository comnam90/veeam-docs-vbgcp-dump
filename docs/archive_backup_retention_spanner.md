---
title: "Retention Policy for Archived Backups"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/archive_backup_retention_spanner.html"
last_updated: "2/12/2024"
product_version: "7.0.0.47"
---

# Retention Policy for Archived Backups


For archived backups, Veeam Backup for Google Cloud retains restore points for the number of days defined in backup scheduling settings as described in section [Creating Spanner Policies](spanner_policy_schedule.md).

To track and remove outdated restore points from an archive backup chain, Veeam Backup for Google Cloud performs the following actions once a day:

1. Veeam Backup for Google Cloud checks the configuration database to detect archive backup repositories that contain outdated restore points.
2. If an outdated restore point exists in a backup repository, Veeam Backup for Google Cloud transforms the archive backup chain in the following way:

1. Rebuilds the full archive backup to include there data of the incremental archive backup that follows the full archive backup. To do that, Veeam Backup for Google Cloud injects into the full archive backup data blocks from the earliest incremental archive backup in the chain. This way, the full archive backup ‘moves’ forward in the archive backup chain.

![Retention Policy for Archived Backups](images/backup_retention_injecting_blocks_archive.webp)

1. Removes the earliest incremental archive backup from the chain as redundant — this data has already been injected into the full archive backup.

![Retention Policy for Archived Backups](images/backup_retention_removing_data_archive.webp)

1. Veeam Backup for Google Cloud repeats step 2 for all other outdated restore points found in the archive backup chain until all the restore points are removed. As data from multiple restore points is injected into the rebuilt full archive backup, Veeam Backup for Google Cloud ensures that the archive backup chain is not broken and that you will be able to recover your data when needed.

![Retention Policy for Archived Backups](images/backup_retention_multiple_points_archive.webp)

1. Removes the worker instance when the retention session completes.

Related Topics

[Enabling Backup Archiving](spanner_backup_archiving.md)


