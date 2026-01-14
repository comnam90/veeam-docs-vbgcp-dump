---
title: "backup_policy_name"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_policy_name.html"
last_updated: "11/11/2025"
product_version: "7.0.0.47"
---


In this article

At the Policy Info step of the wizard, use the Name and Description fields to enter a name for the new backup policy and to provide a description for future reference. The policy name can contain only uppercase Latin letters, lowercase Latin letters, numeric characters and hyphens; the maximum length of the name is 127 characters.

|  |
| --- |
| Note |
| You can tell snapshots created by Veeam Backup for Google Cloud from other snapshots in your infrastructure by their names — the name of every snapshot created by a backup policy will contain the word veeam, a GUID and the ordinary number of the processed persistent disk: veeam-{GUID}-{disk number}. |

[![Adding Backup Policy](images/policy_name.webp)](images/policy_name.webp "Adding Backup Policy")

Page updated 11/11/2025

Page content applies to build 7.0.0.47
