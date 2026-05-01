---
title: "Upgrading to Version 7 from Version 6"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/upgrade_vb_console.html"
last_updated: "4/29/2026"
product_version: "7.0.0.47"
---

# Upgrading to Version 7 from Version 6


When you perform upgrade to version 7 from Veeam Backup for Google Cloud version 6, Veeam Backup & Replication checks for available updates in the Veeam Update Repository and installs all necessary packages automatically.

Before you Begin

Before you upgrade Veeam Backup for Google Cloud, check the following prerequisites:

* Inbound internet access must be allowed for Veeam Backup & Replication server to the backup appliance through port 443.

* The service account whose access keys you plan to use when [deploying a backup appliance](deploy_appliance_account.md) or [connecting to the appliance](connect_appliance_account.md) must be assigned permissions required to perform upgrade. For the list of required permissions, see [Plug-in Permissions](plugin_permissions.md).

If the original appliance was connected to a Shared VPC network, both the service account whose access keys you plan to use and the Google APIs service account must have one of the following role combinations assigned to them:

* compute.networkUser role for the whole Shared VPC host project
* compute.networkViewer role for the whole host project and compute.networkUser for specific subnets in the host project.

* Outbound internet access must be allowed from the backup appliance to the PostgreSQL Apt Repository (apt.postgresql.org) through port 80 over the HTTP protocol.
* Outbound internet access must be allowed from the backup appliance to the PostgreSQL through port 443 over the HTTPS protocol to download the repository key <https://www.postgresql.org/media/keys/ACCC4CF8.asc>.
* Outbound internet access must be allowed from the backup appliance to the [Veeam Update Repository](https://repository.veeam.com/) through port 443 over the HTTPS protocol.

* Outbound internet access must be allowed from the backup appliance to the Ubuntu Security Repository (security.ubuntu.com) through port 80/443 over the HTTP/HTTPS protocol.

How to Perform Upgrade

To upgrade Veeam Backup for Google Cloud, do the following:

1. In the Veeam Backup & Replication console, open the Backup Infrastructure view.
2. Navigate to Managed Servers.
3. Select the necessary backup appliance and click Upgrade appliance on the ribbon.

Alternatively, right-click the appliance and select Upgrade.

[![Upgrade appliance](images/appliance_upgrade.webp)](images/appliance_upgrade.webp "Upgrade appliance")

Related Topics

[How Upgrade Works](vbgc_hiw_upgrade_6_old.md)


