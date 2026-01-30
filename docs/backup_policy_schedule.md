---
title: "Step 6. Specify Policy Scheduling Options"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_policy_schedule.html"
last_updated: "3/4/2024"
product_version: "7.0.0.47"
---

# Step 6. Specify Policy Scheduling Options


At the Schedule step of the wizard, you can instruct Veeam Backup for Google Cloud to start the backup policy automatically according to a specific backup schedule. The backup schedule defines how often data of the VM instances added to the backup policy will be backed up.

To help you implement a comprehensive backup strategy, Veeam Backup for Google Cloud allows you to create schedules of the following types:

* [Daily](schedule_daily.md) — the backup policy will create restore points repeatedly throughout a day on specific days.
* [Weekly](schedule_weekly.md) — the backup policy will create restore points once a day on specific days.
* [Monthly](schedule_monthly.md) — the backup policy will create restore points once a month on a specific day.
* [Yearly](schedule_yearly.md) — the backup policy will create restore points once a year on a specific day.

Combining multiple schedule types together allows you to retain restore points for longer periods of time — for more information, see [Enabling Harmonized Scheduling](harmonized_scheduling.md). Combining multiple schedule types together also allows you to archive backups — for more information, see [Enabling Backup Archiving](backup_archiving.md).


