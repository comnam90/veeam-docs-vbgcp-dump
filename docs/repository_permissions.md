---
title: "repository_permissions"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/repository_permissions.html"
last_updated: "10/22/2025"
product_version: "7.0.0.47"
---


In this article

To allow Veeam Backup for Google Cloud to create a backup repository in a Google Cloud storage bucket and to access the repository when performing backup and restore operations, the service account associated with the Google Cloud project to which this bucket belongs must have the following permissions:

|  |
| --- |
| storage.buckets.list  storage.buckets.get  storage.objects.create  storage.objects.delete  storage.objects.list  storage.objects.get  storage.hmacKeys.create  storage.hmacKeys.list  storage.hmacKeys.get  resourcemanager.projects.get  serviceusage.services.list  storage.buckets.getIamPolicy  storage.buckets.setIamPolicy \*  compute.projects.get  storage.multipartUploads.create |

\* Veeam Backup for Google Cloud will use the storage.buckets.setIamPolicy permission only to grant access to repositories while performing SQL backup operations.

Page updated 10/22/2025

Page content applies to build 7.0.0.47
