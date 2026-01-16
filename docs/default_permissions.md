---
title: "default_permissions"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/default_permissions.html"
last_updated: "12/22/2023"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud requires a service account in each Google Cloud project where data protection and disaster recovery tasks will be performed. To allow Veeam Backup for Google Cloud to access Google Cloud services and resources that you want to protect, service accounts used by Veeam Backup for Google Cloud must have the following minimal set of permissions:

|  |
| --- |
| compute.disks.addResourcePolicies  compute.disks.get  compute.instances.get  compute.resourcePolicies.create  compute.resourcePolicies.get  compute.resourcePolicies.use  compute.zones.get  serviceusage.services.list  compute.projects.get  resourcemanager.projects.get |

Page updated 12/22/2023

Page content applies to build 7.0.0.47
