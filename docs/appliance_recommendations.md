---
title: "appliance_recommendations"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/appliance_recommendations.html"
last_updated: "12/4/2025"
product_version: "7.0.0.47"
---


In this article

You can choose the machine type of the VM instance running Veeam Backup for Google Cloud during the deployment, or later as the environment grows.

General Recommendations

The following recommendations and examples apply to the latest Veeam Backup for Google Cloud builds (7.0.0.47 or later).

By default, the backup appliance can process 25 workloads per policy and up to 15 sessions simultaneously, including running policies, restore, rescan and retention activities.

| Appliance Size\* | Recommended Maximum Number of Protected Workloads |
| --- | --- |
| e2-highmem-2 (2 vCPU, 8 GB RAM) | 100 |
| e2-standard-4 (4 vCPU, 16 GB RAM) | 200 |
| e2-standard-8 (8 vCPU, 32 GB RAM) | 2,500 |
| e2-standard-16 (16 vCPU, 64 GB RAM) | 5,000 |

\*It is recommended that you add 8 vCPU and 32 GB RAM per each additional 2,500 workloads.

Veeam Backup & Replication Integration

When you connect a backup appliance to the backup infrastructure, its policy and retention data is imported into the Veeam Backup & Replication database.

You can connect multiple backup appliances to a single Veeam Backup & Replication server. However, when working in a Google service account with cross-region data transfer, it is recommended that you use one Veeam Backup & Replication server per region, to help you avoid latency issues and meet potential data residency regulations.

Time Consumption

When you connect an existing backup appliance to the backup infrastructure, the integration process includes the following steps:

* Retrieving data from the appliance.
* Saving the retrieved data to the Veeam Backup & Replication database.

| Protected Workloads | Snapshots | Backups | Policy Sessions | Workload Processing Sessions | Time Consumption |
| --- | --- | --- | --- | --- | --- |
| 100 | 10,000 | 10,000 | 1 | 100 | 0:02:26 |
| 200 | 20,000 | 20,000 | 2 | 200 | 0:03:44 |
| 2,500 | 250,000 | 250,000 | 25 | 2,500 | 1:34:52 |
| 5,000 | 500,000 | 500,000 | 50 | 5,000 | 3:31:20 |

|  |
| --- |
| Note |
| The process of synchronizing data between the backup appliance and Veeam Backup & Replication database runs every 2 minutes after you add the appliance to the backup infrastructure. Creating new backup policies and updating policy settings may also trigger the synchronization process. |

Page updated 12/4/2025

Page content applies to build 7.0.0.47
