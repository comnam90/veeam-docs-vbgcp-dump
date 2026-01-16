---
title: "disk_restore_encryption"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/disk_restore_encryption.html"
last_updated: "11/4/2025"
product_version: "7.0.0.47"
---


In this article

[This step applies only if you have selected the Restore to new location, or with different settings option at the Restore Mode step of the wizard]

At the Encryption step of the wizard, do the following:

* If you do not want to change the existing encryption scheme of the restored persistent disks, select the Use original encryption scheme option.
* If you want to encrypt the restored persistent disks with a Google Cloud KMS CMEK, select the Use customer-managed encryption key from Google Cloud KMS option and choose the necessary CMEK from the Encryption key drop-down list.

For a CMEK to be displayed in the list of available encryption keys, it must be stored in the region selected at [step 6](disk_restore_region.md) of the wizard.

[![Restoring VM Disks](images/disk_restore_encryption.webp)](images/disk_restore_encryption.webp "Restoring VM Disks")

Page updated 11/4/2025

Page content applies to build 7.0.0.47
