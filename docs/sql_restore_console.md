---
title: "sql_restore_console"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/sql_restore_console.html"
last_updated: "11/22/2024"
product_version: "7.0.0.47"
---


In this article

Veeam Backup & Replication offers the following restore operations:

* [Instance restore](performing_sql_instance_restore_console.md) — start an entire Cloud SQL instance from a restore point.
* [Database restore](performing_database_restore_console.md) — restore specific databases of a Cloud SQL instance from an image-level backup.

You can restore Cloud SQL instance data to the most recent state or to any available restore point.

|  |
| --- |
| Note |
| You can use restore points stored in standard repositories to perform all the listed recovery operations, while restore points stored in archive repositories can only be used to perform restore of Cloud SQL instances to the original or to a new location. |

Considerations and Limitations

Before you start restoring Cloud SQL instance data, consider the following limitations:

* If you plan to restore a SQL instance that had the configuration of the SQL Server Enterprise Plus Edition when the restore point was created, and if this instance was protected by Veeam Backup for Google Cloud version 5 or earlier, you will be able to restore it only as a SQL Server Enterprise Edition instance — and only to a new location.
* If you plan to restore a SQL instance that had the configuration of the SQL Server Enterprise Edition when the restore point was created, you will be able to restore it only as a SQL Server Enterprise Edition instance — either to the original or to a new location.
* If you plan to restore a SQL instance that had the configuration of the SQL Server Enterprise Plus Edition when the restore point was created, you will be able to restore it only as a SQL Server Enterprise Plus Edition instance — either to the original or to a new location.

As a workaround, you can either restore the instance databases individually, or change the edition of the restored instance as described in [Google Cloud documentation](https://cloud.google.com/sql/docs/mysql/editions-intro#edition-migrate).

Page updated 11/22/2024

Page content applies to build 7.0.0.47
