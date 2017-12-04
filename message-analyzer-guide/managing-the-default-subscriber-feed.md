---
title: "Managing the Default Subscriber Feed | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 166413f3-419f-4a71-9a87-945222af5681
caps.latest.revision: 21
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing the Default Subscriber Feed
Message Analyzer has a default **Message Analyzer** subscriber feed that connects to a Microsoft web service, which provides asset collections and **OPN Parser** packages to your Message Analyzer installation. These collections and packages will be periodically updated over time as useful data manipulation, display, or tracing functionality and additional message parsers are developed at Microsoft for the community of Message Analyzer users. You have the option to auto-sync one or more asset collections or parser packages for updates and you can choose to perform a download of a particular collection or package. You can view these asset collections and parser packages in the **Asset Manager** dialog, synchronize with Microsoft updates, and download any of these items as needed.  
  
## Download and Update Processes  
 Downloads occur automatically for any asset collection or **OPN Parser** package that is set to the auto-sync state. An automatic asset collection download will update the **Message Analyzer** category items in the corresponding local user Library. An automatic **OPN Parser** download will update the local compilation cache that contains all message parsers.  
  
 Automatic downloads from the default **Message Analyzer** subscriber feed can occur only when the **Online**/**Offline** button is toggled to the **Online** mode. However, you can perform manual downloads even if the **Offline** mode is set. If you opted out of automatic updates when you started Message Analyzer for the first time, the asset collections and **OPN Parser** packages that are available for download are listed on the **Downloads** tab under the default **Message Analyzer** subscriber feed. From here, you can perform a download of current versions while the selected asset collections and/or **OPN Parser** packages remain in the un-synced state, or you can set any asset collection or **OPN Parser** package to auto-sync to receive automatic updates as they become available. Any collection or package that you set for auto-syncing updates is removed from the **Downloads** tab and appears on the **Settings** tab. This is also the case if you opted in for asset collection updates when you started Message Analyzer for the first time.  
  
## Feed Management Options  
 From the **Settings** tab, you can manage the default **Message Analyzer** subscriber feed, in addition to any custom feeds that you create. The options that are available for managing the default **Message Analyzer** feed consist of deleting and restoring it.  
  
## Deleting the Default Message Analyzer Feed  
 When you delete this feed, you are un-subscribing from it. During normal Message Analyzer operations, there is no reason why you should ever have to delete the **Message Analyzer** feed. However, if you do attempt to delete it by clicking the **X** to the right of the feed name, you are prompted that all auto-synced asset collections will be removed from your local Libraries, but that you can avoid such removal by clicking the auto-sync status icon of auto-synced collections and then importing the asset collection items into your local user Libraries. If you proceed with the deletion, all items in the **Message Analyzer** category of corresponding asset collection Libraries are removed. However, you can restore all items in this category for all your asset collection Libraries, restore all **OPN Parser** packages, and repopulate the collection and package lists on the **Asset Manager** dialog, by configuring a new feed from the **Settings** tab that points to the Microsoft web service.  
  
## Restoring the Default Message Analyzer Feed  
 To restore the **Message Analyzer** subscriber feed, click the **Add New Feed** button to display the **Add Feed Location** dialog. In the **Feed Name** text box, enter the text “Message Analyzer”. In the **Location** text box, enter the URL of the default **Message Analyzer** feed as “http://go.microsoft.com/fwlink/?LinkID=401500”. After you click **Add** to exit the dialog, all of the default asset collections and **OPN Parser** packages display on the **Downloads** tab under the default **Message Analyzer** feed with the server download status icon displaying to the right of each asset collection and parser package.  
  
 To restore all collections at once to the **Message Analyzer** category of your local user Libraries, click the **Sync All Displayed Items** on the **Downloads** tab.  
  
> [!NOTE]
>  This action will also set all displayed **OPN Parser** packages to the auto-sync state. If there are any updates to **OPN Parser** packages after the default **Message Analyzer** feed is restored, all parser packages that are set to auto-sync will be automatically downloaded to your Message Analyzer installation when they are available.  
  
 To restore specific asset collections to the **Message Analyzer** category of your local user Libraries, click the server download status icon of selected asset collections and then select the **Automatically sync item updates when available** option in the **Item Download Options** dialog. If you select the **Download once and don’t automatically update** option and click **OK** to exit the dialog, the **Select Items to Import** dialog displays, from where you can select the items you want to import to the associated Library and the category in which to place them. In this case, the asset collections will not be set for auto-sync and therefore will not be periodically and automatically updated.  
  
## Other Capabilities  
 Other management features for the default **Message Analyzer** subscriber feed enable you to do the following:  
  
-   Disable feed connections by toggling the **Online/Offline** button to the **Offline** mode. This action will block any update processes occurring in the background. This could be useful if you want to freeze your asset collection and/or **OPN Parser** package version configurations for consistency during protracted tracing and data analysis operations.  
  
-   Use the search box and/or filtering drop-down to locate specific items in the feed list on the **Downloads** tab, as described in [Filtering and Searching For Items](filtering-and-searching-for-items.md).  
  
## See Also  
 [Asset Manager](asset-manager.md)