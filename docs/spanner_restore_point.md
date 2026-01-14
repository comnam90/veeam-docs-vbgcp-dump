---
title: "spanner_restore_point"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/spanner_restore_point.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---


In this article

At the Instances step of the wizard, select a restore point that will be used to restore the selected Cloud Spanner instance. By default, Veeam Backup for Google Cloud uses the most recent valid restore point. However, you can restore the instance data to an earlier state.

To select a restore point, do the following:

1. Select the Cloud Spanner instance and click Restore Point.

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to restore a Cloud Spanner instance from a snapshot, the Veeam.VB.SpannerAccessBackup role must exist in the project to which the target instance belongs. |

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
* Project — a project that manages the protected Cloud Spanner instance.
* Retention — a retention configured for the backup policy that created the restore point.

[![Restoring Cloud SQL Instance](images/spanner_restore_point.webp)](images/spanner_restore_point.webp "Restoring Cloud SQL Instance")

Page updated 11/14/2025

Page content applies to build 7.0.0.47
