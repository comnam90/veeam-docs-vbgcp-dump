---
title: "Step 5. Choose Restore Options"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/restore_config_options.html"
last_updated: "11/20/2025"
product_version: "7.0.0.47"
---

# Step 5. Choose Restore Options


By default, Veeam Backup & Replication restores only configuration data for the existing infrastructure components, created backup policies and configured global settings. At the Restore Options step of the wizard, you can choose whether you want to restore session logs and portal users of the initial backup appliance as well.

If you select the Local users check box, Veeam Backup & Replication will restore all Portal Administrators, Portal Operators and Restore Operators saved to the configuration backup file — and overwrite the currently added portal users. If you select the Session history option, Veeam Backup & Replication will restore backup sessions, restore sessions, rescan sessions and service sessions — in this case, the restore process may take more time to complete.

|  |
| --- |
| Important |
| After you click Next, the restore process will start. You will not be able to halt the process or edit the restore settings. |

![Step 5. Choose Restore Options](images/config_restore_options.webp)


