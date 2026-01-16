---
title: "vbgc_update_from_v5"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/vbgc_update_from_v5.html"
last_updated: "12/9/2025"
product_version: "7.0.0.47"
---


In this article

When you perform upgrade to version 7 from Veeam Backup for Google Cloud version 5.0, the backup appliance operating system is upgraded from Ubuntu 20.04 LTS to Ubuntu 22.04 LTS, and the configuration database is upgraded to PostgreSQL 16. During upgrade, the original root disk of the backup appliance will be replaced with a new one.

|  |
| --- |
| Important |
| Consider that if the [OS Login service](https://docs.cloud.google.com/compute/docs/oslogin) is used as the access management method on your project, Veeam Backup & Replication will not be able to use SSH to connect to the backup appliance, and the deployment operation will fail. |

To upgrade Veeam Backup for Google Cloud, check the following prerequisites — and then install version 7 as described in section [Updating Appliances Using Console](appliance_upgrade_console.md):

* Infrastructure Manager must be enabled for the Google Cloud project to which the backup appliance belongs. Otherwise, upgrade operation may fail or cause unexpected errors.
* Veeam Backup for Google Cloud version must be compatible with the current version of Veeam Plug-in for Google Cloud. For more information, see [System Requirements](system_requirements.md).
* Inbound internet access must be allowed from the Google IAP to the backup appliance through port 22 through the SSH protocol (IP range 35.235.240.0/20).
* Inbound internet access must be allowed for Veeam Backup & Replication server to the backup appliance through port 443.
* The service account whose access keys you plan to use when [deploying a backup appliance](deploy_appliance_account.md) or [connecting to the appliance](connect_appliance_account.md) must be assigned permissions required to perform upgrade. For the list of required permissions, see [Plug-in Permissions](plugin_permissions.md).

If the original appliance was connected to a Shared VPC network, both the service account whose access keys you plan to use and the Google APIs service account must have one of the following role combinations assigned to them:

* compute.networkUser role for the whole Shared VPC host project
* compute.networkViewer role for the whole host project and compute.networkUser for specific subnets in the host project.

* Outbound internet access must be allowed from the backup appliance to the PostgreSQL Apt Repository (apt.postgresql.org, apt-archive.postgresql.org) through port 80 over the HTTP protocol.
* Outbound internet access must be allowed from the backup appliance to the PostgreSQL through port 443 over the HTTPS protocol to download the repository key <https://www.postgresql.org/media/keys/ACCC4CF8.asc>.
* Outbound internet access must be allowed from the backup appliance to the [Veeam Update Repository](https://repository.veeam.com/) through port 443 over the HTTPS protocol.
* Outbound internet access must be allowed from the backup appliance to the Ubuntu Security Repository (security.ubuntu.com) through port 80/443 over the HTTP/HTTPS protocol.
* During upgrade, Veeam Backup & Replication will create a temporary VM instance that will be connected to the same network and will have the same IP configuration as the original appliance. If the original appliance had a public IP address, no additional configuration is required. If the original appliance had a private IP address, the temporary VM will not be able to access Google Cloud Storage services directly — and you will have to work around the issue, for example, by enabling [Private Google Access](https://docs.cloud.google.com/vpc/docs/private-google-access).
* During upgrade, the data disk of the backup appliance will temporarily contain files of 2 databases. That is why the size of the data disk must be twice the total amount of storage space used by the configuration database.
* During upgrade, Veeam Backup & Replication will create a new root disk with default settings. That is why if you have previously modified the root disk settings, for example, if you have increased the volume size or enabled volume encryption, these settings will not be transferred, and custom 3rd-party software installed on the backup appliance will not be migrated.
* During upgrade, Veeam Backup & Replication will overwrite custom settings of the /etc/fstab configuration file on the backup appliance with the default settings. That is why if you have previously attached an additional disk to the backup appliance, you must re-mount the disk by adding its label or UUID to the /etc/fstab file.

How Upgrade Works

During the upgrade process, Veeam Backup & Replication performs the following steps:

1. Instructs Veeam Backup for Google Cloud to create a cloud-native snapshot of the original appliance. If the upgrade process fails, the appliance will be reverted to the created snapshot.

This snapshot will be automatically removed by Veeam Backup & Replication from Google Cloud after the upgrade operation completes successfully.

1. Stops all running backup and restore sessions on the original backup appliance.
2. Upgrades the appliance configuration database to PostgreSQL 16.
3. Saves the following configuration files and settings to the data disk: the appliance configuration file (/etc/veeam/gcpbackup/veeam-gcp-backup.conf), nginx configuration files (/etc/nginx/nginx.conf, /etc/nginx/proxy\_params), users, MFA and time zone settings, and Linux environment (/etc/ssh/, /root/, /home/).
4. Deploys a temporary VM instance from the Ubuntu 22.04 LTS image.
5. Installs a version 7 of the backup appliance to the temporary VM.
6. Detaches the boot disk from the newly created VM instance.
7. Detaches the outdated boot disk and attaches the new boot disk to the original appliance.
8. Removes the outdated boot disk from Google Cloud.
9. Restores the configuration files and settings saved at step 4 to the new boot disk.
10. Removes the temporary VM instance.

Page updated 12/9/2025

Page content applies to build 7.0.0.47
