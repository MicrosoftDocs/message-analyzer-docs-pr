---
title: "Downloading Assets and Auto-Syncing Updates | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 35393b3f-bee9-412b-a364-d0ee7f8873d1
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Downloading Assets and Auto-Syncing Updates

This section describes how to download the default asset collections and **OPN Parser** packages and how to configure them to automatically receive updates that are pushed out by a Microsoft web service. The manner in which you proceed in these tasks depends upon the update option you choose in the **Welcome to Microsoft Message Analyzer** dialog when you start Message Analyzer for the first time. If you opt-out of receiving updates by selecting the **Do not update items** option in the dialog, the latest version of the default asset collections for Message Analyzer are downloaded to your local user Libraries and none of the asset collections or parser packages are auto-synced to receive web service updates.  
  
 However, if you opt-in to receive updates by selecting the **Update items** option in the dialog, the latest version of the default asset collections are downloaded to your local user Libraries and all asset collections (and **OPN Parser** packages) are set to the auto-sync status so that your Message Analyzer installation can automatically receive the latest asset collection and parser package versions through the Microsoft web service, as they become available. The content that follows describes how to proceed with downloading asset collections and subscribing to automatic asset collection updates when you select either of the indicated startup options.  
  
## Opting Out of Automatic Updates  

 If you opted out of auto-synced updates for the default asset collections at first Message Analyzer startup, all asset collections and parser packages are initially downloaded and display on the **Downloads** tab of the **Asset Manager** dialog, with the server download status icon displayed to the right of each collection or package to indicate its un-synced state. In addition, the **Online**/**Offline** button is automatically set to the **Offline** mode to disable all collection updates. However, you still have the option to auto-sync any asset collection or parser package and perform downloads any time after first Message Analyzer startup. For example, even if you have not set an asset collection or parser package for auto-syncing updates, you can still perform a manual download of that collection or package to ensure you have the latest version; however, you cannot manually download again until you set the asset collection or parser package to the auto-sync state.  
  
 **Auto-Syncing Asset Collections and OPN Parser Packages After Opt-out**   
After opting out of automatic updates, you can acquire the auto-sync state for asset collections and parser packages at any time. If you want to auto-sync these entities, do either of the following:  
  
-   **Auto-sync all asset collections and parser packages simultaneously** — click the **Sync All Displayed Items** button on the **Downloads** tab of the **Asset Manager**. This action configures all of the default asset collections and parser packages to automatically receive updates through the Microsoft web service as they become available. Also, all collections and packages are moved to the **Settings** tab of the **Asset Manager**, where the auto-synced status icon displays to the right of each collection or package. When an auto-sync update occurs, the corresponding update items in the **Message Analyzer** category of the appropriate local user asset collection Library or items in some **OPN Parser** package are refreshed to the latest version.  
  
-   **Auto-sync specific asset collections or OPN parser packages** — to manually set collections or packages for auto-syncing, click the server download status icon on the **Downloads** tab for a chosen collection or package to display the **Item Download Options** dialog, from where you can select the **Automatically sync item updates when available** option. After you select this option and click **OK** to exit the dialog, the following occurs:  
  
    -   The chosen asset collection or **OPN Parser** package will receive periodic updates, providing that you also have the **Online** mode set in the **Asset Manager**.  
  
    -   The auto-synced asset collection or parser package is removed from the **Downloads** tab and reappears on the **Settings** tab of the **Asset Manager**, with a corresponding auto-sync status icon displaying to the right of the collection or package name and description.  
  
    -   The **Message Analyzer** category of the local Library that corresponds to the asset collection is updated with the latest collection version and the cache that contains the parsers used by Message Analyzer is also updated. Thereafter, these items will continue to be periodically updated while they are set for auto-syncing.  
  
**Downloading Asset Collections and Parser Packages After Opt-out**   
If you opted out of automatic updates at first Message Analyzer startup, you can periodically download any asset collection or parser package by selecting the **Download once and don’t automatically update** option in the **Item Download Options** dialog that displays when you click the status icon of any asset collection or parser package that is in the un-synced state. The following then occurs for the indicated entities:  
  
-   **Asset collections** — the **Select Items to Import** dialog displays, from where you can choose the items to import and the category in which to place them in the corresponding local asset collection Library. If you accept the default configuration, the asset collection items are placed in the **Examples** subcategory of the appropriate local Library. Thereafter, the chosen asset collection appears on the **Downloads** tab and the server download status icon continues to display to the right of that collection to indicate the un-synced state.  
  
-   **OPN Parser packages** — the **OPN package download** dialog displays and indicates that the package and its dependencies will no longer be downloaded and automatically installed. If you click **OK** to proceed, the parser package is removed from the **Settings** tab and appears on the **Downloads** tab in the un-synced state.  
  
> [!NOTE]
>  When you employ the *download once* option for an asset collection or **OPN Parser** package, you are simply downloading the collection and opting out of the auto-sync process. However, you have the option to set the asset collection for auto-sync anytime thereafter, or to resume auto-sync after download of a previously synced item. After you choose the download option, the current version of the asset collection or parser package is downloaded from the Microsoft web service, even if the **Offline** mode is set.  
  
## Opting In to Automatic Updates  

 If you opted in to auto-sync updates at first Message Analyzer startup, then all of the default asset collections and parser packages are moved to the **Synced Collections** list and the **OPN Parsers** list, respectively, on the **Settings** tab of the **Asset Manager**, with the auto-sync status icon displayed to the right of each asset collection or parser package to indicate the synced state. In addition, the **Message Analyzer** category of each asset collection Library is updated with the latest collection version and the OPN parser cache is updated with the latest OPN parsers. Thereafter, updates to the asset collections and parser packages will be periodically pushed out by the Microsoft web service as they become available.  
  
 At that time, the asset collection items in the **Message Analyzer** category of the appropriate local user Libraries are refreshed with the latest versions and the OPN cache is updated as well. At any time, you can choose to download specific asset collections that are currently in the auto-synced state by clicking the auto-sync status icon for the collection on the **Settings** tab. Thereafter, the **Select Items to Import** dialog displays, from where you can choose the collection items to import and the Library category in which to place them, as previously indicated.  
  
 **Working with Auto-Synced Asset Collections**   
If an asset collection is already synced and you click the auto-sync status icon for that collection on the **Settings** tab of the **Asset Manager**, the **Import Autosynced Items** dialog displays and explains that the asset collection will no longer be synced and prompts you to import the current version to your local asset collection Library. If you click the **No** button to exit this dialog, the asset collection is removed from the **Settings** tab and reappears on the **Downloads** tab in the un-synced state, as indicated by the server download status icon for that collection. The asset collection items and the **Message Analyzer** category that contains them are also removed from the corresponding local Library for that asset collection. However, if you click the **Yes** button to exit the **Import Autosynced Items** dialog, the **Select Items to Import** dialog displays and enables you to choose the items to import and the category in which to place them in the corresponding local Library for the collection, as described earlier.  
  
 **Working with Auto-Synced OPN Parser Packages**   
In the case of a parser package that is already synced, if you click the auto-sync status icon for the package on the **Settings** tab, the **OPN package update** dialog displays and indicates that the package and its dependencies will no longer be downloaded and automatically installed. If you click **OK** to proceed, the package reverts to the un-synced state, as indicated by the download status icon for the package on both the **Settings** and **Downloads** tab. Thereafter, you still have the option to reinstate the auto-synced state.  
  
---  
  
## See Also  

[User Libraries](user-libraries.md)   
[Managing User Libraries](managing-user-libraries.md)   
[Managing Microsoft OPN Parser Packages](managing-microsoft-opn-parser-packages.md)