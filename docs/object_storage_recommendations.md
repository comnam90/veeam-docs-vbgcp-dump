---
title: "object_storage_recommendations"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/object_storage_recommendations.html"
last_updated: "6/24/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud compresses all backed-up data when saving it to a backup repository. The compression rate depends on the type and structure of source data and usually varies from 50% to 60%. This means that the compressed data typically consumes 50% less storage space than the source data.

| Parameter | Value |
| --- | --- |
| Average size of backed-up data | 40%–50% of source data |
| Compression rate | 50%–60% |

Object Sizes

Depending on whether you choose to keep backed-up data in short-term or long-term storage, Veeam Backup for Google Cloud saves different objects to Google Cloud storage buckets.

| Object Type | Block Size |
| --- | --- |
| Backup data (Standard) | 1 MB (compressed to ~512 KB) |
| Backup data (Archive) | 512 MB |
| Metadata | 4 KB (per 1 GB of VM source data) |

Storage Bucket Placement

To achieve best performance, create backup repositories in regional storage buckets and place them in the same region as source instances. A situation where a storage bucket is located far from a source instance may cause slow network throughput between regions.

Cost Estimation

Veeam Backup for Google Cloud comes with a built-in cost calculator that allows you to estimate your Google Cloud expenses. It uses publicly available Google Cloud price lists, so it may not reflect your exact cost in case of custom pricing or an enterprise agreement. Full details can be found at the cost estimation step of the Add Policy wizard.

Related Topics

* [Performing VM Backup](performing_vm_backup.md)
* [Performing SQL Backup](performing_sql_backup.md)
* [Performing Spanner Backup](performing_spanner_backup.md)

Page updated 6/24/2025

Page content applies to build 7.0.0.47
