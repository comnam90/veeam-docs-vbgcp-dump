---
title: "Deploying Backup Appliance"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/deploying_appliance.html"
last_updated: "12/19/2025"
product_version: "7.0.0.47"
---

# Deploying Backup Appliance


|  |
| --- |
| Important |
| * Before you start deploying a backup appliance, make sure that [Infrastructure Manager](https://cloud.google.com/infrastructure-manager/docs/enable-service) is enabled for the Google Cloud project to which the appliance will belong. Otherwise, Veeam Backup for Google Cloud deployment may fail or cause unexpected errors. * If the [OS Login service](https://docs.cloud.google.com/compute/docs/oslogin) is used as the access management method on your project, Veeam Backup & Replication will not be able to use SSH to connect to the backup appliance, and the deployment operation will fail. |

To deploy a new backup appliance from the Veeam Backup & Replication console, do the following:

1. [Launch the New Veeam Backup for Google Cloud Appliance wizard](deploy_appliance_launch.md).
2. [Choose a deployment mode](deploy_appliance_mode.md).
3. [Specify a Veeam Backup for Google Cloud account in which the appliance will be deployed](deploy_appliance_account.md).
4. [Specify a name and description for the appliance](deploy_appliance_instance.md).
5. [Specify connection type for the appliance](vbgc_connection_type.md).
6. [Specify network settings for the appliance](deploy_network_resources.md).
7. [Specify credentials for the default user account](deploy_guest_os_credentials.md).
8. [Wait for the appliance to be added to the backup infrastructure](deploy_appliance_apply.md).
9. [Finish working with the wizard](deploy_appliance_finish.md).

How Deployment Works

When deploying Veeam Backup for Google Cloud, Veeam Backup & Replication performs the following steps:

1. Creates a [Google Cloud storage bucket](https://brainstorage.amust.local/index.php/Veeam_Plug-in_for_Google_Cloud/VB_deployment##) with the name deployfiles-{InstanceName}-{TimeStamp} and uploads a preconfigured VM deployment package to this bucket.
2. Deploys a VM instance from the Ubuntu 22.04 LTS image.
3. Creates a temporary Google Cloud storage bucket for installation packages.
4. Uploads Veeam Backup for Google Cloud installation packages and their software dependencies to the temporary storage bucket.
5. Initiates the creation of a [Google Cloud storage bucket](https://cloud.google.com/infrastructure-manager/docs/deployments-revisions#deployment_metadata) with the name {ProjectNumber}-{Location}-blueprint-config to store the installation state files, logs and variables.
6. Installs the [required software components](backup_appliances.md) on the VM instance.
7. Configures the default service account on the backup appliance. The default service account will then be used to perform data protection and recovery operations within the Google Cloud project to which the backup appliance belongs. Out of the box, this account is already assigned all the required permissions listed in section [Service Account Permissions](permissions.md).

You will be able to add other service accounts later, after Veeam Backup for Google Cloud installation. For more information, see [Managing Service Accounts](managing_service_accounts.md).

1. Removes the temporary storage bucket.

Note that the deployfiles-{InstanceName}-{TimeStamp} and {ProjectNumber}-{Location}-blueprint-config buckets will remain in Google Cloud infrastructure after the deployment procedure and must not be removed manually. Otherwise, [backup appliance removal operation](removing_appliances.md) may fail or cause unexpected errors.

Related Topics

[Connecting to Existing Appliances](connecting_existing_appliance.md)


