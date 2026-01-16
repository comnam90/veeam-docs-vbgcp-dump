---
title: "overview_worker_instances"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/overview_worker_instances.html"
last_updated: "12/4/2025"
product_version: "7.0.0.47"
---


In this article

A worker instance is an auxiliary Linux-based VM instance that is responsible for the interaction between the backup appliance and other components of the Veeam Backup for Google Cloud architecture. Worker instances process backup workload and distribute backup traffic when transferring data to and from backup repositories.

Worker Instance Components

A worker instance uses the following components:

* Veeam Data Mover — a service that performs data processing tasks. During backup, Veeam Data Mover retrieves data from snapshots and stores the retrieved data to backup repositories. During restore, Veeam Data Mover transfers backed-up data from backup repositories to the target location.

* File-level recovery browser — a web service that allows you to find and save files and folders of a backed-up VM instance to a local machine or to the original location. The file-level recovery browser is installed automatically on every worker instance that is deployed for file-level recovery.

For more information on recovering files of VM instances with the file-level recovery browser, see [Performing File-Level Recovery](performing_flr.md).

Security Certificates for Worker Instances

During the file-level recovery process, Veeam Backup for Google Cloud uses self-signed TLS certificates to establish secure communication between the web browser on a user workstation and the file-level recovery browser running on a worker instance. A self-signed certificate is generated automatically on the worker instance when the recovery session starts.

How Worker Instances Work

Veeam Backup for Google Cloud automatically deploys a worker instance in Google Cloud for the duration of a backup or restore process, and removes it immediately as soon as the process is over. To minimize cross-region traffic charges and to speed up the data transfer, depending on the performed operation, Veeam Backup for Google Cloud deploys the worker instance in the following location:

| Operation | Worker Instance Location | Default Worker Machine Types |
| --- | --- | --- |
| Creating image-level backups of VM instances | Google Cloud region in which a processed VM instance resides | e2-highcpu-8, with an additional empty standard persistent (pd-standard) disk up to 4000 GB in size |
| Creating image-level backups of Cloud SQL instances | Google Cloud region in which a processed Cloud SQL instance resides | e2-highcpu-8 |
| Creating image-level backups of Cloud SQL instances using a staging server | Google Cloud region in which a source Cloud SQL instance resides | e2-highcpu-8 |
| Creating image-level backups of Cloud Spanner instances | Either the Google Cloud region in which a target backup repository resides, or the region in which read-write and read-only replicas are located, or any other region defined by the Google Cloud logic | e2-highcpu-8 |
| Creating archived image-level backups of VM instances | Google Cloud region in which a target backup repository of the Standard or Nearline storage class resides. | e2-standard-4 |
| Creating archived image-level backups of Cloud SQL instances | Google Cloud region in which a target backup repository of the Standard or Nearline storage class resides | e2-standard-4 |
| Creating archived image-level backups of Cloud Spanner instances | Google Cloud region in which a target backup repository of the Standard or Nearline storage class resides | e2-standard-4 |
| Performing health check for created restore points | Google Cloud region in which a target backup repository of the Standard or Nearline storage class resides | e2-standard-4 |
| Applying retention policy settings to created restore points | Google Cloud region in which a backup repository with backed-up data resides | e2-highcpu-8 |
| Restoring VM instances | Google Cloud region to which a VM instance is restored | e2-highcpu-4, with an additional empty standard persistent (pd-standard) disk up to 1500 GB in size |
| Restoring Cloud SQL instances | Google Cloud region in which a backup repository with backed-up data resides (for MySQL instances); Google Cloud region in which the restored Cloud SQL instance will reside (for PostgreSQL instances) | e2-highcpu-8 |
| Restoring Cloud Spanner instances | Either the Google Cloud region to which a Cloud Spanner instance is restored, or the region in which read-write replicas are located | e2-highcpu-8 |
| Restoring individual persistent disks of VM instances | Google Cloud region to which the persistent disks of a processed VM instance are restored | e2-highcpu-4, with an additional empty standard persistent (pd-standard) disk up to 1500 GB in size |
| Restoring specific Cloud SQL databases | Google Cloud region in which a backup repository with backed-up data resides (for MySQL databases); Google Cloud region in which the target Cloud SQL instance resides (for PostgreSQL databases) | e2-highcpu-8 |
| Restoring specific Cloud Spanner databases | Either the Google Cloud region to which the databases of a processed Cloud Spanner instance are restored, or the region in which read-write replicas are located | e2-highcpu-8 |
| File-level recovery from cloud-native snapshots | Google Cloud region in which a source VM instance resides | e2-highcpu-4 |
| File-level recovery from image-level backups | Google Cloud region in which a backup repository with backed-up data resides | e2-highcpu-4 |

Worker instances are deployed based on worker configurations and profiles. For more information, see [Managing Worker Instances](managing_workers.md).

|  |
| --- |
| Important |
| For Veeam Backup for Google Cloud to deploy the number of worker instances required for a backup or restore process, you must have enough resource quotas allocated between your projects. To learn how to check your quotas, see [Google Cloud documentation](https://docs.cloud.google.com/compute/quotas-limits). |

For the list of network ports that must be open to ensure proper communication of worker instances with other components of the Veeam Backup for Google Cloud architecture, see [Ports](ports.md).

Page updated 12/4/2025

Page content applies to build 7.0.0.47
