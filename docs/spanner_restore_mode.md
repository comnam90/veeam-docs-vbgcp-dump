---
title: "spanner_restore_mode"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/spanner_restore_mode.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---


In this article

At the Restore Mode step of the wizard, choose whether you want to restore the selected Cloud Spanner instance to the original or to a new location.

|  |
| --- |
| Important |
| Restore to the original location is supported only using restore points of the Backup and Archive types. If you select a restore point of the Snapshot or Manual Snapshot type at [step 2](spanner_restore_point.md) of the wizard, you will be able to select the Restore to original option and proceed with the wizard but only up to the Verification step — at this step, the verification check will notify you that the restore settings have not been configured properly. As a result, Veeam Backup for Google Cloud will not be able to perform the operation. |

[![Restoring Cloud SQL Instance](images/spanner_restore_mode.webp)](images/spanner_restore_mode.webp "Restoring Cloud SQL Instance")

Page updated 11/14/2025

Page content applies to build 7.0.0.47
