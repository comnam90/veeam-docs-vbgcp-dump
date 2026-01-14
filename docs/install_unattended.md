---
title: "install_unattended"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/install_unattended.html"
last_updated: "11/18/2025"
product_version: "7.0.0.47"
---


In this article

You can install and uninstall Veeam Plug-in for Google Cloud in the unattended mode using the command line interface. The unattended installation mode does not require user interaction — the installation runs automatically in the background, and you do not have to respond to the installation wizard prompts. You can use the unattended installation mode to automate the Veeam Plug-in for Google Cloud installation process in large-scale environments.

To install Veeam Plug-in for Google Cloud in the unattended mode, use either of the following options:

* If Veeam Plug-in for Google Cloud is a part of Veeam Backup & Replication installation package, follow the instructions provided in the Veeam Backup & Replication User Guide, section [Installing Veeam Backup & Replication in Unattended Mode](https://helpcenter.veeam.com/docs/vbr/userguide/silent_mode_vbr.html?ver=13).
* If Veeam Plug-in for Google Cloud is delivered as a separate .EXE file, follow the instructions provided in this section.

Before You Begin

Before you start unattended installation, do the following:

1. Download the Veeam Plug-in for Google Cloud .EXE file as described in section [Installing Plug-In](deploying_plugin.md) (steps 1–4).
2. Check compatibility of the Veeam Plug-in for Google Cloud and Veeam Backup & Replication versions. For more information, see [System Requirements](system_requirements.md).

Installation Command-Line Syntax

Open the command prompt and run the .EXE file using the following parameters:

|  |
| --- |
| %path% /silent /accepteula /acceptlicensingpolicy /acceptthirdpartylicenses /acceptrequiredsoftware [/uninstall] |

The following command-line parameters are used to run the setup file:

| Parameter | Required | Description |
| --- | --- | --- |
| %path% | Yes | Specifies a path to the installation .EXE file on the backup server or in a network shared folder. |
| /silent | Yes | Sets the user interface level to None, which means no user interaction is needed during installation. |
| /accepteula | Yes | Confirms that you accept the terms of the Veeam license agreement. |
| /acceptlicensingpolicy | Yes | Confirms that you accept the Veeam licensing policy. |
| /acceptthirdpartylicenses | Yes | Confirms that you accept the license agreement for 3rd party components that Veeam incorporates. |
| /acceptrequiredsoftware | Yes | Confirms that you accept the license agreements for each required software that Veeam will install. |
| /uninstall | No | Uninstalls the plug-in.  Example: ”GCPPlugin\_12.6.1.10.exe /silent /accepteula /acceptthirdpartylicenses /uninstall” |
| /repair | No | Replaces missing files and firewall rules.  Example: ”GCPPlugin\_12.6.1.10.exe /silent /accepteula /acceptthirdpartylicenses /repair” |

Page updated 11/18/2025

Page content applies to build 7.0.0.47
