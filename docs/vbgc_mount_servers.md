---
title: "Mount Servers"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/vbgc_mount_servers.html"
last_updated: "11/21/2025"
product_version: "7.0.0.47"
---

# Mount Servers


Mount server is a server required for restore operations such as Instant Recovery, guest OS file restore and application item restore. To access files or items stored in a backup file, Veeam Backup & Replication mounts the content of the backup to the mount server. After the content is mounted, Veeam Backup & Replication can obtain the files and copy them to the restore location.

Mount servers are created for every backup repository and are associated with it. When you configure a backup repository, you specify to which servers you want to assign the roles of the Windows mount server and the Linux mount server. To reduce the network load and speed up the restore process, it is recommended that the mount server is located in the same region as the backup repository where backup files are stored. For more information on mount server functionality and selection recommendations, see Veeam Backup & Replication User Guide, section [Mount Servers](https://helpcenter.veeam.com/docs/vbr/userguide/mount_server.html?ver=13).


