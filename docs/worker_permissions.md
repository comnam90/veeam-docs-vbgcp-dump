---
title: "worker_permissions"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/worker_permissions.html"
last_updated: "8/23/2024"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to create a worker instance in a Google Cloud project and to access the instance when performing backup and restore operations, the service account associated with the project must have the following permissions:

VM Backup and Restore Permissions

|  |
| --- |
| compute.regions.list  compute.disks.list  compute.instances.get  compute.instances.list  compute.snapshots.get  compute.snapshots.list  compute.zones.get  compute.zones.list  compute.globalOperations.get  compute.zoneOperations.get  compute.regionOperations.get  resourcemanager.projects.get  compute.projects.get  compute.firewalls.list  compute.snapshots.getIamPolicy  compute.networks.list  compute.subnetworks.list  resourcemanager.projects.getIamPolicy  resourcemanager.projects.setIamPolicy \*  iam.serviceAccounts.actAs  compute.disks.create  compute.disks.createSnapshot  compute.disks.delete  compute.disks.setLabels  compute.instances.attachDisk  compute.instances.create  compute.instances.delete  compute.instances.detachDisk  compute.instances.setMetadata  compute.instances.setName  compute.instances.setServiceAccount  compute.instances.setLabels  compute.instances.setTags  compute.routes.list  compute.regions.get  compute.snapshots.create  compute.snapshots.setLabels  compute.snapshots.setIamPolicy  compute.snapshots.delete  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.list  pubsub.subscriptions.get  logging.sinks.get  logging.sinks.delete  logging.sinks.list  pubsub.topics.attachSubscription  pubsub.topics.detachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.list  pubsub.topics.get  pubsub.topics.publish  compute.machineTypes.get  compute.machineTypes.list  compute.subnetworks.get  compute.subnetworks.use  compute.subnetworks.useExternalIp  compute.disks.use  pubsub.subscriptions.setIamPolicy  pubsub.subscriptions.getIamPolicy  pubsub.topics.setIamPolicy  pubsub.topics.getIamPolicy  storage.objects.create  storage.objects.delete  storage.objects.list  storage.objects.get  storage.objects.update  storage.buckets.create  serviceusage.services.list |

|  |
| --- |
| Important |
| * To allow Veeam Backup for Google Cloud to perform restore to the original location while source VM instances still exist there, the deletion protection setting must be disabled for the source instance. * To allow Veeam Backup for Google Cloud to connect a created worker instance to a Shared VPC network, the service account associated with the Google Cloud project to which the instance belongs must also have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project. To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject). |

Cloud SQL Backup and Restore Permissions

|  |
| --- |
| compute.regions.list  compute.disks.list  compute.instances.get  compute.instances.list  compute.snapshots.get  compute.snapshots.list  compute.zones.get  compute.zones.list  compute.globalOperations.get  compute.zoneOperations.get  compute.regionOperations.get  resourcemanager.projects.get  compute.projects.get  compute.firewalls.list  compute.snapshots.getIamPolicy  compute.networks.list  compute.subnetworks.list  resourcemanager.projects.getIamPolicy  resourcemanager.projects.setIamPolicy \*  iam.serviceAccounts.actAs  compute.disks.create  compute.disks.createSnapshot  compute.disks.delete  compute.disks.setLabels  compute.instances.attachDisk  compute.instances.create  compute.instances.delete  compute.instances.detachDisk  compute.instances.setMetadata  compute.instances.setServiceAccount  compute.instances.setLabels  compute.instances.setTags  compute.routes.list  compute.regions.get  compute.snapshots.create  compute.snapshots.setLabels  compute.snapshots.setIamPolicy  compute.snapshots.delete  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.list  pubsub.subscriptions.get  logging.sinks.get  logging.sinks.delete  logging.sinks.list  pubsub.topics.attachSubscription  pubsub.topics.detachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.list  pubsub.topics.get  pubsub.topics.publish  compute.machineTypes.get  compute.machineTypes.list  compute.subnetworks.get  compute.subnetworks.use  compute.subnetworks.useExternalIp  compute.disks.use  serviceusage.services.list  cloudsql.databases.list  cloudsql.instances.create  cloudsql.instances.delete  cloudsql.instances.export  cloudsql.instances.get  cloudsql.instances.list  cloudsql.instances.listServerCas  cloudsql.users.create  cloudsql.users.list  cloudsql.users.update  compute.projects.get |

\* Veeam Backup for Google Cloud will use the resourcemanager.projects.setIamPolicy permission only to assign the cloudsql.instances.get and cloudsql.instances.restoreBackup permissions to service accounts while performing backup operations.

Cloud Spanner Backup and Restore Permissions

|  |
| --- |
| compute.regions.list  compute.disks.list  compute.instances.get  compute.instances.list  compute.snapshots.get  compute.snapshots.list  compute.zones.get  compute.zones.list  compute.globalOperations.get  compute.zoneOperations.get  compute.regionOperations.get  resourcemanager.projects.get  compute.projects.get  compute.firewalls.list  compute.snapshots.getIamPolicy  compute.networks.list  compute.subnetworks.list  resourcemanager.projects.getIamPolicy  iam.serviceAccounts.actAs  compute.disks.create  compute.disks.createSnapshot  compute.disks.delete  compute.disks.setLabels  compute.instances.attachDisk  compute.instances.create  compute.instances.delete  compute.instances.detachDisk  compute.instances.setMetadata  compute.instances.setServiceAccount  compute.instances.setLabels  compute.instances.setTags  compute.routes.list  compute.regions.get  compute.snapshots.create  compute.snapshots.setLabels  compute.snapshots.setIamPolicy  compute.snapshots.delete  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.list  pubsub.subscriptions.get  logging.sinks.get  logging.sinks.delete  logging.sinks.list  pubsub.topics.attachSubscription  pubsub.topics.detachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.list  pubsub.topics.get  pubsub.topics.publish  compute.machineTypes.get  compute.machineTypes.list  compute.subnetworks.get  compute.subnetworks.use  compute.subnetworks.useExternalIp  compute.disks.use  serviceusage.services.list |

Page updated 8/23/2024

Page content applies to build 7.0.0.47
