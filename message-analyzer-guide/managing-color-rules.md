---
title: "Managing Color Rules | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 688a2405-c7c8-4d7c-a602-3e65c83dd3b5
caps.latest.revision: 39
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing Color Rules
Message Analyzer enables you to share your local **Message Analyzer Color Rules** asset collection Library items with others, either by employing a user-configured feed or by sharing asset collection items directly with other users on a designated file share. You can share your entire Library as a set, or you can create a subset that includes specific **Color Rules** while excluding others. You can also modify the filtering and decoration scheme for **Color Rules** that you will export and share with others; however, keep in mind that any edits you make to custom **Color Rules** that you intend to export, will modify the corresponding local asset collection Library items. You can view the **Color Rule** items that are available in your local asset collection Library by clicking the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar.  
  
 To create a **Color Rule** export configuration, you must select the **Manage Color Rules** item from the **Color Rules** drop-down list on the previously indicated toolbar to display the **Manage Color Rules** dialog. Note that you can use the **Manage Color Rules** dialog to export and import **Color Rules** directly to and from a user-designated location, respectively, without employing a user-configured feed in the Message Analyzer Sharing Infrastructure.  
  
## Managing Color Rule Items  
 The **Manage Color Rules** dialog provides the following UI elements to enable you to share **Color Rules** with others:  
  
-   **Import** — enables you to navigate to a location designated by a user or team that previously posted a **Color Rule** asset collection, so that you can retrieve it and add the **Color Rules** it contains to your local **Library**.  
  
    > [!CAUTION]
    >  You should not use the **Import** feature to retrieve **Color Rule** items from a file share that is configured as a feed in the Message Analyzer Sharing Infrastructure. If you use the **Import** feature to retrieve **Color Rule** items from such a user file share, all rules that you select in the **Select Items to Import** dialog will be *added to* your local Library, while any items that have an identical name will not be overwritten, resulting in duplicate rules in your local Library. For **Color Rule** downloads or updates through the Message Analyzer Sharing Infrastructure, you should always click the status icon on the **Downloads** tab of the **Asset Manager** dialog to obtain the download or update options for the **Message Analyzer Color Rules** or **Azure Storage Color Rules** asset collections. For more information about downloading asset collections, see [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md). For a procedure that provides an example of importing Library items, see [Share Local Library Items on a File Share](procedures-using-the-asset-management-features.md#BKMK_ShareLibraryItems).  
  
-   **Export** — you can use this feature to post a set of **Color Rules** to a designated file share that you intend to configure as a feed in the Message Analyzer Sharing Infrastructure. However, you can also use this feature to post a **Color Rule** asset collection to a file share that is not configured as a user feed in the Message Analyzer Sharing Infrastructure. Note that if you use the **Export** feature to publish *updates* to a **Color Rule** asset collection on a user feed, some manual configuration is necessary for this to be successful, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
-   **Delete** — enables you to remove any **Color Rule** in the **My Items** **Category** of your local **Color Rules** asset collection Library.  
  
     Note that you cannot delete any of the predefined **Color Rules** in your local Library, although you can **Create a Copy** to save in the **My Items**  **Category**. However, to ensure that you do not lose any of your custom-created **Color Rules**, you should save a backup to a designated location so that you can always reimport your rule set as necessary.  
  
-   **Rule selection** — enables you to specify the **Color Rules** that you want to include in your export configuration by selecting check box nodes, as follows:  
  
    -   **My Items** — includes all **Color Rules** under the **My Items** node in the export configuration.  
  
    -   **Message Analyzer** — includes all **Color Rules** in each **Category** node under **Message Analyzer** in the export configuration.  
  
    -   **Category** — includes all the **Color Rules** of a specified **Category**, for example, under the **Network** node, in the export configuration.  
  
    -   **Color Rules** — includes one or more selected **Color Rules** in your export configuration.  
  
-   **Context menu** — the context menu that displays when you right-click a **Color Rule** in the **My Items** category contains the following items:  
  
    -   **Edit** — displays the **Edit Color Rule** dialog, from where you can modify any **Color Rule** under the **My Items** node only. If you modify the **Color Rule** configuration or **Category** placement from this location, the changes will apply to your local asset collection Library after you click **Save** in the **Edit Color Rule** dialog.  
  
    -   **Create a Copy** — displays the **Edit Color Rule** dialog, from where you can copy an existing **Color Rule**, for example, into a different **Category** in your local asset collection Library. After you make a copy of an existing **Color Rule**, you can reconfigure it as required and move it to a new or existing category under **My Items**; thereafter, your local Library will reflect the changes that you specified.  
  
    -   **Delete** — removes a single item from your local asset collection **Library** that you select under the **My Items** node.  
  
        > [!IMPORTANT]
        >  The right-click **Delete** command removes a single selected item from your local asset collection Library under the **My Items** node only. You can also perform a **Delete** operation from the **Manage Color Rules** dialog by clicking the **Delete** button on the dialog toolbar after selecting one or more **Color Rules**. If you attempt to **Delete** any of the predefined **Color Rules** from this location, you will be prompted for a deletion of all **Color Rules** in the **My Items** category.  
  
> [!NOTE]
>  When you open the **Edit Color Rules** dialog from the **Manage Color Rules** dialog, by right-clicking a **Color Rule** and selecting either the **Edit** or **Create a Copy** command from the context menu, you will be using the same dialog that displays when you select the **New Color Rule** item in the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar. The only difference is that when you select the **Edit** or **Create a Copy** command as indicated, you can only *revise* the **Color Rule** configurations, rather than create any new rules. Please note that any modifications you make to a **Color Rule** from the **Edit Color Rule** dialog—when accessing such dialog from the **Manage Color Rules** dialog—including deleting it, changing the decoration scheme, or modifying the **Category**, **Name**, filtering criteria, and so on, will be reflected in your local Library.  
  
## Updating the Color Rules Asset Collection  
 Microsoft provides a default **Message Analyzer** feed on the **Downloads** tab of the **Asset Manager** dialog that enables you to download **Message Analyzer Color Rules** or **Azure Storage Color Rules** asset collections from a Microsoft web service and to synchronize with asset collection updates that are periodically pushed out by the service. At any time, you can perform a download of an auto-synced collection from the **Settings** tab of the **Asset Manager** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about the common **Manage** ***\<AssetType>*** dialog, see [Managing User Libraries](managing-user-libraries.md).   
---  
  
## See Also  
 [Creating and Modifying Color Rules](creating-and-modifying-color-rules.md)   
 [Downloading Assets and Auto-Syncing Updates](downloading-assets-and-auto-syncing-updates.md)