---
title: "Step 2. Select Restore Point"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/sql_restore_point.html"
last_updated: "11/4/2025"
product_version: "7.0.0.47"
---

# Step 2. Select Restore Point


At the Instances step of the wizard, select a restore point that will be used to restore the selected Cloud SQL instance. By default, Veeam Backup for Google Cloud uses the most recent valid restore point. However, you can restore the instance data to an earlier state.

To select a restore point, do the following:

1. Select the Cloud SQL instance and click Restore Point.

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to restore a Cloud SQL instance from a snapshot, the Veeam.VB.SqlAccessBackup role must exist in the project where the target instance resides. |

1. In the Choose restore point window, select the necessary restore point and click Apply.

To help you choose a restore point, Veeam Backup for Google Cloud provides the following information on each available restore point:

* Creation Time — the date when the restore point was created.
* Destination — the type of the restore point:

* Snapshot — a cloud-native snapshot created by a backup policy.
* Manual Snapshot — a cloud-native snapshot created manually.
* Backup — an image-level backup created by a backup policy.
* Archive — an archived backup created by a backup policy.

* State — the result of the latest health check performed for the restore point.
* Storage Class — the storage class of a backup repository where the restore point is stored (applies only to image-level backups).
* Policy — a backup policy that created the restore point.
* Region — a region in which the protected Cloud SQL instance resides.
* Project — a project that manages the protected Cloud SQL instance.
* Retention — a retention configured for the backup policy that created the restore point.

[![Restoring Cloud SQL Instance](images/sql_restore_point.webp)](images/sql_restore_point.webp "Restoring Cloud SQL Instance")


