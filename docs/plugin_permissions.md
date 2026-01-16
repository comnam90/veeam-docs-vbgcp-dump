---
title: "plugin_permissions"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/plugin_permissions.html"
last_updated: "11/19/2025"
product_version: "7.0.0.47"
---


In this article

To perform backup and restore operations, accounts that Veeam Plug-in for Google Cloud uses to perform data protection and disaster recovery operations must be granted the following permissions.

Veeam Backup & Replication User Account Permissions

A user account that you use when installing and working with Veeam Backup & Replication must have the permissions listed in the Veeam Backup & Replication User Guide, section [Installing and Using Veeam Backup & Replication](https://helpcenter.veeam.com/docs/vbr/userguide/required_permissions.html?ver=13#installing-and-using-veeam-backup---replication).

Veeam Backup for Google Cloud User Account Permissions

A user account that Veeam Backup & Replication uses to authenticate against a backup appliance and get access to the appliance functionality must be assigned the Portal Administrator role. For more information on user roles, see [Managing User Accounts](managing_permissions.md).

|  |
| --- |
| Note |
| When you deploy a backup appliance from the Veeam Backup & Replication console, Veeam Backup & Replication automatically creates the necessary user account that is assigned all the required permissions. |

Google Cloud Service Account Permissions

Veeam Plug-in for Google Cloud requires the following service accounts:

* A service account whose permissions are used to create, connect and manage backup appliances. You can create this account manually in Google Cloud or instruct Veeam Backup & Replication to create the account automatically.

If you instruct Veeam Backup & Replication to create the service account automatically, the account is assigned the Owner role with a wide scope of permissions and capabilities. If you create a new service account in Google Cloud manually, consider that the service account must have the following minimal set of permissions:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)List of permissions

|  |  |
| --- | --- |
| |  | | --- | | {  compute.addresses.create  compute.addresses.delete  compute.addresses.get  compute.addresses.list  compute.addresses.setLabels  compute.addresses.use  compute.disks.create  compute.disks.createSnapshot  compute.disks.delete  compute.disks.get  compute.disks.setLabels  compute.disks.use  compute.firewalls.create  compute.firewalls.delete  compute.firewalls.get  compute.firewalls.list  compute.globalOperations.get  compute.instances.attachDisk  compute.instances.create  compute.instances.delete  compute.instances.detachDisk  compute.instances.get  compute.instances.getGuestAttributes  compute.instances.list  compute.instances.setLabels  compute.instances.setMetadata  compute.instances.setServiceAccount  compute.instances.setTags  compute.instances.start  compute.instances.stop  compute.machineTypes.list  compute.networks.create  compute.networks.delete  compute.networks.get  compute.networks.list  compute.networks.updatePolicy  compute.projects.get  compute.regions.get  compute.regions.list  compute.snapshots.create  compute.snapshots.delete  compute.snapshots.get  compute.snapshots.list  compute.snapshots.useReadOnly  compute.subnetworks.create  compute.subnetworks.delete  compute.subnetworks.get  compute.subnetworks.list  compute.subnetworks.use  compute.subnetworks.useExternalIp  compute.zoneOperations.get  compute.zoneOperations.list  compute.zones.get  compute.zones.list  config.deployments.create  config.deployments.delete  config.deployments.get  config.deployments.getLock  config.deployments.getState  config.deployments.list  config.deployments.lock  config.deployments.update  config.deployments.updateState  config.operations.get  config.resources.list  config.revisions.list  iam.roles.create  iam.roles.get  iam.roles.update  iam.serviceAccounts.actAs  iam.serviceAccounts.create  iam.serviceAccounts.delete  iam.serviceAccounts.get  iap.tunnelInstances.accessViaIAP  logging.logEntries.create  logging.logEntries.route  resourcemanager.projects.getIamPolicy  resourcemanager.projects.setIamPolicy  serviceusage.services.get  storage.buckets.create  storage.buckets.delete  storage.buckets.get  storage.buckets.getIamPolicy  storage.buckets.list  storage.buckets.setIamPolicy  storage.objects.create  storage.objects.delete  storage.objects.get  storage.objects.list  } | |

After you create a service account in Google Cloud, you must add it to Veeam Backup & Replication as described in the Veeam Backup & Replication User Guide, section [Google Cloud Platform Service Account](https://helpcenter.veeam.com/docs/vbr/userguide/cloud_credentials_gcp.html?ver=13).

* A service account whose permissions are used to perform data protection and disaster recovery operations with Google Cloud resources.

* When you deploy a new backup appliance, the default service account is automatically created on this appliance and is assigned all the required permissions.
* When you connect to an existing backup appliance, Veeam Plug-in for Google Cloud uses a service account with a set of predefined permissions that has already been created on this appliance.

Virtualization Servers and Hosts Service Account Permissions

If you plan to copy backups to on-premises repositories, to perform restore to VMware vSphere and Microsoft Hyper-V environments, or to perform other tasks related to virtualization servers and hosts, you must check whether the service account specified for these servers and hosts has the required permissions described in the Veeam Backup & Replication User Guide, section [Using Virtualization Servers and Hosts](https://helpcenter.veeam.com/docs/vbr/userguide/required_permissions.html?ver=13#using-virtualization-servers-and-hosts).

Microsoft Azure Account Permissions

An Azure AD application that you plan to use to restore VM instances to Microsoft Azure must have permissions described in the Veeam Backup & Replication User Guide, section [Permissions](https://helpcenter.veeam.com/docs/vbr/userguide/required_permissions.html?ver=13).

AWS IAM User Permissions

An IAM user whose one-time access keys you plan to use to perform restore of VM instances to Amazon EC2 must have permissions described in the Veeam Backup & Replication User Guide, section [AWS IAM User Permissions](https://helpcenter.veeam.com/docs/vbr/userguide/restore_amazon_permissions.html?ver=13).

Page updated 11/19/2025

Page content applies to build 7.0.0.47
