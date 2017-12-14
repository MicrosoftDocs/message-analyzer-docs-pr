---
title: "User Libraries | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 100e89b2-fc27-4db1-8b77-eeb73c1d5e1e
caps.latest.revision: 40
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# User Libraries
Message Analyzer provides default asset collections that appear in various user Libraries in the user interface, as described in [User Library Locations](user-libraries.md#BKMK_UserLibraryLocations). From these user Libraries, you can select and apply the built-in functionality of default items to a displayed set of messages, or in the case of **Trace Scenarios**, select and apply predefined trace template functionality to capture specific data in a live trace. Moreover, you might apply a built-in view  **Filter** item to trace results by selecting one from the **Library** on the default Filter panel of the Filtering toolbar. You can also expand any user Library, with the exception of the **Viewpoints** and **Parsing Level** libraries, by creating and adding your own items to it, which then appear in the **My Items** category of the associated Library. Thereafter, you can select and apply any of your own items just as you would one of the default items.  
  
## User Library Configuration  
 Message Analyzer enables you to **Edit**, **Delete**, set as **Favorite**, or **Create a Copy** of any item in the **My Items** category of a user Library. For items in the default **Message Analyzer** category of any user Library, you can only set the **Favorite** status or **Create a Copy** of an item.  
  
 For example, you can modify a **Color Rule**, view **Filter**, or **Pattern Expression** in the **My Items** category by right-clicking it and selecting the **Edit** command from the context menu that appears, which thereafter displays the **Edit Item** dialog that contains the configuration features you will need to modify item functionality. Note that you can also make a copy of any item in the **Message Analyzer** category of a default asset collection such as the **Color Rule**, view **Filter**, or **Pattern Expression** collection, modify it, and then save it under a new name and category, which is tantamount to creating a new item. However, although you cannot delete any of the default items from a user Library, you can delete any item in the **My Items** category of any user Library. In the case of the default asset collections such as **View Layouts**, **Trace Scenarios**, **Chart** viewer **Layouts**, and so on, modifications are limited to changing the **Name**, **Description**, and **Category** when you use the **Create a Copy** command (from the context menu that displays when you right-click a default item).  
  
 In addition, most user **Libraries** have an **Examples** subcategory under **My Items** that contains a sample that you can build upon as practice in developing your own Library items, in which you are encouraged to engage. For further details about the operations you can perform on items in each user Library, see the table in [Managing User Libraries](managing-user-libraries.md).  
  
## User Library and Sharing Infrastructure Integration  
 All user **Libraries** are integrated with the Message Analyzer Sharing Infrastructure and have corresponding asset collections that display in the **Asset Manager** dialog. From the **Asset Manager** dialog, you can refresh any user Library you wish by downloading an asset collection that corresponds to the particular Library, or by setting that collection to auto-sync updates, as described in the [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md) section. You can also interact with the Sharing Infrastructure from the **Manage** ***\<AssetType>*** dialog of any user Library only to the extent of posting and retrieving items to and from a user-configured subscriber feed, respectively. This dialog is accessible from a **Manage** ***\<AssetType>*** menu item in each Library drop-down list, as described in [Managing User Libraries](managing-user-libraries.md), with the exception of the **Parsing Level** Library, which does not have this menu item. From the **Manage** ***\<AssetType>*** dialog, you can **Export** any item in a Library to a file share or other location so that you can share it with others. You can also **Import** items that other users have shared to a designated location. The dialog also enables you to select which items you want to **Export** or **Import** from and to your Library and you can **Delete** items from the dialog in the **My Items** category only.  
  
## User Library Categorical Structure  
 By default, most asset collection **Libraries** contain the following top-level categories of items.  
  
> [!NOTE]
>  Some Message Analyzer asset collections have no categories all, such as the **Message Analyzer Window Layouts** and **Message Analyzer Parsing Levels** collections. These assets appear as simple lists in the Message Analyzer user interface.  
  
-   **Favorites** — this category is generated when you configure any asset as a Favorite, by clicking the white star next to the asset name in the drop-down list of a particular Library. There must be at least one Favorited item for this category to exist.  
  
-   **Message Analyzer** — this category corresponds to the default **Message Analyzer** subscriber feed and contains a default asset collection for each particular user Library type. This is the category that is refreshed with periodic updates when you set corresponding asset collections to the auto-sync state from the **Asset Manager**. The **Message Analyzer** category in each Library exists by default and persists while you are auto-syncing. However, if you download an asset collection, rather than auto-sync it, all the items in the collection are moved into the **My Items** category of the Library. If you choose at some point to auto-sync the asset collection again, the **Message Analyzer** category will be restored in the Library to hold the asset collection items until such time that you perform a download once more.  
  
-   **My Items** — this category contains an **Example** subcategory that provides a sample item for development practice. However, as indicated earlier, this category is also the repository for asset collections that you download. Note that once you download an asset collection, the only way you can remove it from the **My Items** category is by using the **Manage** ***\<AssetType>*** dialog to **Delete** it.  
  
    -   **Examples** — a **My Items** subcategory that provides a sample asset that you can work with. The sample asset is available for you to modify however you want, and is meant to help you get started with developing your own assets. After you modify the sample, you can save it to an existing category or another one that you define.  
  
<a name="BKMK_UserLibraryLocations"></a>   
## User Library Locations  
 Each default asset collection is included in a unique user Library in the Message Analyzer locations listed below. The formal Library names in the lists that follow are as specified in the **Asset Manager** dialog. Note that although the Library accessibility points for **Session Filters**, view **Filters**, and **Viewpoint Filters** are different, it is the same centralized Filter Expression **Library** that you access in each case:  
  
-   **Global Message Analyzer toolbar** — the following user Libraries are accessible from the global Message Analyzer toolbar:  
  
    -   **Message Analyzer Chart View Layouts** Library — **Chart** viewer **Layouts** are accessible from the **New Viewer** drop-down list on the above indicated toolbar.  
  
    -   **Message Analyzer  Charts** Library — accessible from the **Charts (Deprecated)** menu in the **New Viewer** drop-down list on the specified toolbar.  
  
    -   **Message Analyzer View Layouts** Library — **Analysis Grid** viewer **Layouts** are accessible from the **New Viewer** drop-down list on the specified toolbar.  
  
    -   **Message Analyzer Window Layouts** Library — a non-categorical library that is accessible from the **Window Layout** drop-down list on the above specified toolbar.  
  
    -   **Message Analyzer Grouping View Layouts** Library — **Grouping** viewer **Layouts** are accessible from the **New Viewer** drop-down list on the specified toolbar.  
  
    -   **Aliases** Library — accessible from the **Aliases** drop-down list on the specified toolbar, although this is not an asset collection that you can auto-sync or download, as currently it does not appear in the **Asset Manager** dialog.  
  
-   **Filtering toolbar** — the following user Libraries are accessible from the Message Analyzer Filtering toolbar that displays above the main analysis surface:  
  
    -   **Message Analyzer Filters** Library — accessible from the **Library** drop-down list in any Filter panel on the Filtering toolbar. Also accessible from the **Library** drop-down list on a **Viewpoint** Filter panel, but only after you apply a **Viewpoint**.  
  
    -   **Message Analyzer Viewpoints** Library — accessible by clicking the **Viewpoint** drop-down list on the Filtering toolbar.  
  
-   **Analysis Grid** toolbar — the following user Libraries are accessible from the **Analysis Grid** viewer toolbar:  
  
    -   **Message Analyzer Color Rules** Library — accessible from the **Color Rules** drop-down list on the above indicated toolbar.  
  
    -   **Message Analyzer View Layouts** Library — accessible from the **Layout** drop-down list on the above indicated toolbar.  
  
-   **Grouping** viewer toolbar — the following user Libraries are accessible from the **Grouping** viewer toolbar:  
  
    -   **Message Analyzer Grouping View Layouts** Library — accessible from the **Layout** drop-down list on the above indicated toolbar.  
  
    -   **Message Analyzer Filters** Library — accessible from the **Library** drop-down list in any Filter panel that displays on the **Grouping** viewer toolbar when you click the **Add Filter** item in the **Add Filter** drop-down list. Also accessible from the **Library** drop-down list in any **Viewpoint** Filter panel on the **Grouping** viewer toolbar, but only after applying a **Viewpoint** from the **Grouping** viewer toolbar.  
  
    -   **Message Analyzer Viewpoints** Library — accessible by clicking the **Viewpoint** drop-down list on the **Grouping** viewer toolbar.  
  
-   **Pattern Match** viewer — the **Message Analyzer Sequence (Pattern) Expressions** user Library is accessible from the **AVAILABLE PATTERNS** list in the **Pattern Match** viewer.  
  
-   **Global Message Analyzer Tools** menu — the following user Libraries are accessible from the **Tools** menu:  
  
    -   **Aliases** Library — accessible from the **Aliases** drop-down list, although this is not an asset collection that you can auto-sync or download, as currently it does not appear in the **Asset Manager** dialog.  
  
    -   **Message Analyzer Correlations** — accessible by clicking the **Unions** drop-down list in the global Message Analyzer **Tools** menu.  
  
    -   **Message Analyzer Window Layouts** Library — a non-categorical library that is accessible from the **Window Layout** drop-down list in the **Windows** submenu that appears in the global Message Analyzer **Tools** menu. However, this is not an asset collection that you can manage with the **Manage** ***\<AssetType>*** dialog.  
  
-   **Session configuration** — the following user Libraries are accessible from the **New Session** dialog:  
  
    -   **Message Analyzer Trace Scenarios** — accessible by clicking the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog during session configuration.  
  
    -   **Message Analyzer Filters** — accessible by clicking the **Library** drop-down list above the **Session Filter** text box of the **New Session** dialog during session configuration. This is the same centralized **Library** for all Filter Expressions that is also shared by the **Filter** Library in all Filter panels on the Filtering toolbar.  
  
    -   **Message Analyzer Parsing Levels** — a non-categorical library that is accessible from the **Parsing Level** drop-down list in the **New Session** dialog, although this is not an asset collection that you can manage with the **Manage** ***\<AssetType>*** dialog.  
  
## See Also  
 [Managing User Libraries](managing-user-libraries.md)