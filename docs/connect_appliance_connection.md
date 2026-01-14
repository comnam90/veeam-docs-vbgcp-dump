---
title: "connect_appliance_connection"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/connect_appliance_connection.html"
last_updated: "12/2/2025"
product_version: "7.0.0.47"
---


In this article

At the Connection Type step of the wizard, specify the way Veeam Backup & Replication will connect to the backup appliance:

* Select the Direct connection option if the backup appliance is connected to a network with the inbound internet access allowed and you want the backup server to connect to this appliance over the internet. In this case, Veeam Backup & Replication will detect the public IP address of the appliance automatically.
* Select the Private network option if the backup appliance and the backup server are connected to the same private network, or you want the backup server to connect to this appliance over VPN. In this case, you must specify the private IP address or the DNS hostname of the appliance in the Specify the IP address or DNS name of the appliance field.

![Step 5. Specify Connection Type](images/add_server_connection.webp)

Page updated 12/2/2025

Page content applies to build 7.0.0.47
