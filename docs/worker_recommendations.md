---
title: "worker_recommendations"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/worker_recommendations.html"
last_updated: "12/19/2025"
product_version: "7.0.0.47"
---


In this article

If you want initial full backups to be processed quickly, it is recommended that you use a larger worker profile, and then change it to a smaller profile for incremental backup. You can change worker profile settings on a regional basis, so make sure that the selected profile is appropriate to process the largest workload within the required time.

Each worker instance is deployed as an Ubuntu image and is removed once the task that it performs completes. Machine types of worker instances depend on the regional quota.

| Worker Profile | Default Machine Type | Usage | Backup Speed |
| --- | --- | --- | --- |
| Primary | e2-highcpu-8 | Processing resources while sufficient disk quota is available | Up to 420 MBps (NTFS disks up to 540 MBps) |
| Secondary | e2-highcpu-2 | Processing resources while running out of disk quota | Up to 210 MBps |
| Archiving | e2-standard-4 | Transferring data to archive repositories | Up to 370 MBps |

For details on Google Cloud pricing, see [Google Cloud documentation](https://cloud.google.com/compute/all-pricing).

VM Instance Backup

The default configuration (e2-highcpu-8) is universal and available in all Google Cloud regions. For this configuration, the backup speed is up to 420 MBps if the sum of the source disk sizes is less than 5 TB. For NTFS disks, the backup speed is up to 540 MBps. For better speed consistency and overall performance at the same price level, it is recommended that you use n2d-highcpu-8 as the primary worker profile. By changing the profile to e2-highcpu-16, it is possible to achieve the backup speed up to 800 MBps; however, this will require adjusting the performance disk size of worker instances by changing the value in the configuration file /opt/veeam/gcpbackup/ServiceSettings.json.

|  |
| --- |
| "Backup": { |

If the sum of source disk sizes is more than 10 TB, changing the primary worker profile to e2-highcpu-16 (n2d-highcpu-16) allows you to achieve the backup speed up to 800 MBps. However, this will increase the total monthly infrastructure costs.

VM Instance Archive

The default configuration (e2-standard-4) allows you to archive data up to 370 MBps. By changing the archiving worker profile to e2-standard-8, it is possible to achieve the archiving speed up to 420 MBps; however, this will increase the total monthly infrastructure costs.

VM Instance Restore

The default configuration (e2-highcpu-4) allows you to restore data up to 170 MBps. For better speed consistency and overall performance at the same price level, you can use n2d-highcpu-4 as the worker profile.

By default, a worker instance deployed for the entire VM instance restore operation will use an additional performance disk up to 1500 GB; the disk size can be changed in the configuration file /opt/veeam/gcpbackup/ServiceSettings.json to increase the restore speed. To restore VM instances with a size of 24 TB or more, you can change the worker profile to e2-highcpu-8.

|  |
| --- |
| "HardwareSettings": {   "Restore": "e2-highcpu-8" } |

To achieve a higher restore speed, you can change the worker profile to e2-highcpu-8 with the additional 2048 GB performance disk. However, this will increase the total monthly infrastructure costs.

|  |
| --- |
| "HardwareSettings": {   "Restore": "e2-highcpu-8" }, "Restore": {   "TotalHddDisksSize": 2048 } |

File-Level Recovery

To avoid prolonged execution time of file-level recovery operations, it is recommended that you change the worker profile to e2-highmem-4 if the processed VM instances have a lot of disks. The profile can be changed in the configuration file /opt/veeam/gcpbackup/ServiceSettings.json.

|  |
| --- |
| "HardwareSettings": {   "Flr": "e2-highmem-4" } |

|  |
| --- |
| Important |
| It is not recommended to manually change the default worker profile that is used to deploy worker instances performing restore or file-level recovery operations — to customize the profile, open a [support case](collecting_logs.md). |

Retention

By default, all retention processes run on the backup appliance. However, it is possible to execute these processes on a worker instance (except for the deletion of an entire backup chain). To do that, it is recommended that you change the backup retention threshold to 0 in the configuration file /opt/veeam/gcpbackup/ServiceSettings.json. You can also adjust the worker profile to fit the size of the largest processed source instance.

|  |
| --- |
| {   "BackupRetention": {     "CreateWorkerRestorePointsThresholdGb": 150   }   "HardwareSettings": {    "Retention": "e2-highcpu-8"   } } |

Worker Profile Recommendations for Retention

| Largest Source Instance | Worker Profile |
| --- | --- |
| Less than 8 TB | e2-highcpu-8 |
| Between 8 and 16 TB | e2-highcpu-16 |
| Larger than 16 TB | e2-highcpu-32 |

|  |
| --- |
| Important |
| It is not recommended to manually change the default worker profile that is used to deploy worker instances performing retention operations — to customize the profile, open a [support case](collecting_logs.md). |

Page updated 12/19/2025

Page content applies to build 7.0.0.47
