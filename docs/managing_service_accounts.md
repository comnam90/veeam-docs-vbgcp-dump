---
title: "managing_service_accounts"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/managing_service_accounts.html"
last_updated: "2/7/2024"
product_version: "7.0.0.47"
---


In this article

For each data protection and disaster recovery operation performed for a Google Cloud resource, you must specify a service account that has access to the resource and is assigned a set of permissions required to perform the operation.

Particularly, Veeam Backup for Google Cloud uses service accounts to perform the following tasks:

* To access projects and folders that manage Google Cloud resources.
* To synchronize the Google Cloud environment data with the data stored in the configuration database of the backup appliance.
* To create and remove snapshots of VM instances.
* To create and remove snapshots of Cloud SQL instances.
* To create and remove snapshots of Cloud Spanner instances.

During the product installation, the project in which the backup appliance is being deployed is automatically added to the configuration database, and the default service account is created in this project. The account can be further assigned permissions to perform operations within the initial project or any other project (or folder) added to Veeam Backup for Google Cloud. You can also create new and add existing Google Cloud service accounts to use them to access resources for data protection and disaster recovery tasks.

After you create or add a service account, you must grant the account the necessary permissions required to perform operations in a specific project (or folder), as described in section [Managing Projects and Folders](managing_projects.md).

In This Section

* [Adding Service Accounts](adding_service_accounts.md)
* [Editing Service Accounts](editing_service_accounts.md)
* [Removing Service Accounts](removing_service_accounts.md)

Page updated 2/7/2024

Page content applies to build 7.0.0.47
