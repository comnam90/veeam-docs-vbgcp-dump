---
title: "configuring_global_notification_settings"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/configuring_global_notification_settings.html"
last_updated: "11/12/2025"
product_version: "7.0.0.47"
---


In this article

You can specify email notification settings for automated delivery of backup policy results and daily reports. Every daily report contains cumulative statistics for all backup policy and snapshot retention sessions run within the past 24-hour period.

To connect an email server that will be used for sending email notifications:

1. Switch to the Configuration page.
2. Navigate to General > Email.
3. Select the Enable email notifications check box.
4. Click the link in the Email server field and configure [email server settings](#server).

1. In the From field, enter an email address of the notification sender. This email address will be displayed in the From field of notifications.

1. In the To field, enter an email address of a recipient. Use a semicolon to separate multiple recipient addresses.

For each particular policy, you can specify additional recipients. For more information, see [Creating Backup Policies](backup_policy_notifications.md).

|  |
| --- |
| Note |
| If you specify the same email recipient in both backup policy notification and global notification settings, Veeam Backup for Google Cloud will send each notification to this recipient twice. |

1. In the Subject field, specify a subject for notifications. You can use the following runtime variables:

* %JobName% — a backup policy name.
* %JobResult% — a backup policy result.
* %ObjectCount% — the number of instances in a backup policy.
* %Issues% — the number of instances in a backup policy that encountered any issues (errors and warnings) while being processed.

1. In the Notify immediately on policy section, choose whether you want to receive email notifications in case backup policies complete successfully, complete with warnings or complete with errors.

1. To receive daily reports, select the Send daily report at check box and specify the exact time when the reports will be sent.

1. Click Save.

|  |
| --- |
| Tip |
| Veeam Backup for Google Cloud allows you to send a test message to check whether you have configured the settings correctly. To do that, click Send Test Email. A test message will be sent to the specified email address. |

Configuring Email Server Settings

To configure email server settings, choose whether you want to employ [Basic (SMTP)](#basic) or [Modern (OAuth 2.0)](#modern) authentication for your email server.

Using Basic Authentication

To employ the Basic authentication to connect to your email server, in the Email Server Settings window:

1. From the Authentication drop-down list, select Basic.
2. In the Email server name or address field, enter a DNS name or an IP address of the SMTP server. All email notifications (including test messages) will be sent by this SMTP server.
3. In the Port field, specify a communication port for SMTP traffic. The default SMTP port is 587.
4. In the Timeout field, specify a connection timeout for responses from the SMTP server.
5. For an SMTP server with SSL/TLS support, select the Connect using SSL check box to enable SSL data encryption.
6. If your SMTP server requires authentication, select the This server requires authentication check box and choose an account that will be used when authenticating against the SMTP server from the Connect as drop-down list.

For an account to be displayed in the list of available accounts, it must be added to Veeam Backup for Google Cloud as described in section [Adding SMTP Accounts](adding_smtp_accounts.md). If you have not added the necessary account beforehand, click Add and complete the Add Account wizard.

1. Click Save.

Using Modern Authentication

To employ the Modern authentication to connect to your email server:

1. In Email Server Settings window, copy the URL from the Redirect URL field.
2. For Veeam Backup for Google Cloud to be able to use OAuth 2.0 to access Google Cloud or Microsoft Azure APIs, register a new client application either in the [Google Cloud console](https://developers.google.com/workspace/guides/configure-oauth-consent) or in the [Microsoft Azure portal](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

When registering the application, make sure that the redirect URI specified for the application matches the URL copied from the Veeam Backup for Google Cloud Web UI.

|  |
| --- |
| Important |
| If you plan to use a client application registered in the Microsoft Azure portal, you must grant is the Mail.Send Microsoft Graph application permission and the following Microsoft Graph delegated permissions: email, offline\_access, openid, User.Read. For more information on Microsoft Graph permissions, see [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference). |

1. Back to the Veeam Backup for Google Cloud Web UI, do the following in Email Server Settings window:

1. From the Authentication drop-down list, select Modern.
2. Use the Email server drop-down list to choose whether the server that you want to use to send email notifications is a Google or Microsoft email server.
3. In the Application client ID and Client secret fields, provide the Client ID and Client secret created for the application as described in [Google Cloud documentation](https://developers.google.com/workspace/guides/create-credentials#oauth-client-id) or [Microsoft Docs](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
4. [Applies only if you have selected the Microsoft option] In the Tenant ID field, provide the ID of an Azure AD tenant in which the application has been registered.
5. Click Authorize. You will be redirected to the authorization page. Sign in using a Google or Microsoft Azure account to validate the configured settings.

[![Configuring Notification Settings](images/notification_settings.webp)](images/notification_settings.webp "Configuring Notification Settings")

Page updated 11/12/2025

Page content applies to build 7.0.0.47
