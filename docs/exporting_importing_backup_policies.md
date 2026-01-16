---
title: "exporting_importing_backup_policies"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/exporting_importing_backup_policies.html"
last_updated: "11/21/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud allows you to use settings of an existing backup policy as a template for creating other backup policies. You can export a backup policy to a .JSON file, modify the necessary settings in the file, and then import the policy to the same or a different backup appliance.

Exporting Backup Policies

To export a backup policy to a .JSON file, do the following:

1. Navigate to Policies.
2. Switch to the necessary tab and select the backup policy.
3. Click Advanced > Export Policy.

Veeam Backup for Google Cloud will save the backup policy settings as a single .JSON file to the default download directory on the local machine.

[![Exporting Backup Policy](images/exporting_backup_policy.webp)](images/exporting_backup_policy.webp "Exporting Backup Policy")

Importing Backup Policies

To import a backup policy from a .JSON file, do the following:

1. Click Advanced > Import Policy.
2. In the Import Policy window, specify a name for the imported backup policy, paste the content of the necessary .JSON file, and click Import.

[![Importing Backup Policy](images/importing_backup_policy.webp)](images/importing_backup_policy.webp "Importing Backup Policy")

Page updated 11/21/2025

Page content applies to build 7.0.0.47
