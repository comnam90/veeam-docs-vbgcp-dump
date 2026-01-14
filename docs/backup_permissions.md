---
title: "backup_permissions"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_permissions.html"
last_updated: "1/26/2024"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to perform backup operations, the service account associated with the Google Cloud project managing instances that you want to protect must have the following permissions.

VM Backup Permissions

|  |
| --- |
| compute.addresses.list  compute.regions.list  compute.disks.list  compute.disks.createSnapshot  compute.disks.get  compute.instances.get  compute.instances.list  compute.snapshots.create  compute.snapshots.delete  compute.snapshots.get  compute.snapshots.list  compute.snapshots.getIamPolicy  compute.snapshots.setIamPolicy  compute.snapshots.setLabels  compute.subnetworks.list  compute.routes.list  compute.machineTypes.get  compute.zones.list  compute.globalOperations.list  compute.globalOperations.get  compute.zoneOperations.get  compute.regionOperations.get  compute.projects.get  compute.regions.get  compute.networks.list  compute.firewalls.list  resourcemanager.projects.get  resourcemanager.projects.getIamPolicy  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  logging.sinks.update  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.subscriptions.consume  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy  pubsub.topics.update  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  cloudkms.cryptoKeys.setIamPolicy  cloudkms.cryptoKeys.getIamPolicy  serviceusage.services.list |

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to back up a VM instance connected to a Shared VPC network, the service account associated with the project to which the instance belongs must also have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project.  To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject). |

Cloud SQL Backup Permissions

|  |
| --- |
| cloudsql.backupRuns.create  cloudsql.backupRuns.delete  cloudsql.backupRuns.get  cloudsql.backupRuns.list  cloudsql.databases.list  cloudsql.instances.export  cloudsql.instances.get  cloudsql.instances.list  cloudsql.instances.listServerCas  cloudsql.instances.update  cloudsql.users.list  compute.regions.list  compute.zones.list  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy  serviceusage.services.list  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  compute.projects.get  resourcemanager.projects.get |

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to use Cloud IAM credentials while backing up a MySQL instance, the service account associated with the project to which the instance belongs must also have the cloudsql.instances.login permission assigned. |

Cloud Spanner Backup Permissions

|  |
| --- |
| spanner.databases.list  spanner.databases.get  spanner.databases.getDdl  spanner.databases.beginReadOnlyTransaction  spanner.databases.partitionQuery  spanner.databases.select  spanner.instanceConfigs.get  spanner.instanceConfigs.list  spanner.instances.get  spanner.instances.list  spanner.sessions.create  spanner.sessions.delete  compute.regions.list  compute.zones.list  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription,  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy  serviceusage.services.list  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  compute.projects.get  monitoring.timeSeries.list  resourcemanager.projects.get |

Page updated 1/26/2024

Page content applies to build 7.0.0.47
