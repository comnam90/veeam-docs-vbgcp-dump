---
title: "Removing Worker Configurations"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/removing_worker_configurations.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---

# Removing Worker Configurations


Veeam Backup for Google Cloud allows you to permanently remove worker configurations if you no longer need them. When you remove a worker configuration, Veeam Backup for Google Cloud does not remove currently running worker instances that have been created based on this configuration — these instances are removed only when the related operations complete.

To remove a worker configuration from Veeam Backup for Google Cloud, do the following:

1. Switch to the Configuration page.
2. Navigate to Workers > Network.
3. Select the worker configuration and click Remove.

|  |
| --- |
| Note |
| If there are any worker instances created based on the selected configuration that are currently involved in a backup or restore process, these instances will be removed only when the process completes. |

[![Removing Worker Configurations](images/removing_workers.webp)](images/removing_workers.webp "Removing Worker Configurations")


