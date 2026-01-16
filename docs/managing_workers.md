---
title: "managing_workers"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_workers.html"
last_updated: "11/8/2024"
product_version: "7.0.0.47"
---


In this article

To perform most data protection and disaster recovery operations (such as creating image-level backups in backup repositories and restoring backed-up data), Veeam Backup for Google Cloud uses worker instances. Worker instances are temporary Linux-based VM instances that are responsible for the interaction between the backup appliance and other Veeam Backup for Google Cloud components. Worker instances process backup workload and distribute backup traffic when transferring data to backup repositories.

Each worker instance is deployed in a specific Google Cloud region for the duration of the backup or restore process. For more information on regions in which Veeam Backup for Google Cloud deploys worker instances, see [Architecture Overview](overview_worker_instances.md#workers).

|  |
| --- |
| Note |
| You can tell worker instances from other VM instances running in your environment by their names — the names of all worker instances deployed by Veeam Backup for Google Cloud will contain the word worker, a GUID and the name of the processed resource, and will be assigned the label veeamvbid. |

In This Section

* [Managing Worker Configurations](managing_worker_configurations.md)
* [Managing Worker Profiles](managing_worker_profiles.md)
* [Assigning Worker Instance Labels](worker_profile_labels.md)

Page updated 11/8/2024

Page content applies to build 7.0.0.47
