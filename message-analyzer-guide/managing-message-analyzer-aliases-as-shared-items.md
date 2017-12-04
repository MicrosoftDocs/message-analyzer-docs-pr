---
title: "Managing Message Analyzer Aliases as Shared Items | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d657248-6f0c-4f32-816b-f15fda3fb8bc
caps.latest.revision: 24
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing Message Analyzer Aliases as Shared Items
The **Aliases** drop-down list in the global Message Analyzer **Tools** menu or on the global toolbar contains items that you can share with others. Message Analyzer provides a simple way to expose **Alias** items to others on your team for sharing purposes, or to retrieve **Alias** items that others have shared. You can manage your **Alias** assets in the **Manage Alias** dialog, from where you can **Import** or **Export** an **Alias** asset collection Library containing one or more **Aliases** that you select. Any **Alias** Library that you export is saved as a \*.asset file with a name that you specify and any **Alias** Library that you import can only be of the same type. In addition, you can store an **Alias** asset collection Library on a user-configured file share or a feed that you create in the Message Analyzer sharing infrastructure.  
  
## Exporting and Importing Alias Libraries  
 To create an **Alias** asset collection Library for export, you simply select the specific **Aliases** or categories containing one or more **Aliases** in the **Manage Alias** dialog that you want to include in the Library. After you select **Aliases** and click the **Export** button, the **Save Library** dialog displays, in which you can specify **Title**, **Description**, **Author**, and **Organization** information before you **Save** the Library in a chosen location.  
  
 To import an **Alias** Library, click the **Import** button in the **Manage Alias** dialog and navigate to the directory location where the **Alias** assets are stored. When you open the Library, you are prompted by the **Select Items to Import** dialog to choose the **Alias** items you want to import. You also have the option to specify the **Category** in which to import the Library items.  
  
## Sharing Aliases on a File Share  
 You can share **Alias** items directly with others by using the **Export** feature in the **Manage Alias** dialog to save one or more **Alias** items as a collection to a designated file share. You can also use the **Import** feature in the same dialog to access **Alias** items that have been shared by others in a similar manner.  
  
## Sharing Aliases Through a User Feed  
 You can also share your **Alias** items through a user feed that you configure in the Message Analyzer Sharing Infrastructure from the **Settings** tab in the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu. Thereafter, you can use the **Export** feature of the **Manage Alias** dialog to post your **Alias** collection items to the feed so that others can access them on the **Downloads** tab of the **Asset Manager** dialog. As the asset publisher, if you update your existing **Alias** items or add others to your collection, you can make them available to team members or other consumers through the configured feed, where they can view, synchronize with, and download your collection items. However, to enable others to synchronize with item collection *updates*, you will need to perform some manual configuration, as described in [Manual Item Update Synchronization](../messageanalyzer_content/manual-item-update-synchronization.md).  
  
## Downloading Alias Asset Collections from Microsoft  
 Microsoft also provides a default **Message Analyzer** feed on the **Downloads** tab of the **Asset Manager** dialog that will enable you to download **Alias** asset collections from a Microsoft web service in a future Message Analyzer release. When available, you will be able to synchronize with asset collection updates that are periodically pushed out by the service.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using the common **Manage** ***\<AssetType>*** dialog to share and manage your **Aliases**, see the [Managing User Libraries](../messageanalyzer_content/managing-user-libraries.md) topic.  
**To learn more** about the Sharing Infrastructure, downloading asset collections, and auto-syncing asset collection updates, see the [Sharing Infrastructure](../messageanalyzer_content/sharing-infrastructure.md) and [Managing Asset Collection Downloads and Updates](../messageanalyzer_content/managing-asset-collection-downloads-and-updates.md) topics.  
___________________\_