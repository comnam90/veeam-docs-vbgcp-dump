---
title: "Changing Time Zone"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/changing_time_zone.html"
last_updated: "11/12/2025"
product_version: "7.0.0.47"
---

# Changing Time Zone


Veeam Backup for Google Cloud runs daily reports and performs all data protection and disaster recovery operations according to the time zone set on the backup appliance.

|  |
| --- |
| Important |
| If Daylight Saving Time (DST) is used in the time zone set on the backup appliance, consider the following:   * When DST starts (clocks are set one hour forward), all policy sessions scheduled to launch at the skipped hour on this day do not run. * When DST ends (clocks are set one hour back), all policy sessions scheduled to launch at the duplicated hour on this day run only once. |

Since the backup appliance is deployed on a VM instance in Google Cloud, the time zone is set to Coordinated Universal Time (UTC) by default. However, you can change the time zone if required. For example, you may want the time on the backup appliance to match the time on the workstation from which you access Veeam Backup for Google Cloud.

To change the time zone set on the backup appliance:

1. Switch to the Configuration page.
2. Navigate to General > Time Zone.
3. Select the necessary time zone from the Time zone drop-down list.
4. Click Save.

|  |
| --- |
| Note |
| You cannot change the time zone if any data protection or disaster recovery session is currently running. Wait for all the running sessions to complete or [stop them manually](viewing_session_statistics.md) — and then try changing the time zone again. |

[![Changing Time Zone](images/time_settings.webp)](images/time_settings.webp "Changing Time Zone")


