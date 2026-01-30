---
title: "Step 2. Select Restore Point"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_sql_instance_restore_point.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---

# Step 2. Select Restore Point


At the SQL instance step of the wizard, choose a restore point that will be used to restore the selected Cloud SQL instance. By default, Veeam Backup & Replication uses the most recent valid restore points. However, you can restore the instance data to an earlier state.

To select a restore point, do the following:

1. In the Select SQL instance list, select the Cloud SQL instance and click Point.

1. In the Restore Points window, expand the backup policy that protects the Cloud SQL instance, select the necessary restore point and click OK.

To help you choose a restore point, Veeam Backup & Replication provides the following information on each available restore point:

* Job — the name of the backup policy that created the restore point and the date when the restore point was created.
* Type — the type of the restore point.
* Location — the region or repository where the restore point is stored.

|  |
| --- |
| Tip |
| You can use the wizard to restore multiple instances at a time. To do that, click Add, select more Cloud SQL instances to restore and select a restore point for each of them. |

![Step 2. Select Restore Point](images/restore_sql_instance.webp)


