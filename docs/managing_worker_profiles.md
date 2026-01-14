---
title: "managing_worker_profiles"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_worker_profiles.html"
last_updated: "8/12/2024"
product_version: "7.0.0.47"
---


In this article

A profile is the machine type of a worker instance that Veeam Backup for Google Cloud deploys in a specific Google Cloud region to perform a backup or archive operation. Veeam Backup for Google Cloud deploys one worker instance per each Google Cloud resource (whether it is a VM instance, a Cloud SQL instance or a Cloud Spanner instance) added to a backup policy. The profile of each deployed worker instance is selected based on the regional quota.

There are 3 types of worker profiles in Veeam Backup for Google Cloud:

* Primary — a profile that Veeam Backup for Google Cloud uses for creating image-level backups if the regional disk quota has not been reached yet.
* Secondary — a profile that Veeam Backup for Google Cloud uses for creating image-level backups if you have run or about to run out of the regional disk quota.
* Archiving — a profile that Veeam Backup for Google Cloud uses for creating archived backups.

Out of the box, Veeam Backup for Google Cloud comes with the default set of worker profiles where the primary profile is e2-highcpu-8, the secondary profile is e2-highcpu-2, and the archiving profile is e2-standard-4. However, to boost operational performance and to guarantee that you do not breach Google Cloud quota limits, you can add custom sets of worker profiles to specify machine types of VM instances that will operate as worker instances in different regions.

|  |
| --- |
| Important |
| Veeam Backup for Google Cloud does not allow you to change the default worker profiles that are used to deploy worker instances performing restore, file-level recovery, health check and retention operations — the default machine types of these instances are listed in section [Architecture Overview](overview_worker_instances.md#workers). To customize the default worker profiles, open a [support case](collecting_logs.md). |

In This Section

* [Adding Worker Profiles](creating_worker_profiles.md)
* [Editing Worker Profiles](editing_worker_profiles.md)
* [Removing Worker Profiles](removing_worker_profiles.md)

Page updated 8/12/2024

Page content applies to build 7.0.0.47
