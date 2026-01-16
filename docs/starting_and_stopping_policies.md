---
title: "starting_and_stopping_policies"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/starting_and_stopping_policies.html"
last_updated: "11/13/2025"
product_version: "7.0.0.47"
---


In this article

You can start a backup policy manually, for example, if you want to create an additional restore point in the snapshot or backup chain and do not want to modify the configured backup policy schedule. You can also stop a backup policy if processing of an instance is about to take too long, and you do not want the policy to have an impact on the production environment during business hours.

To start or stop a backup policy, do the following:

1. In the Veeam Backup & Replication console, open the Home view.
2. Navigate to Jobs.
3. Select the necessary backup policy, and click Start or Stop on the ribbon.

Alternatively, you can right-click the selected policy, and select Start or Stop.

[![Start or stop backup policy](images/starting_policy.webp)](images/starting_policy.webp "Start or stop backup policy")

Page updated 11/13/2025

Page content applies to build 7.0.0.47
