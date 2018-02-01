---
title: "Sharing Infrastructure | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ebfaf009-ae7b-408e-947e-86ba78f2d8d5
caps.latest.revision: 29
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Sharing Infrastructure

The Message Analyzer Sharing Infrastructure is a centralized framework that integrates specific functions of the **Asset Manager** with user **Library** asset collections in your Message Analyzer installation. Asset collections are accessible from Library drop-down lists, which contain tools that you can use to capture, filter, and manipulate the data, or change the data view, for example, with **Trace Scenario**, **Filter**, **Viewpoint**, and **Chart** viewer **Layout** Library types, respectively. In addition, a common management dialog is available so that you can manage the items in your asset collection Libraries.  
  
## Sharing Infrastructure Overview  

 Some of the specific entities that you can use to manage the Sharing Infrastructure consist of the following:  
  
-   **Asset Manager** dialog — access from the global Message Analyzer **Tools** menu and perform the following tasks:  
  
    -   View the list of default asset collections that are provided by Microsoft to all Message Analyzer installations.  
  
    -   Access and exercise the auto-syncing and downloading functions for the default Message Analyzer asset collections that are stored in user Libraries.  
  
    -   Create new data feeds for mutually sharing assets with others.  
  
    -   Search for various types of assets.  
  
-   **Manage** dialog — use a common dialog to manage the asset collections in various user Libraries that are integrated with the Sharing Infrastructure. Provides facilities for importing, exporting, and modifying asset collections from any Library with which you are working.  
  
-   **Add New Feed** feature — create your own custom user feed through which you can export or import asset collections for mutual sharing with others, including any items that you develop.  
  
-   **Export/Import** commands — share asset collections directly with other users by posting or retrieving them to/from a user-designated file share or other location.  
  
## Managing and Sharing User Libraries  

 The **Libraries** that contain your asset collections are centralized, up-dateable, user-expandable, and shareable. Managing user **Libraries** includes creating new items, organizing asset collections, and sharing them with others, as follows:  
  
-   **Manage asset collection Libraries** — you can create, reconfigure, export, import, and save asset collections to local user Libraries that are integrated with the Sharing Infrastructure, so that you, other team members, or the larger Message Analyzer community can mutually share asset collection items, including any of the default Message Analyzer items that you copy and modify. You can manage your assets from a common **Manage** ***\<AssetType>*** dialog that displays from various **Library** drop-down lists in the Message Analyzer user interface.  
  
 > [!NOTE]
 >  The **Manage** ***\<AssetType>*** dialog functionality is common across all user Libraries; however, the actual dialog name varies depending on which Library you are managing. For example, when you are managing the **Filters** Library, the dialog is named **Manage Filter**; when you are managing the **Color Rules** Library, the dialog is named **Manage Color Rule**; and so on.  
  
 From the common **Manage** ***\<AssetType>*** dialog, you can create new items that get added to the **My Items** category, copy and modify any of the built-in items in a Library, or delete any item in the **My Items** category. You can also select items for export configurations and import items from a file share, user feed, or other designated location. The asset collections that are provided with Message Analyzer by default are contained in \*.asset files, the contents of which display in the **Libraries** that are described in [User Libraries](user-libraries.md).  
  
-   **Share asset collections from a user feed** — you can configure a custom user subscriber data feed to which you can export any of the built-in Message Analyzer asset collection items or any of those that you created in the **My Items** category of a local user Library for a particular item type, so that others can import them for their own use. When you create your own feed, you must specify a **Feed Name** and a directory **Location** where you intend to export selected items or collections to make them accessible to other users.  
  
-   **Share asset collections from a file share** — you can share your asset collection Library items directly with others by using the **Export** command in the **Manage** ***\<AssetType>*** dialog for the particular Library. You simply select the items or item categories that you want to export and you are prompted to navigate to a file share or other location where you want to post the items in an asset file for sharing with others. Similarly, you can use the **Import** command to access asset collections that others have shared.  
  
The topics below provide further details about the **Asset Manager** functions, user asset collection Libraries,  and how to manage these Libraries.  
  
---  
  
## See Also  

[Asset Manager](asset-manager.md)   
[User Libraries](user-libraries.md)   
[Managing User Libraries](managing-user-libraries.md)