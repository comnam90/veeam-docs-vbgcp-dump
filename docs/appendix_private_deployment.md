---
title: "Appendix A. Configuring Deployment Mode"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/appendix_private_deployment.html"
last_updated: "4/25/2025"
product_version: "7.0.0.47"
---

# Appendix A. Configuring Deployment Mode


Veeam Backup for Google Cloud automatically deploys worker instances in Google Cloud for the duration of backup or restore processes, and removes them immediately after the processes complete. Depending on the types of workloads you plan to protect with Veeam Backup for Google Cloud and on the external security requirements, you can configure a deployment mode for your worker instances.

Configuring Private IPs for Worker Instances Performing File-Level Recovery

By default, worker instances deployed by Veeam Backup for Google Cloud do not use public IPs because they access protected Google Cloud resources through private virtual networks. The only exception is worker instances deployed during file-level recovery operations, allowing you to access backed-up files through the file-level recovery browser.

To enable access to the browser only through private networks, do the following:

1. Connect to the backup appliance through SSH as described in [Google Cloud documentation](https://cloud.google.com/compute/docs/instances/ssh).

1. Edit the FlrPerformer value in the /opt/veeam/gcpbackup/JobManagerSettings.json configuration file:

|  |
| --- |
| "FlrPerformer": {         "DisableWorkerPublicIp": true    } |

Configuring Public IPs for Worker Instances Processing Cloud SQL Instances

By default, worker instances that are deployed to process Cloud SQL instances do not have public network access. That is why you must configure private network access between the subnets of these worker instances and the subnets of the processed Cloud SQL instances as described in [Google Cloud documentation](https://cloud.google.com/vpc/docs/configure-private-services-access).

Alternatively, you can configure the worker instances to allow public IP access. To do that, add the SqlWorker parameter to the /opt/veeam/gcpbackup/ServiceSettings.json configuration file:

|  |
| --- |
| "SqlWorker": {                  "AllowExternalIp": true           } |

Deploying Worker Instances as Shielded VMs

If you need the Virtual Trusted Platform Module (vTPM) and Integrity Monitoring enabled for your worker instances, you can instruct Veeam Backup for Google Cloud to deploy them as [Shielded VMs](https://cloud.google.com/compute/shielded-vm/docs/shielded-vm). To do that, edit the Worker value in the /opt/veeam/gcpbackup/ServiceSettings.json configuration file, and restart the veeambackup service:

|  |
| --- |
| "Worker": {                 "EnableVtpm": true,                 "EnableIntegrityMonitoring": true         } |


