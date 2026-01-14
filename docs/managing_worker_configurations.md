---
title: "managing_worker_configurations"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_worker_configurations.html"
last_updated: "11/8/2024"
product_version: "7.0.0.47"
---


In this article

A configuration is a group of network settings that Veeam Backup for Google Cloud uses to deploy worker instances in a specific Google Cloud region to perform data protection and disaster recovery operations. Veeam Backup for Google Cloud deploys one worker instance per each VM, Cloud SQL or Cloud Spanner instance added to a backup policy or restore task.

By default, Veeam Backup for Google Cloud deploys worker instances with the same network configurations as those specified for the processed instances. However, to optimize infrastructure costs and to ensure better performance of backup and restore processes, you can add worker configurations to specify network settings for each region in which worker instances will be deployed.

In This Section

* [Specifying Project for Worker Instances](worker_project.md)
* [Adding Worker Configurations](adding_worker_configurations.md)
* [Editing Worker Configurations](editing_worker_configurations.md)
* [Removing Worker Configurations](removing_worker_configurations.md)

Page updated 11/8/2024

Page content applies to build 7.0.0.47
