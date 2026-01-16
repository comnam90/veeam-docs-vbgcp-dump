---
title: "viewing_session_statistics"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/viewing_session_statistics.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

For each performed data protection or disaster recovery operation, Veeam Backup for Google Cloud starts a new session and stores its records in the configuration database.

Viewing Session Statistics Using Console

You can track real-time statistics of all running and completed operations on the Jobs, Last 24 hours and Running nodes. For more information, see the Veeam Backup & Replication User Guide, sections [Viewing Real-Time Statistics](https://helpcenter.veeam.com/docs/vbr/userguide/realtime_statistics.html?ver=13) and [Viewing Job Session Results](https://helpcenter.veeam.com/docs/vbr/userguide/session_results.html?ver=13).

Veeam Backup & Replication also allows you track statistics of most data recovery operations initiated from Veeam Backup for Google Cloud. To do that, do either of the following:

* In the Veeam Backup & Replication console, open the Home view and navigate to Last 24 hours. In the working area, double-click the necessary session.

Alternatively, select the session and click Statistics on the ribbon.

* In the Veeam Backup & Replication console, open the History view and navigate to Jobs or Restore. In the working area, double-click the necessary session.

Alternatively, select the session and click Statistics on the ribbon.

The opened window will display restore session details such as the name of the Google Cloud resource whose data is being processed, the account under which the session has started, the session status and duration, information on the restore point selected for the operation, and the list of tasks performed during the session.

[![View statistics](images/view_restore_statistics.webp)](images/view_restore_statistics.webp "View statistics")

Viewing Session Statistics Using Web UI

You can track real-time statistics of all running and completed operations on the Session Logs page. To view the full list of tasks executed during an operation, click the link in the Status column. To view the full list of Google Cloud resources processed during an operation, click the link in the Items column.

|  |
| --- |
| Tip |
| If you want to specify the time period during which Veeam Backup for Google Cloud will keep session records in the configuration database, follow the instructions provided in section [Configuring Global Retention Settings](configuring_global_retention_settings.md#sessions). |

[![Viewing Session Details](images/viewing_sessions.webp)](images/viewing_sessions.webp "Viewing Session Details")

Page updated 11/18/2025

Page content applies to build 7.0.0.47
