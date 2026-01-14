---
title: "backup_policy_priority"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_policy_priority.html"
last_updated: "11/21/2025"
product_version: "7.0.0.47"
---


In this article

By default, Veeam Backup for Google Cloud runs backup policies in the order you create them. However, you can set the backup policy priority manually:

1. Navigate to Policies.
2. Switch to the necessary tab and click Priority.
3. In the Priority Order window, do the following:

1. Select a backup policy in the list of existing policies.
2. To move the policy up or down the list, use the Up and Down arrows.
3. To save changes made to the priority order, click Apply.

|  |
| --- |
| Note |
| If an instance is included into multiple backup policies, it will be processed only by the backup policy that has the highest priority. |

[![Changing Backup Policy Priority](images/policy_priority.webp)](images/policy_priority.webp "Changing Backup Policy Priority")

Page updated 11/21/2025

Page content applies to build 7.0.0.47
