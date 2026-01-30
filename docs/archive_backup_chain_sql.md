---
title: "Archive Backup Chain"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/archive_backup_chain_sql.html"
last_updated: "2/2/2024"
product_version: "7.0.0.47"
---

# Archive Backup Chain


If you enable backup archiving for a backup policy, Veeam Backup for Google Cloud creates a new backup in an archive repository during every archive session. A sequence of backups created during a set of archive sessions makes up an archive backup chain.

The archive backup chain includes backups of the following types:

* Full — a full archive backup stores a copy of the full instance image.
* Incremental — incremental archive backups store incremental changes of the instance image.

To create an archive backup chain for an Cloud SQL instance protected by a backup policy, Veeam Backup for Google Cloud implements the forever forward incremental backup method:

1. During the first archive session, Veeam Backup for Google Cloud detects backed-up data that is stored in the full backup and all incremental backups existing in the [regular backup chain](backup_chain_sql.md), creates a full archive backup with all the data, and copies this backup to the archive repository. The full archive backup becomes a starting point in the archive chain.
2. During subsequent archive sessions, Veeam Backup for Google Cloud checks the regular backup chain to detect data blocks that have changed since the previous archive session, creates incremental archive backups with only those changed blocks, and copies these backups to the archive repository. The content of each incremental archive backup depends on the content of the full archive backup and the preceding incremental archive backups in the archive backup chain.

Veeam Backup for Google Cloud creates incremental backups based on the Veeam proprietary filtering mechanism that filters out unchanged data blocks by calculating a checksum for every block. The Google Cloud changed block tracking (CBT) mechanism that would allow tracking changed blocks of data and would increase the efficiency of incremental backups is not implemented at the moment.

![Archive Backup Chain](images/archive_chain.webp)

Full and incremental archive backups act as restore points for backed-up instances that let you roll back instance data to the necessary state. To recover an instance to a specific point in time, the chain of backups created for the instance must contain a full archive backup and a set of incremental archive backups.

If some backup in the archive backup chain is missing, you will not be able to roll back to the necessary state. For this reason, you must not delete individual backups from the archive repository manually. Instead, you must specify retention policy settings that will let you maintain the necessary number of backups in the archive repository. For more information, see [Retention Policy for Archived Backups](archive_backup_retention_sql.md).

Related Topics

[Enabling Backup Archiving](sql_backup_archiving.md)


