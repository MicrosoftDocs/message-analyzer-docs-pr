---
title: "Managing Unions as Shared Items | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e3a1f06-7430-4e1b-931e-dda57fb6c08c
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing Unions as Shared Items
The **Manage Unions** dialog contains **Union** items that you can share with others. Message Analyzer provides a simple way to expose **Union** items to others on your team for sharing purposes, or to retrieve **Union** items that others have shared. You can manage your **Union** assets in the **Manage Union** dialog, which is accessible as an item in the **Unions** drop-down list on the global Message Analyzer **Tools** menu. From this dialog, you can **Import** or **Export** a **Union** asset collection Library containing one or more **Unions** that you select. Any **Union** Library that you export is saved as a \*.asset file with a name that you specify, and any **Union** Library that you import can only be of the same type. In addition, you can store a **Union** Library on a user-configured file share or a feed that you create in the Message Analyzer sharing infrastructure.  
  
## Working with Union Libraries  
 To create a **Union** asset collection Library for export, you simply select the specific **Unions** or categories containing one or more **Unions** in the **Manage Union** dialog that you want to include in the Library. After you select **Unions** and click the **Export** button, the **Save Library** dialog displays, in which you can specify **Title**, **Description**, **Author**, and **Organization** information before you **Save** the Library in a chosen location.  
  
 To import a **Union** Library, click the **Import** button in the **Manage Union** dialog and navigate to the directory location where the **Union** asset file is stored. When you open the file, you are prompted by the **Select Items to Import** dialog to choose the **Union** items you want to import. You also have the option to specify the **Category** in which to import the Library items.  
  
 The **Manage Unions** dialog also enables you to modify any **Union** that displays in the **My Items** category of the dialog list. You can access the modification commands by right-clicking any **Union** in the dialog to display a context menu that contains the **Edit**, **Create a Copy**, and **Delete** commands. If you **Delete** a **Union** in the **My Items** category of the **Manage Unions** dialog, obviously that **Union** will not be available to include in an export Library. If you decide to **Edit** a **Union** in the **My Items** category from the dialog, or **Create a Copy** and edit the **Union** copy, and you save it, then only the edited version of the **Union** is available to include in a Library export. If a user that is running a different Message Analyzer instance imports the Library, the **Union** assets that it contains will be new entities on their computer and will take effect immediately, although it is still possible that there could be a collision with an existing **Union** name. However, any modifications that you made to a **Union** in the current Message Analyzer instance take effect only after a Message Analyzer restart.  
  
## Sharing Unions on a File Share  
 You can share **Union** items directly with others by using the **Export** feature in the **Manage Union** dialog to save one or more **Union** items to a designated file share. You can also use the **Import** feature in the same dialog to access **Union** items that have been shared by others in a similar manner.  
  
## Sharing Unions Through a User Feed  
 You can also share your **Union** items through a user feed that you configure in the Message Analyzer Sharing Infrastructure from the **Settings** tab of the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu. You can specify a feed name and location in the **Add Feed Location** dialog, which is accessible by clicking the **Add New Feed** button on the **Settings** tab. Thereafter, you can use the **Export** feature of the **Manage Union** dialog to post your Library of **Union** assets to the feed so that others can access them on the Message Analyzer **Downloads** tab of the **Asset Manager** dialog. As the asset publisher, if you update your existing **Union** items or add others to your collection, you can make them available to team members or other consumers through the configured feed, where they can view, synchronize with, and download your collection items. However, to enable others to synchronize with your item collection updates, you will need to perform some manual configuration, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
## Accessing the Union Assets Collection  
 **Unions** are contained in an asset package named **Message Analyzer Correlations** on the **Downloads** tab of the **Asset Manager** dialog. You can either auto sync the package for periodic updates that occur automatically, or you can download the package from the **Downloads** tab of the **Asset Manager**, at which time the auto-sync status is canceled. However, after you download, you still have the option to auto-sync again later to synchronize your Message Analyzer installation for future updates to this asset package.  
  
> [!IMPORTANT]
>  The **Message Analyzer Correlations** asset collection is installed by default with Message Analyzer, so it is unnecessary to download the collection whenever you start Message Analyzer. But if it is the first time you have started Message Analyzer, you are presented with a **Welcome** dialog that provides you with the choice to opt in or out of automatic updates. If you choose to opt in to auto-syncing updates, then all Message Analyzer asset collections are automatically set to the auto-sync state, including the **Message Analyzer Correlations** asset collection, and no further action is required.  
  
 However, if you opted out, you still have the option to automatically receive periodic collection updates later by setting the **Offline** mode to **Online** on the **Downloads** tab of the **Asset Manager** and clicking the **Sync All Displayed Items** button, which auto-syncs all asset collections, or you can set individual collections to the auto-sync state on the **Downloads** tab as you require them. To do this, click the download icon to the right of the collection on the **Downloads** tab and select the **Automatically sync item collection updates when available** option in the **Item Download Options** dialog.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using the common **Manage** ***\<AssetType>*** dialog to share and manage your **Unions**, see the [Managing User Libraries](managing-user-libraries.md) topic.  
**To learn more** about the Sharing Infrastructure, downloading asset collections, and auto-syncing asset collection updates, see the [Sharing Infrastructure](sharing-infrastructure.md) and [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md) topics.  
___________________\_