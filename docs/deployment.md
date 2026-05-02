---
title: "Deployment"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/deployment.html"
last_updated: "12/16/2025"
product_version: "7.0.0.47"
---

# Deployment


To deploy Veeam Backup for Google Cloud, do the following:

1. Deploy the backup server as described in the Veeam Backup & Replication User Guide, section [Installing Veeam Backup & Replication](https://helpcenter.veeam.com/docs/vbr/userguide/install_console.html?ver=13).

Alternatively, you can use a backup server that already exists in your backup infrastructure if it meets the Veeam Plug-in for Google Cloud [system requirements](system_requirements.md).

1. [Install Veeam Plug-in for Google Cloud on the backup server](deploying_plugin.md).

This step applies only to Veeam Backup & Replication versions prior to 12.0. Version 12.0 (and later) comes pre-packed with Veeam Plug-in for Google Cloud.

1. [Deploy a backup appliance](deploying_appliance.md).

Related Topics

* [Upgrading Plug-In](upgrading_plugin.md)
* [Upgrading Backup Appliance](updating_vb.md)


