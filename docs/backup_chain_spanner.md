---
title: "Backup Chain"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_chain_spanner.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---

# Backup Chain


If you enable image-level backups for a backup policy, Veeam Backup for Google Cloud creates a new backup in a standard or nearline repository during every backup session. A sequence of backups created during a set of backup sessions makes up a regular backup chain.

Each Cloud Spanner backup in the backup chain contains metadata that stores information about the protected instance, the backup policy that created the backup, as well as the date, time and configured retention settings. Veeam Backup for Google Cloud uses metadata to identify outdated backups, to retrieve information on the source instance configuration during recovery operations and so on.

|  |
| --- |
| Note |
| The [forever forward incremental backup](backup_chain_vm.md) method is not implemented for Cloud Spanner instances — during every backup session Veeam Backup for Google Cloud creates a full backup in the regular backup chain. |

The period of time during which Cloud Spanner backups are kept in the backup chain is defined by retention policy settings. For details, see [Spanner Backup Retention](backup_retention_spanner.md).

Related Topics

* [Archive Backup Chain](archive_backup_chain_spanner.md)
* [Spanner Backup Retention](backup_retention_spanner.md)


