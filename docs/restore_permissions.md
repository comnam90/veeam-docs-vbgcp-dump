---
title: "restore_permissions"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_permissions.html"
last_updated: "11/28/2024"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to perform restore operations, the service account associated with the Google Cloud project that will be used to manage the restored instances must have the following permissions.

VM Restore Permissions

|  |
| --- |
| compute.addresses.list  compute.disks.create  compute.disks.get  compute.disks.setLabels  compute.disks.use  compute.disks.delete  compute.disks.useReadOnly  compute.firewalls.list  compute.globalOperations.list  compute.globalOperations.get  compute.instances.create  compute.instances.delete  compute.instances.get  compute.instances.setLabels  compute.instances.setMachineResources  compute.instances.setMetadata  compute.instances.setMinCpuPlatform  compute.instances.setName  compute.instances.setScheduling  compute.instances.setServiceAccount  compute.instances.setTags  compute.instances.start  compute.instances.stop  compute.instances.updateDisplayDevice  compute.instances.updateNetworkInterface  compute.instances.setDeletionProtection  compute.machineTypes.list  compute.networks.list  compute.projects.get  compute.regionOperations.get  compute.regions.get  compute.regions.list  compute.snapshots.create  compute.snapshots.delete  compute.snapshots.get  compute.snapshots.getIamPolicy  compute.snapshots.list  compute.snapshots.setLabels  compute.snapshots.useReadOnly  compute.subnetworks.list  compute.subnetworks.use  compute.subnetworks.useExternalIp  compute.zoneOperations.get  compute.zones.get  compute.zones.list  iam.serviceAccounts.actAs  iam.serviceAccounts.list  resourcemanager.projects.get  cloudkms.cryptoKeys.list  cloudkms.keyRings.list  compute.addresses.use  compute.addresses.useInternal  compute.disks.list  compute.instances.list  compute.routes.list  cloudkms.cryptoKeys.setIamPolicy  cloudkms.cryptoKeys.getIamPolicy  serviceusage.services.list  pubsub.subscriptions.setIamPolicy  pubsub.subscriptions.getIamPolicy  pubsub.topics.setIamPolicy  pubsub.topics.getIamPolicy  storage.objects.create  storage.objects.delete  storage.objects.list  storage.objects.get  storage.objects.update  storage.buckets.create  storage.buckets.delete |

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to connect a restored VM instance to a Shared VPC network, the service account associated with the project to which the instance belongs must also have either the compute.networkUser role for the whole Shared VPC host project, or the compute.networkViewer role for the whole host project plus compute.networkUser for specific subnets in the host project.  To allow Veeam Backup for Google Cloud to check the subnet configuration of the Shared VPC network to which the restored VM instance is connected, you must also add the following permissions to the service account associated with the project to which the instance belongs: compute.firewalls.list, compute.networks.get, compute.routes.list and compute.subnetworks.get for the whole Shared VPC host project.  To learn how to provide access to Shared VPC networks, see [Google Cloud documentation](https://cloud.google.com/vpc/docs/provisioning-shared-vpc#networkuseratproject). |

Cloud SQL Restore Permissions

|  |
| --- |
| cloudkms.cryptoKeys.getIamPolicy  cloudkms.cryptoKeys.list  cloudkms.cryptoKeys.setIamPolicy  cloudkms.keyRings.list  cloudsql.backupRuns.get  cloudsql.instances.create  cloudsql.instances.get  cloudsql.instances.import  cloudsql.instances.restoreBackup  cloudsql.instances.update  compute.firewalls.list  compute.networks.list  compute.projects.get  compute.regions.list  compute.routes.list  compute.subnetworks.list  compute.zones.list  resourcemanager.projects.get  cloudsql.backupRuns.list  cloudsql.databases.create  cloudsql.databases.list  cloudsql.instances.list  cloudsql.instances.listServerCas  cloudsql.users.create  cloudsql.users.list  cloudsql.users.update  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.list  serviceusage.services.list  cloudsql.backupRuns.create  cloudsql.backupRuns.delete  cloudsql.databases.get |

|  |
| --- |
| Important |
| To allow Veeam Backup for Google Cloud to use Cloud IAM credentials while restoring a MySQL instance, the service account associated with the project to which the instance belongs must also have the cloudsql.instances.login permission assigned. |

Cloud Spanner Restore Permissions

|  |
| --- |
| spanner.backupOperations.get  spanner.backups.get  spanner.backups.restoreDatabase  spanner.backups.delete  spanner.databaseOperations.get  spanner.databases.create  spanner.databases.list  spanner.databases.update  spanner.instanceConfigOperations.get  spanner.instanceConfigs.create  spanner.instanceConfigs.delete  spanner.instanceConfigs.get  spanner.instanceConfigs.list  spanner.instanceOperations.get  spanner.instances.create  spanner.instances.delete  spanner.instances.get  spanner.instances.list  cloudkms.cryptoKeys.getIamPolicy  cloudkms.cryptoKeys.list  cloudkms.cryptoKeys.setIamPolicy  cloudkms.keyRings.list  compute.projects.get  monitoring.timeSeries.list  resourcemanager.projects.get  spanner.databases.get  spanner.databases.updateDdl  spanner.databases.beginOrRollbackReadWriteTransaction  spanner.databases.beginReadOnlyTransaction  spanner.databases.write  spanner.databases.select  spanner.sessions.create  spanner.sessions.delete  pubsub.subscriptions.consume  pubsub.subscriptions.create  pubsub.subscriptions.delete  pubsub.subscriptions.get  pubsub.subscriptions.list  pubsub.topics.attachSubscription  pubsub.topics.create  pubsub.topics.delete  pubsub.topics.detachSubscription  pubsub.topics.get  pubsub.topics.list  serviceusage.services.list  resourcemanager.projects.get  resourcemanager.projects.getIamPolicy  resourcemanager.projects.setIamPolicy |

Page updated 11/28/2024

Page content applies to build 7.0.0.47
