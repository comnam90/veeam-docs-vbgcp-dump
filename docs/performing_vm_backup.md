---
title: "Performing VM Backup"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/performing_vm_backup.html"
last_updated: "8/30/2023"
product_version: "7.0.0.47"
---

# Performing VM Backup


One backup policy can be used to process one or more VM instances within one Google Cloud project or folder. The scope of data that you can protect in a project or folder is limited by permissions of a service account that is specified in the backup policy settings.

Before you create a VM backup policy, check the following prerequisites:

* If you plan to create image-level backups of VM instances, backup infrastructure components that will take part in the backup process must be added to the backup infrastructure and configured properly. These include [backup repositories](managing_repositories.md) and [worker instances](managing_workers.md).
* If you plan to receive email notifications on the backup policy results, configure SMTP server settings first. For more information, see [Configuring Global Notification Settings](configuring_global_notification_settings.md).

To schedule data protection tasks to run automatically, [create backup policies](creating_vm_backup_policies.md). For each protected VM instance, you can also [take a cloud-native snapshot manually](creating_manual_snapshots_vms.md) when needed.


