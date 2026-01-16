---
title: "managing_sql_accounts"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_sql_accounts.html"
last_updated: "3/6/2024"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to authenticate against Cloud SQL instances protected by backup policies, you must specify credentials that will be used to access the instances.

Out of the box, Veeam Backup for Google Cloud comes with the default IAM account. Credentials of this account allow Veeam Backup for Google Cloud to automatically detect unique email addresses associated with service accounts that are used to access Cloud SQL instances added to backup policies. However, you can create additional Cloud SQL accounts to granularly define credentials that will be used to access specific Cloud SQL instances.

|  |
| --- |
| Important |
| To be able to use the default IAM credentials, you must configure Cloud SQL IAM database authentication for Cloud SQL instances in the Google Cloud console in advance, as described in [Google Cloud documentation](https://cloud.google.com/sql/docs/mysql/authentication). Note that Cloud IAM database authentication method is supported for MySQL instances only. |

In This Section

* [Adding Cloud SQL Accounts](add_sql_accounts.md)
* [Editing Cloud SQL Accounts](sql_account_edit.md)
* [Removing Cloud SQL Accounts](sql_account_remove.md)

Page updated 3/6/2024

Page content applies to build 7.0.0.47
