---
title: "ports"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/ports.html"
last_updated: "1/6/2026"
product_version: "7.0.0.47"
---


In this article

As Veeam Plug-in for Google Cloud is installed on the same machine where Veeam Backup & Replication runs, it uses the same ports as those described in the Veeam Backup & Replication User Guide, section [Ports](https://helpcenter.veeam.com/docs/vbr/userguide/used_ports.html?ver=13). In addition, Veeam Plug-in for Google Cloud also uses ports listed in the following table.

| From | To | Protocol | Port | Description |
| --- | --- | --- | --- | --- |
| Workstation web browser | Backup appliance | TCP/HTTPS | 443 | Required to access the Web UI component from a user workstation. |
| TCP/HTTPS | 13140 | Required to communicate with the REST API service running on the backup appliance. |
| Worker instance | TCP/HTTPS | 443 | Required to access the file-level recovery browser running on a worker instance during the file-level recovery process. |
| Backup appliance | Ubuntu Security Repository (security.ubuntu.com) | TCP/HTTP | 80 | Required to get OS security updates. |
| Veeam Update Repository (repository.veeam.com), [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) (cloudfront.net, amazonaws.com) | TCP/HTTPS | 443 | Required to download available product updates, worker deployment packages and restore utilities.  Note: Veeam Update Repository uses the Amazon CloudFront service to distribute traffic when downloading product updates. |
| SMTP server | TCP | 587 | Required to send email notifications.  Note: You cannot use the TCP port 25 that is most commonly used by SMTP servers — the port is always blocked by Google Compute Engine. For more information, see [Google Cloud documentation](https://cloud.google.com/compute/docs/tutorials/sending-mail). |
| nginx web server | HTTPS | 80/443 | Required to upgrade the backup appliance. |
| PostgreSQL Apt Repository | HTTPS | 80/443 | Required to get PostgreSQL updates. |
| Microsoft Package Repository (packages.microsoft.com) | HTTPS | 80/443 | Required to get .NET and ASP.NET updates. |
| Veeam Plug-in for Google Cloud | Backup appliance, [Google Cloud services](google_cloud_apis.md) | TCP/HTTPS | 443 | Required to communicate with Google Cloud and Veeam Backup for Google Cloud. |
| AWS CheckIP service (DNS name: checkip.amazonaws.com) | TCP/HTTPS | 443 | Required to get the public IP address of the Veeam Backup & Replication server during the deployment of Veeam Plug-in for Google Cloud. |
| Veeam Backup & Replication console and Veeam ONE server | Backup server | TCP | 9403 | Required to connect to Veeam Plug-in for Google Cloud. |
| Worker instance | [Google Cloud services](google_cloud_apis.md) | TCP/HTTPS | 443 | Required to perform data protection and disaster recovery operations. |
| Cloud SQL instances | TCP | 3306 |
| TCP | 5432 |
| Cloud Spanner instances | TCP | 443 |
| [Google Cloud services](google_cloud_apis.md) | Backup appliance | SSH | 22 | Required to allow inbound traffic through SSH protocol during backup appliance deployment and upgrade and to perform automatic updates of the TLS certificates installed on the appliance. |

|  |
| --- |
| Note |
| When you deploy a backup appliance from the Veeam Backup & Replication console, Veeam Backup & Replication automatically creates firewall rules for the required ports to allow communication between the backup server and the appliance components. |

Related Topics

[Google Cloud APIs](google_cloud_apis.md)

Page updated 1/6/2026

Page content applies to build 7.0.0.47
