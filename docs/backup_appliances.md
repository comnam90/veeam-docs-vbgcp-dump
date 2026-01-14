---
title: "backup_appliances"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/backup_appliances.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

A backup appliance is a Linux-based VM instance where Veeam Backup for Google Cloud is installed. The backup appliance performs the following administrative activities:

* Manages architecture components.
* Coordinates snapshot creation, backup and recovery tasks.
* Controls backup policy scheduling.
* Generates daily reports and email notifications.

The backup appliance also maintains the configuration database that stores data collected from Veeam Backup for Google Cloud for the existing backup policies, protected VM, Cloud SQL and Cloud Spanner instances, deployed worker instances, connected Google Cloud projects and so on.

|  |
| --- |
| Tip |
| If you have multiple backup appliances deployed in Google Cloud, you can add the appliances to Veeam Backup & Replication, and then use the Veeam Backup & Replication console as the central management console for Veeam Backup for Google Cloud operations. For more information on the Veeam Backup & Replication console, see the [Veeam Backup & Replication User Guide](https://helpcenter.veeam.com/docs/vbr/userguide/backup_console.html?ver=13). |

Backup Appliance Software

The VM instance running Veeam Backup for Google Cloud is deployed with the pre-installed set of software components:

* Ubuntu 22.04
* ASP.NET Core Runtime 8.0
* PostgreSQL 16
* nginx 1.18
* libpam-google-authenticator 20191231-2
* Veeam Backup for Google Cloud installation packages

In case any software updates become available for the backup appliance, these updates can be installed using the Veeam Updater service as described in section [Updating Veeam Backup for Google Cloud](updates_install.md).

Backup Appliance Components

The backup appliance uses the following components:

* Backup service — coordinates data protection and disaster recovery operations.

* Configuration database — stores data on the existing backup policies, worker instance configurations, added IAM roles, sessions and so on, as well as information on the available and protected resources collected from Google Cloud.
* Web UI — provides a web interface that allows user to access the Veeam Backup for Google Cloud functionality.
* Updater service — allows Veeam Backup for Google Cloud to check, view and install product and package updates.
* Self Backup service — allows Veeam Backup for Google Cloud to back up and restore the configuration database of the backup appliance.
* REST API service — allows users to perform operations with Veeam Backup for Google Cloud entities using HTTP requests and standard HTTP methods. For details, see the [Veeam Backup for Google Cloud REST API Reference](https://helpcenter.veeam.com/docs/vbgc/rest/overview.html?ver=50).

Page updated 11/18/2025

Page content applies to build 7.0.0.47
