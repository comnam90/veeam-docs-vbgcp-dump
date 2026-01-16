---
title: "managing_permissions"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_permissions.html"
last_updated: "6/24/2025"
product_version: "7.0.0.47"
---


In this article

Veeam Backup for Google Cloud controls access to its functionality with the help of user roles. A role defines what operations users can perform and what range of data is available to them in the Veeam Backup for Google Cloud UI.

There are 3 roles that you can assign to users working with Veeam Backup for Google Cloud:

* Portal Administrator — can perform all configuration actions, can manage user roles, and can also act as a Portal Operator and Restore Operator.
* Portal Operator — can create, edit and start backup policies, manage the protected data, perform all restore operations and view session statistics.
* Restore Operator — can only perform restore operations and view session statistics.

The following table describes the functionality available to users with different roles in the Veeam Backup for Google Cloud UI.

| Tab | Functionality | Portal Administrator | Portal Operator | Restore Operator |
| --- | --- | --- | --- | --- |
| Overview | Dashboard | Full | Full | N/A |
| Resources | Infrastructure | Full | Full | N/A |
| Policies | Backup policies | Full | Full | N/A |
| Protected Data | Restore | Full | Full | Execute |
| File-level recovery | Full | Full | Execute |
| Remove | Full | Full | N/A |
| Session Logs | Session logs | Full | Full | Read |
| Stop session execution | Full | Full | N/A |
| Configuration | | | | |
| Infrastructure | Service accounts, projects and folders | Full | N/A | N/A |
| Accounts | Portal users and SMTP accounts | Full | N/A | N/A |
| Repositories | Backup repositories | Full | N/A | N/A |
| Workers | Worker instances | Full | N/A | N/A |
| General | General settings | Full | N/A | N/A |
| License | Licensing | Full | N/A | N/A |
| Support Information | Updates and logs | Full | N/A | N/A |

In This Section

* [Adding User Accounts](adding_backup_admins.md)
* [Changing User Passwords](changing_passwords.md)
* [Enabling Multi-Factor Authentication](enabling_mfa.md)

Page updated 6/24/2025

Page content applies to build 7.0.0.47
