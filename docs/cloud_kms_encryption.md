---
title: "Cloud KMS Encryption"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/cloud_kms_encryption.html"
last_updated: "7/30/2024"
product_version: "7.0.0.47"
---

# Cloud KMS Encryption


Veeam Backup for Google Cloud allows you to back up and restore data of encrypted Cloud Spanner databases, Cloud SQL instances and VM instances whose persistent disks are encrypted with Google Cloud KMS. Additionally, you can choose to encrypt data with original CMEKs or change CMEKs used to encrypt data when performing the following operations:

* [Restoring entire VM instances to a new location](vm_restore_encryption.md)
* [Restoring persistent disks of VM instances to a new location](disk_restore_encryption.md)
* [Restoring entire Cloud SQL instances to a new location](sql_restore_encryption.md)
* [Restoring entire Cloud Spanner instances to a new location](spanner_restore_encryption.md)
* [Restoring specific Cloud Spanner databases to a new location](spanner_database_restore_instance.md)

Depending on the operation performed for an encrypted Cloud Spanner databases, Cloud SQL instance or a VM instance that has encrypted persistent disks, the service account that Veeam Backup for Google Cloud uses for the operation may require specific permissions to access Google Cloud KMS resources:

* [Creating cloud-native snapshots](#snapshots_create)
* [Creating image-level backups](#backups_create)
* [Restoring from cloud-native snapshots](#snapshots_restore)
* [Restoring from image-level backups](#backups_restore)

Creating Cloud-Native Snapshots

The process of creating cloud-native snapshots of an encrypted Cloud Spanner databases, Cloud SQL instance or a VM instance with encrypted persistent disks does not differ from the same process for an unencrypted Cloud Spanner instance, Cloud SQL instance or a VM instance with unencrypted persistent disks. The service account used to encrypt the created snapshots does not require any additional permissions — Veeam Backup for Google Cloud encrypts these snapshots with the same CMEKs with which the source Cloud SQL instance, databases of the source Cloud Spanner instance or persistent disks of the source VM instance are encrypted.

Creating Image-Level Backups

The process of creating image-level backups of a Cloud Spanner instance with encrypted databases, an encrypted Cloud SQL instance or a VM instance with encrypted persistent disks does not depend on the location where the worker instance processing the data is deployed. Regardless of whether the worker instance is deployed in the same Google Cloud project to which the source Cloud Spanner, Cloud SQL or VM instance belongs, Veeam Backup for Google Cloud performs the following steps:

* To back up a Cloud Spanner instance:

1. Takes a cloud-native snapshot of the Cloud Spanner instance.
2. Uses the worker instance to retrieve databases, views, tables and foreign keys of the processed Cloud Spanner instance, transfers the retrieved data to the target backup repository and stores the data in the native Veeam format.

The service account that is used to retrieve data from the Cloud Spanner instance requires permissions to access CMEKs with which the source Cloud Spanner database is encrypted.

1. Removes the worker instance from Google Cloud.

* To back up a Cloud SQL instance:

1. Takes a cloud-native snapshot of the Cloud SQL instance.

1. Uses the worker instance to export databases, triggers, stored procedures and users of the Cloud SQL instance to the target backup repository.

The service account that is used to retrieve the data requires permissions to access CMEKs with which the source Cloud SQL instance is encrypted.

1. Removes the worker instance from Google Cloud.

* To back up a VM instance:

1. Takes a cloud-native snapshot of the VM instance.
2. Creates persistent disks from the snapshot.

To encrypt the created disks, Veeam Backup for Google Cloud requires permissions of a service account that can access CMEKs with which you want to encrypt these disks.

1. Attaches the created persistent disks to the worker instance to read and further transfer the backed-up data to a backup repository.

1. Removes the worker instance from Google Cloud.

|  |
| --- |
| Note |
| Every time before creating persistent disks from a cloud-native snapshot, Veeam Backup for Google Cloud checks whether the total size of pd-standard disks breaches the zone quota for the project in which the worker instance is deployed. If the total disk size is less than 4000 GB, Veeam Backup for Google Cloud temporarily attaches an additional empty disk to the worker instance — but only for the duration of the backup process and if the quota allows attaching the disk. This allows Veeam Backup for Google Cloud to speed up the data transfer to reduce your backup costs. |

Restoring from Cloud-Native Snapshots

The process of restoring a Cloud Spanner, Cloud SQL or VM instance from an encrypted cloud-native snapshot does not differ depending on the location where the restored instance will reside. Regardless of whether the Cloud Spanner, Cloud SQL or VM instance will be restored to the same Google Cloud project to which the cloud-native snapshot belongs, Veeam Backup for Google Cloud performs the following steps:

* To restore a Cloud Spanner instance:

1. Creates a Cloud Spanner instance in the target location.

To encrypt the databases of the created instance, Veeam Backup for Google Cloud requires permissions of a service account that can access the CMEK with which you want to encrypt these databases.

1. Copies the snapshot of the source Cloud Spanner instance to the target Cloud Spanner instance, and then restores databases from the snapshot to the target instance.

* To restore a Cloud SQL instance:

1. Creates a Cloud SQL instance in the target location.

The service account that is used to create the instance requires permissions to access the CMEK with which you want to encrypt this instance.

1. Uses native Google Cloud capabilities to revert the created Cloud SQL instance to the snapshot.

* To restore a VM instance:

1. Creates persistent disks from the cloud-native snapshot.

To encrypt the created disks, Veeam Backup for Google Cloud requires permissions of a service account that can access the CMEK with which you want to encrypt these disks.

1. Creates a VM instance in the target location.
2. Attaches the created persistent disks with the restored data to the VM instance.

Restoring from Image-Level Backups

The process of restoring a Cloud Spanner instance with encrypted databases, an encrypted Cloud SQL instance or a VM instance with encrypted persistent disks from an image-level backup does not differ depending on the location where the worker instance processing the data is deployed. Regardless of whether the worker instance is deployed in the same Google Cloud project to which the restored Cloud Spanner, Cloud SQL or VM instance will belong, Veeam Backup for Google Cloud performs the following steps:

* To restore a Cloud Spanner instance:

1. Creates a Cloud Spanner instance in the target location.

To encrypt the databases of the created instance, Veeam Backup for Google Cloud requires permissions of a service account that can access the CMEK with which you want to encrypt these databases.

1. Uses the worker instance to transfer database schema, data and foreign keys of the backed-up Cloud Spanner instance to the target instance.
2. Removes the worker instance from Google Cloud.

* To restore a Cloud SQL instance:

1. Creates a Cloud SQL instance in the target location.

The service account that is used to create the instance requires permissions to access the CMEK with which you want to encrypt this instance.

1. Uses the worker instance to transfer databases, triggers, stored procedures and users of the backed-up Cloud SQL instance to the target instance.

1. Removes the worker instance from Google Cloud.

* To restore a VM instance:

1. Creates empty persistent disks and attaches the disks to the worker instance to restore the backed-up data to the target location.

To encrypt the created disks, Veeam Backup for Google Cloud requires permissions of a service account that can access the CMEK with which you want to encrypt these disks.

1. Takes cloud-native snapshots of the persistent disks with the restored data.
2. Creates a VM instance in the target location.
3. Creates persistent disks from the snapshots, and attaches the disks to the VM instance.

To encrypt the created disks, Veeam Backup for Google Cloud requires permissions of a service account that can access the CMEK with which you want to encrypt these disks.

1. Removes the worker instance from Google Cloud.


