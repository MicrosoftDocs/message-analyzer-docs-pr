---
title: "Managing Chart Viewer Layouts | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8deb5ff-a0b4-4b4d-80ce-181d92c8bf0d
caps.latest.revision: 26
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Managing Chart Viewer Layouts

This section describes how to manage the items of your **Message Analyzer Chart View Layouts** asset collection. Also included are discussions about using the Message Analyzer Sharing Infrastructure to share **Chart** viewer **Layouts** with others and how to receive automatic updates for this collection.  
  
## Managing the Chart Viewer Layouts Library  

 To manage  the **Chart** viewer **Layouts** in the **Message Analyzer Chart View Layouts** asset collection Library, you will use commands that are available in the **Manage Chart Layout** dialog, which is accessible from the global Message Analyzer **Session** menu by selecting the **Chart**, **Layout**,  **Manage Layouts**, and **Manage** items in succession.  
  
 The **Message Analyzer Chart View Layouts** asset collection Library has a **Message Analyzer** category for the default asset collection that contains the built-in **Layouts** that are described in the [Built-In Chart Viewer Layouts](configuring-chart-viewer-layouts.md#BKMK_Charts) topic. This Library also contains a **My Items** category from where you can manage any **Layouts** of your own design that you saved. The commands that are available in this dialog are described in [Managing Chart Viewer Layout Library Items](managing-chart-viewer-layouts.md#BKMK_ManageChartLayoutItems).  
  
 All the Library collection items in both of these categories are shareable **Layout** items. Message Analyzer provides a simple way to expose your **Layouts** asset collection items to others for sharing or to retrieve **Layouts** that others have shared. You can share **Layout** collection items directly with others by using the **Export** feature in the **Manage Chart Layout** dialog to save one or more **Layout** collection items to a designated file share. You can also use the **Import** feature in the same dialog to access **Layout** collection items that have been shared by others.  
  
---  
  
 **More Information**   
 **To learn more** about managing Message Analyzer asset collections, including the **Message Analyzer Chart View Layouts** collection, see [Managing User Libraries](managing-user-libraries.md).   

---  
  
## Using the Layout Commands  

 This section briefly describes the Layout commands that you can use to manage any of the built-in **Chart** viewer **Layouts** or any new **Layout** that you have created. These commands are accessible from the **Layouts** drop-down list that appears on the Charts toolbar whenever a **Chart** viewer **Layout** is displayed. A descriptions of each command is specified in the list that follows:  
  
-   **Save Current Layout As...** — the primary command that you will use to save a newly modified **Chart** viewer **Layout** as a custom **Layout** of your own. When you click this command from the **Layout** drop-down list on the Charts toolbar, the **Edit Chart Layout** dialog displays with the **Layout** configuration and formulas that you specified, where you can provide a **Name**, **Description**, and a **Category** for your custom **Chart** viewer **Layout**.  
  
-   **Load Default User Layout** — appears in the **Manage Layouts** submenu of the **Layout** drop-down list that displays on the Charts toolbar. Enables you to load the default user **Layout** that you previously specified with the **Save Current as Default User Layout** command.  
  
-   **Restore Application Default Layout** — appears in the **Manage Layouts** submenu of the **Layout** drop-down list that displays on the Charts toolbar. Enables you to load the application default **Chart** viewer **Layout**, which consists of a bar element visualizer that displays the relative distribution of message volume for each protocol or module that was captured in a set of trace results.  
  
-   **Save Current as Default User Layout** — appears in the **Manage Layouts** submenu of the **Layout** drop-down list that displays on the Charts toolbar. Enables you to save the currently displayed **Chart** viewer **Layout** as the default, such that you can display it any time thereafter by executing the **Load Default User Layout** command.  
  
## Utilizing the Message Analyzer Sharing Infrastructure  

 You can share your **Layout** collection items through the Message Analyzer Sharing Infrastructure by using the **Export** feature of the **Manage Chart Layout** dialog to post one or more **Layouts** to a file share or other designated location that is accessed through a user-configured feed. You can create your own feed from the **Settings** tab in the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu. Thereafter, you can update existing **Layout** collection items or add others to make them available to team members or other users through the configured feed, where they can view, synchronize, and download them. However, the synchronization feature that keeps users up to date  requires some manual configuration at this time, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
 Message Analyzer also has a default subscriber feed that appears on both the **Downloads** and **Settings** tabs of the **Asset Manager** dialog. On the **Downloads** tab, the feed enables you to view the default assets provided with Message Analyzer.  On the **Settings** tab, the feed provides the path that enables the Message Analyzer application to download the **Message Analyzer Chart View Layouts** asset collection from a Microsoft web service at first Message Analyzer startup. It also enables you to receive asset collection updates that are periodically pushed out by the service, as useful **Layout** assets are developed at Microsoft for the community of Message Analyzer users. To receive updates that will appear in the **Message Analyzer** category of your local **Message Analyzer Chart View Layouts** asset collection Library, you must set this asset collection to the auto-sync state on the **Downloads** tab of the **Asset Manager**, as described in [Downloading Assets and Auto-Syncing Updates](downloading-assets-and-auto-syncing-updates.md).  
  
<a name="BKMK_ManageChartLayoutItems"></a>   
## Managing Chart Viewer Layout Library Items  
 You can manage **Layout** items in both categories of your local **Message Analyzer Chart View Layouts** Library. The following features are available to do so:  
  
-   **Item selection** — you can select **Layout** collection items to include in an export configuration by selecting all items in the **Message Analyzer** category, the **My Items** category, or both. You can also select any combination of individual collection items in these categories to include in the export.  
  
-   **Context menu commands** — the following context menu command is available by right-clicking any collection item in the **Message Analyzer** category of your local **Layouts** asset collection Library:  
  
    -   **Create a Copy** — enables you to create a copy of an existing **Layout** collection item, such as the **Average Response Times for Operations** layout, and place it in your **My Items** category. You can then launch this copied **Layout** in an Analysis Session and use the controls and features of the **Edit Chart Layout** and **Formula Editor** dialogs to edit and customize the **Layout** to your own design and then save it under a new name of your choice, as described in [Overview of Configuring a Custom Chart Viewer Layout](configuring-chart-viewer-layouts.md#BKMK_ChartConfigOverview).  
  
  The following context menu commands are available by right-clicking any collection item in the **My Items** category of your local **Layouts** asset collection Library:  
  
    -   **Edit** — enables you to save a **Layout** collection item with a new **Name**, **Description**, and **Category**.  
  
    -   **Create a Copy** — enables you to create a copy of a **Layout** collection item and use it as  a functionality template for creating a new **Layout** that will have similar components in the configuration.  
  
    -   **Delete** — enables you to delete any **Layout** collection item in the **My Items** category. When you select this command, all selected **Layout** collection items are immediately deleted without any prompt. Note that you cannot delete any Library collection items in the **Message Analyzer** category.  
  
-   **Import** — enables you to open the **Select Library to Open** dialog from where you can navigate to a **Layout** asset collection. When you exit this dialog by clicking the **Open** button, the **Select Items to Import** dialog opens, from where you can choose the **Layout** items you want to import and the category into which they will be placed. Note that you can navigate to a user-designated file share or other location from the **Select Library to Open** dialog, to import a **Layout** asset collection that another user has posted in that location.  
  
-   **Export** — enables you to open the **Save Library** dialog, from where you can specify a library **Title** along with optional **Description**, **Author**, and **Organization** information. When you exit this dialog by clicking the **Save** button, the **Select Library Location** dialog opens, from where you can navigate to a user-designated file share or other location to post your **Layout** asset collection files.  
  
---  
  
 **More Information**   
 **To learn more** about sharing Message Analyzer asset collection Library items, including further details about the common **Manage** ***\<AssetType>*** dialog, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.  
**To learn more** about the manual synchronization process for a user-configured feed, see [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
**To learn more** about auto-syncing and downloading item collections, see [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md).   

---