---
title: "snapshot_permissions"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/snapshot_permissions.html"
last_updated: "2/7/2024"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to create and manage cloud-native snapshots of Google Cloud instances, the service account associated with the Google Cloud project managing instances that you want to protect must have the following permissions.

VM Snapshot Permissions

|  |
| --- |
| compute.addresses.list  compute.firewalls.list  compute.regions.list  compute.disks.list  compute.disks.createSnapshot  compute.disks.get  compute.instances.get  compute.instances.list  compute.networks.list  compute.projects.get  compute.snapshots.create  compute.snapshots.delete  compute.snapshots.get  compute.snapshots.list  compute.snapshots.getIamPolicy  compute.snapshots.setIamPolicy  compute.snapshots.setLabels  compute.subnetworks.list  compute.routes.list  compute.zones.list  compute.globalOperations.list  compute.globalOperations.get  compute.zoneOperations.get  compute.regionOperations.get  resourcemanager.projects.get  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  logging.sinks.update  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.subscriptions.consume  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy  pubsub.topics.update  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  serviceusage.services.list |

Cloud SQL Snapshot Permissions

|  |
| --- |
| cloudsql.backupRuns.create  cloudsql.backupRuns.delete  cloudsql.backupRuns.get  cloudsql.backupRuns.list  cloudsql.databases.list  cloudsql.instances.get  cloudsql.instances.list  compute.regions.list  compute.zones.list  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy  serviceusage.services.list  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  compute.projects.get  resourcemanager.projects.get |

Cloud Spanner Snapshot Permissions

|  |
| --- |
| spanner.backups.copy,  spanner.backups.create  spanner.backups.get  spanner.backups.list  spanner.backups.delete  spanner.backupOperations.cancel  spanner.backupOperations.get  spanner.backupOperations.list  spanner.databases.createBackup  spanner.databases.list  spanner.instanceConfigs.get  spanner.instanceConfigs.list  spanner.instances.get  spanner.instances.list  compute.regions.list  compute.zones.list  logging.sinks.create  logging.sinks.delete  logging.sinks.get  logging.sinks.list  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.getIamPolicy  pubsub.topics.list  pubsub.topics.setIamPolicy,  serviceusage.services.list  cloudkms.keyRings.list  cloudkms.cryptoKeys.list  compute.projects.get  resourcemanager.projects.get |

Page updated 2/7/2024

Page content applies to build 7.0.0.47
