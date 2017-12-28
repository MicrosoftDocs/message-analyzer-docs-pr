---
title: "Managing Microsoft OPN Parser Packages | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 667ae82e-ea7f-4916-84cb-38e2bdd48231
caps.latest.revision: 37
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Managing Microsoft OPN Parser Packages

By default, every Message Analyzer installation is provided with a baseline set of **OPN Parsers** that enable the PEF Runtime to decode messages that are captured by various Message Analyzer providers. These **OPN Parsers** are automatically copied to default locations during Message Analyzer installation. Thereafter, they are accessed by the PEF Runtime when parsers are required for decoding captured messages.  
  
## Downloading and Updating OPN Parsers  

 Message Analyzer enables you to download **OPN Parser** updates from a Microsoft web service that drives the **Message Analyzer** feed on the **Downloads** tab of the Message Analyzer **Asset Manager**. The **OPN Parsers** are listed on this tab and the **Settings** tab, from where you can manage your downloads with interactive status icons. As indicated earlier, the default behavior is to copy **OPN Parsers** to specific directory locations during Message Analyzer installation, but the default behavior does not automatically synchronize them for updates. In this state, all **OPN Parser** packages display server download icons that you can click for download options, either from the **Downloads** or **Settings** tab of the **Asset Manager**. To automatically synchronize for updates, you must set the *auto-sync* download option, which changes the **OPN Parser** download status; or you can elect to perform a single download without syncing for future updates.  
  
> [!TIP]
>  You might want to perform a download after you install or upgrade Message Analyzer to ensure that you have the latest parser versions.  
  
 You can manage **OPN Parser** downloads and updates by selecting different options in the **Item Download Options** dialog, which displays when you click the server download status icon for an **OPN Parser** package. The options that you can select in this dialog along with the different actions that they invoke are described as follows:  
  
-   **Automatically sync item updates when available** — by selecting this option for a particular **OPN Parser** package, the latest version of that package is downloaded from the **Message Analyzer** feed so that you can use the latest parsers contained in the package for decoding messages that you capture with Message Analyzer. In addition, the **OPN Parser** package is configured for auto-synced updates, so that you automatically receive the latest parser versions as they become available in the future. Auto-syncing ensures that a selected parser package is always current and that Message Analyzer can parse messages from protocols that have undergone revisions to date. After an **OPN Parser** package is auto-synced, it is removed from the **Downloads** tab because it is automatically synchronized for future updates, and its status icon displays on the **Settings** tab as a grey button that contains circular arrows, to indicate the auto-synced state.  
  
-   **Download once and don’t automatically update** — by selecting this option for an **OPN Parser** package, you opt out of the update process for the package. When this occurs, the current version of the package is downloaded from the **Message Analyzer** feed, but the package is not configured to auto-sync with the latest versions and download updates automatically. The **OPN Parser** package remains on the **Downloads** and **Settings** tabs and continues to display the server download status icon. However, you still have the option to auto-sync the package by clicking the server download status icon for the package on the **Downloads** tab to display the **Item Download Options** dialog, from where you can select the auto-sync option, even if you already downloaded the package once.  
  
 Other capabilities that you can employ when managing **OPN Parser** packages include the following:  
  
-   **Auto-sync all items** — by clicking the **Sync All Displayed Items** button on the **Downloads** tab of the **Asset Manager**, all **OPN Parser** packages are removed from the **Downloads** tab and appear on the **Settings** tab under the **OPN Parsers** list in the auto-synced state.  
  
-   **Reinstall or uninstall any OPN Parser package** — by clicking the appropriate icons on the **Settings** tab, such as the **Reinstall this OPN package** or **Uninstall this OPN package** icon, you can reinstall any **OPN Parser** package or uninstall one, respectively. Even if you temporarily uninstall an **OPN Parser** package, the feed and update design ensures that you can never lose an **OPN Parser** package and that you can always have access to the latest parser updates.  
  
-   **Work offline** — when you toggle the **Online** button on the **Downloads** page to the **Offline** state, you essentially prevent **OPN Parser** updates from being pushed out to your Message Analyzer installation from the web service. Going into the **Offline** state has no effect on your current **OPN Parser** download status, such that any auto-sync configuration that you previously set will automatically resume after you return to the **Online** state.  
  
## OPN Parser Groupings and Dependencies  

 The **OPN Parsers** are grouped into packages which contain components that relate to specific areas of functionality, such as applications, devices, communications, support, and so on. For example, the **Core Networking** package contains parsers for public network protocols and the **Microsoft Remote Desktop** package contains parsers for remote desktop application communications and management. In addition, some **OPN Parser** packages have dependencies on other **OPN Parser** packages, which means, for example, that syncing, downloading, or reinstalling one package will include any dependent packages as well. The dependencies between **OPN Parser** packages are automatically managed by Message Analyzer, such that the following occurs:  
  
-   When you download an **OPN Parser** package that depends on another **OPN Parser** package, it is automatically downloaded with the dependency package included.  
  
-   When you uninstall an **OPN Parser** package upon which other **OPN Parser** packages depend, you are prompted to also uninstall the dependent **OPN Parser** packages.  
  
-   When an **OPN Parser** package is set for auto-syncing updates, any **OPN Parser** packages upon which the synced package depends will be included in the updates.  
  
## OPN Parser Package Descriptions  

 The following table identifies and describes the baseline **OPN Parser** packages that are provided with Message Analyzer:  
  
### Table 28. OPN Parser Packages and Dependencies  
  
|Name|Description|Dependency|  
|----------|-----------------|----------------|  
|**Azure Storage Parsers Version 1.0**|Contains parsers for both Azure Storage Analytics and client-side logs from Azure Storage Client Libraries|Core Networking|  
|**Core Networking Version 1.4**|Contains parsers for public network protocols, upon which many other parsers depend. This is the basic foundation for protocol parsing functionality. Removing this group will prevent parsing of other major protocols.|Infrastructure|  
|**Device and Log File Version 1.4**|Contains parsers for device traffic and text log files. Enable parsing of textlogs such as Cluster, IIS, Lync, Netlogon, SambaSysLogs, ULS, VMM, and so on.|None|  
|**Exchange ActiveSync Parsers Version 1.2**|Contains parsers for Microsoft Exchange ActiveSync.|Microsoft Common, Core Networking, Infrastructure|  
|**Exchange MAPI Parsers Version 1.3**|Contains parsers for Microsoft Exchange MAPI services.|Microsoft Common, Core Networking, Infrastructure|  
|**Exchange Web Services Parsers Version 1.2**|Contains parsers for Microsoft Exchange Web Services protocols|Core Networking, Infrastructure|  
|**FSSHTTP and WOPI Parsers Version 1.2.1**|Contains parsers for the FSSHTTP and WOPI protocols.|Microsoft Common, Core Networking, Infrastructure|  
|**Infrastructure Version 1.4.1**|Contains infrastructure components that provide support functions, enumerations, and types for all other parsers and modules. This group does not contain actual parsers, but rather provides the basic foundation for protocol parsing. Removing this group may cause parsing functionality to fail.|None|  
|**Microsoft Common Version 1.4.1**|Contains parsers for common Microsoft and public protocols, upon which many other Microsoft protocols depend.|Core Networking, Infrastructure|  
|**Microsoft File Sharing Version 1.4.1**|Contains parsers for Microsoft Windows file sharing and branch cache protocols.|Microsoft Common, Core Networking, Infrastructure|  
|**Microsoft Identity and Security Version 1.4**|Contains parsers for Microsoft Windows identity, authentication, authorization, and security protocols.|Microsoft Common, Core Networking, Infrastructure|  
|**Microsoft Others Version 1.4**|Contains parsers for other, less common Microsoft protocols, to support special requirements.|Microsoft Common, Core Networking, Infrastructure|  
|**Microsoft Remote Desktop Version 1.4**|Contains parsers for Microsoft Windows Remote Desktop communication and management protocols.|Microsoft Common, Core Networking, Infrastructure|  
|**Microsoft SMB2 Scenario Validation Version 1.4**|Contains parsers that provide protocol scenario validation for SMB2 Negotiate, SessionSetup, TreeConnect, Logoff, and TreeDisconnect. Protocol scenario validation will check if the network traces violate defined message or field value ranges in protocol technical documents and report errors/warnings.|Microsoft Common, Core Networking, Infrastructure, File Sharing|  
|**Office and SharePoint Parsers Version 1.2**|Contains parsers for the Microsoft Office and SharePoint protocols.|Microsoft Common, Core Networking, Infrastructure|  
|**Public Version 1.4.1**|Contains parsers for public protocols that are not included in the Core Networking or Microsoft Common packages.|Microsoft Common, Core Networking, Infrastructure|  
|**Skype for Business Parsers Version 1.3**|Contains parsers for Microsoft Skype services.|Core Networking, Public, Infrastructure|  
  
## See Also  

- [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md)   
- [Asset Manager](asset-manager.md)