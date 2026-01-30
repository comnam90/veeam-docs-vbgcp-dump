---
title: "Considerations and Limitations"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/limitations.html"
last_updated: "12/8/2025"
product_version: "7.0.0.47"
---

# Considerations and Limitations


When you plan to deploy and configure Veeam Backup for Google Cloud, keep in mind the following limitations and considerations.

Licensing

If the license file is not installed, Veeam Backup for Google Cloud will operate in the Free edition allowing you to protect up to 10 instances free of charge.

Software

To access Veeam Backup for Google Cloud, use Microsoft Edge (latest version), Mozilla Firefox (latest version) or Google Chrome (latest version). Internet Explorer is not supported.

Security Certificates

Veeam Backup for Google Cloud supports certificates only in the PFX and P12 formats.

Backup Repositories

When managing backup repositories, consider the following:

* The Coldline storage class is not supported. For more information on storage classes offered by Cloud Storage, see [Google Cloud documentation](https://cloud.google.com/storage/docs/storage-classes).
* You cannot change Google Cloud storage buckets, subdirectories and storage classes for backup repositories already added to Veeam Backup for Google Cloud.
* Customer-supplied encryption keys (CSEKs) are not supported for repository encryption.
* After you create a repository with encryption enabled, you will not be able to disable encryption for this repository. However, you will still be able to change the encryption settings as described in section [Editing Backup Repositories](editing_repositories.md).
* A backup repository must not be managed by multiple backup appliances simultaneously. Retention sessions running on different appliances may corrupt backups stored in the repository, which may result in unpredictable data loss.

Worker Instances

When managing worker instances, consider the following:

* For Veeam Backup for Google Cloud to be able to deploy the number of worker instances required for a backup or restore process, you must have enough resource quotas allocated between your projects. To learn how to check your quotas, see [Google Cloud documentation](https://docs.cloud.google.com/compute/quotas-limits).
* To allow Veeam Backup for Google Cloud to connect a created worker instance to a Shared VPC network, the service account associated with the Google Cloud project to which the instance belongs must have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project.

To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject).

Backup

When protecting Google Cloud resources, consider the following:

* Veeam Backup for Google Cloud allows you to protect MySQL and PostgreSQL instances. SQL Server instances are not supported. For more information on types of Cloud SQL instances, see [Google Cloud documentation](https://cloud.google.com/sql/docs/features).
* To allow Veeam Backup for Google Cloud to back up a VM instance connected to a Shared VPC network, the service account associated with the project to which the instance belongs must have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project.

To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject).

* Veeam Backup for Google Cloud does not support backup of Google Cloud hyperdisks if they are shared across several VMs.

* Veeam Backup for Google Cloud does not support backup of the default PostgreSQL databases (template0, template1 and postgres).
* Veeam Backup for Google Cloud does not support backup of SQL instances of PostgreSQL version 18 or higher.
* When backing up Cloud Spanner instances, Veeam Backup for Google Cloud does not process their internal settings — except for the version\_retention\_period setting. For more information on internal settings of Cloud Spanner instances, see [Google Cloud documentation](https://cloud.google.com/spanner/docs/pitr).

* Veeam Backup for Google Cloud does not support backup of Cloud Spanner instances of the Enterprise and Enterprise Plus editions.

Restore

When restoring Google Cloud resources, consider the following:

* When restoring a VM instance, Veeam Backup for Google Cloud recovers data from all zonal and regional persistent disks (standard, balanced, extreme and SSD) attached to the instance. However, due to [technical reasons](https://cloud.google.com/compute/docs/disks/local-ssd#data_persistence), when it comes to local SSDs (SCSI and NVMe), Veeam Backup for Google Cloud is able to recover only the configuration of these disks, which means that any data stored on the disks is lost during the restore process.
* To allow Veeam Backup for Google Cloud to connect a restored VM instance to a Shared VPC network, the service account associated with the project to which the instance belongs must have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project.

To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject).

* Veeam Backup for Google Cloud does not support restore of Google Cloud hyperdisks if they are shared across several VMs.
* Due to [Google Cloud technical limitations](https://cloud.google.com/compute/docs/disks/local-ssd#data_persistence), Veeam Backup for Google Cloud does not support restore of local SSDs (SCSI and NVMe).
* Veeam Backup for Google Cloud supports file-level recovery for FAT, FAT32, NTFS, ext2, ext3, ext4, XFS and Btrfs file systems only. However, attributes of files and folders stored in FAT and FAT32 file systems cannot be restored to the original location.
* Veeam Backup for Google Cloud does not support restore of NTFS links (hard links, junction points, symbolic links) to the original location.
* Veeam Backup for Google Cloud does not support restore of files and folders stored on disks with Windows-native [Data Deduplication](https://learn.microsoft.com/en-us/windows-server/storage/data-deduplication/overview) enabled.

* Veeam Backup for Google Cloud does not support restore of SQL instances of PostgreSQL version 18 or higher.

* Due to [Google Cloud techical limitations](https://cloud.google.com/sql/docs/troubleshooting#managing-instances), Veeam Backup for Google Cloud does not support restore to the original location if the source Cloud SQL instance is still present in Google Cloud, if it has been recently deleted (less than a week ago), or if its name is reserved.
* Restore of PostgreSQL instances to Cloud SQL instances of the db-f1-micro and db-g1-small machine types is not supported. If you want to restore a PostgreSQL instance to one of the specified machine types, you must first manually create a Cloud SQL instance of the necessary type in the Google Cloud console as described in [Google Cloud documentation](https://cloud.google.com/sql/docs/postgres/create-instance), and then restore the backed-up databases to the created instance as described in section [Performing Database Restore](performing_database_restore_ui.md).

* Veeam Backup for Google Cloud does not support restore of the default PostgreSQL databases (template0, template1 and postgres).

* Veeam Backup for Google Cloud does not support restore of Cloud Spanner instances of the Enterprise and Enterprise Plus editions.

* Veeam Backup for Google Cloud does not support restore of encrypted files to their original locations.

* When restoring encrypted folders to the original locations, folder encryption attributes will not be restored.
* When restoring root folders to their original locations while the folders no longer exist in these locations, Veeam Backup for Google Cloud restores all the folder attributes in the Overwrite mode.

* Due to Google Cloud technical limitations, Veeam Backup for Google Cloud does not support data encryption of Cloud SQL instances with multi-regional keys. For more information, see [Cloud SQL for MySQL documentation](https://cloud.google.com/sql/docs/mysql/configure-cmek#key) and [Cloud SQL for PostgreSQL documentation](https://cloud.google.com/sql/docs/postgres/configure-cmek#key).
* Due to [Google Cloud technical limitations](https://cloud.google.com/sql/docs/troubleshooting#managing-instances), Veeam Backup for Google Cloud does not support database restore to the original location if the source database is still located on the server.
* When restoring Cloud SQL instances, Veeam Backup for Google Cloud turns off the point in time recovery setting, and it is turned on automatically only as soon as the restore process completes, which means that all the historical data is lost.


