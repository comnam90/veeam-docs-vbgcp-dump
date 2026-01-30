---
title: "Upgrading to Version 7 from Version 6"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/upgrade_vb_console.html"
last_updated: "12/8/2025"
product_version: "7.0.0.47"
---

# Upgrading to Version 7 from Version 6


When you perform upgrade to version 7 from Veeam Backup for Google Cloud version 6, no major operating system or configuration database updates take place. To upgrade Veeam Backup for Google Cloud to version 7, check the [prerequisites](#Prerequisites) and follow the instructions provided in section [Updating Appliances Using Console](appliance_upgrade_console.md).

How Upgrade Works

During the upgrade process, Veeam Backup & Replication performs the following steps:

1. Instructs Veeam Backup for Google Cloud to create a cloud-native snapshot of the original appliance. If the upgrade process fails, the appliance will be reverted to the created snapshot.

This snapshot will be automatically removed by Veeam Backup & Replication from Google Cloud after the upgrade operation completes successfully.

1. Stops all running backup and restore sessions on the original backup appliance.
2. Checks for updates using the Veeam Updater service and installs them on the backup appliance
3. Initializes the backup appliance services.
4. Removes the temporary cloud-native snapshot.

Limitations and Prerequisites

Before you start the upgrade process, consider the following requirements and limitations:

* Inbound internet access must be allowed for Veeam Backup & Replication server to the backup appliance through port 443.

* The service account whose access keys you plan to use when [deploying a backup appliance](deploy_appliance_account.md) or [connecting to the appliance](connect_appliance_account.md) must be assigned permissions required to perform upgrade. For the list of required permissions, see [Plug-in Permissions](plugin_permissions.md).

If the original appliance was connected to a Shared VPC network, both the service account whose access keys you plan to use and the Google APIs service account must have one of the following role combinations assigned to them:

* compute.networkUser role for the whole Shared VPC host project
* compute.networkViewer role for the whole host project and compute.networkUser for specific subnets in the host project.

* Outbound internet access must be allowed from the backup appliance to the PostgreSQL Apt Repository (apt.postgresql.org) through port 80 over the HTTP protocol.
* Outbound internet access must be allowed from the backup appliance to the PostgreSQL through port 443 over the HTTPS protocol to download the repository key <https://www.postgresql.org/media/keys/ACCC4CF8.asc>.
* Outbound internet access must be allowed from the backup appliance to the [Veeam Update Repository](https://repository.veeam.com/) through port 443 over the HTTPS protocol.

* Outbound internet access must be allowed from the backup appliance to the Ubuntu Security Repository (security.ubuntu.com) through port 80/443 over the HTTP/HTTPS protocol.


