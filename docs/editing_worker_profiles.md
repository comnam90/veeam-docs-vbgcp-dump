---
title: "Editing Worker Profiles"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/editing_worker_profiles.html"
last_updated: "11/14/2025"
product_version: "7.0.0.47"
---

# Editing Worker Profiles


For each set of worker profiles created for a Goggle Cloud region, you can modify settings specified while creating the profile set:

1. Switch to the Configuration page.
2. Navigate to Workers > Profile.
3. Select the profile set and click Edit.
4. Complete the Edit Worker Profiles wizard:

1. To change profiles that will be used to deploy worker instances in the selected region, follow the instructions provided in section [Adding Worker Profiles](profiles_selection.md) (step 3).
2. At the Summary step of the wizard, review configuration information and click Finish to confirm the changes.

|  |
| --- |
| Note |
| If there are any worker instances that are currently involved in a backup or archive process in the selected region, the changes will be applied only when the process completes. |

[![Editing Worker Profiles](images/editing_worker_profiles.webp)](images/editing_worker_profiles.webp "Editing Worker Profiles")


