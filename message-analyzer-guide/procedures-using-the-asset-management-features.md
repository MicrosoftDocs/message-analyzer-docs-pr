---
title: "Procedures: Using the Asset Management Features | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50f33d9e-ff89-4fed-9204-46b2bd5e9064
caps.latest.revision: 36
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Procedures: Using the Asset Management Features
This section contains procedures that demonstrate how to use the Message Analyzer asset collection download, auto-syncing, and sharing features for tasks that you are likely to perform on a consistent basis. Also included is a procedure that shows how to manually configure an asset collection for update synchronization.  
  
 ______________________\_  
  
 **Procedure Overviews**   
A brief description of each procedure is included here for review, as follows.  
______________________\_  
  
 **[Download and Auto-Sync Asset Collections](../messageanalyzer_content/procedures-using-the-asset-management-features.md#BKMK_DownloadAutoSync)**  — provides an example of how to download an asset collection once without synchronizing it for updates; how to set a selected asset collection for auto-syncing updates; and how to synchronize all asset collections for updates.  
  
 **[Share Local Library Items on a File Share](../messageanalyzer_content/procedures-using-the-asset-management-features.md#BKMK_ShareLibraryItems)**  — provides an example of how to export and import user asset collection Library items for mutual sharing and collaboration with others.  
  
 **[Manually Configure Asset Collection Update Synchronization on a User Feed](../messageanalyzer_content/procedures-using-the-asset-management-features.md#BKMK_ManualUpdateSyncing)**  — shows how to manually configure an asset collection for update synchronization on a user-configured feed.  
  
<a name="BKMK_DownloadAutoSync"></a>   
## Download and Auto-Sync Asset Collections  
 This example demonstrates how to download default Library asset collections and how to auto-sync these collections for updates.  
  
#### To download an asset collection  
  
1.  From the **Start** menu, **Start** page, or taskbar of your computer, click the **Microsoft Message Analyzer** icon to start Message Analyzer.  
  
2.  Open the **Asset Manager** dialog by clicking the global Message Analyzer **Tools** menu and then click the **Asset Manager** menu item.  
  
3.  In the **Asset Manager** dialog, click the **Downloads** tab (if it is not already selected) to display any asset collections that are not auto-synced, as indicated by the server download status icon to the right of the asset collection you want to download.  
  
4.  Click the server download status icon for an unsynced asset collection to display the **Item Download Options** dialog.  
  
5.  In the **Item Download Options** dialog, select the **Download once and don’t automatically update** option and then click **OK** to exit the dialog and display the **Select Items to Import** dialog.  
  
6.  In the **Select Items to Import** dialog, accept the default selection of the **Use Existing Categories** check box, or optionally deselect this check box and specify the Library category in which to place asset collection items by clicking the **Add to Category** drop-down list and selecting a category.  
  
7.  In the **Select Items to Import** dialog, select the items and/or categories that contain the items you want to download.  
  
8.  Click **OK** to exit the **Select Items to Import** dialog.  
  
9. Open the local Library that corresponds to the type of asset collection you downloaded and observe that the Library is populated with the items you selected and in the category you specified.  
  
#### To auto-sync an asset collection  
  
1.  From the **Start** menu, **Start** page, or taskbar of your computer, click the **Microsoft Message Analyzer** icon to start Message Analyzer.  
  
2.  Click the **Downloads** tab in the **Asset Manager** dialog to display any asset collections that are not auto-synced, as indicated by the server download status icon to the right of a target asset collection.  
  
3.  Click the server download status icon for the asset collection that you want to auto-sync for updates, to display the **Item Download Options** dialog.  
  
4.  In the **Item Download Options** dialog, select the **Automatically sync item updates when available** option and then click **OK** to exit the dialog.  
  
     The asset collection that you auto-synced is removed from the **Downloads** tab and reappears on the **Settings** tab with the auto-sync status icon displaying to the right of the collection. The auto-synced state indicates that the asset collection in your Message Analyzer installation will be periodically and automatically refreshed with updates as they become available.  
  
5.  To auto-sync all asset collections that are currently displayed on the **Downloads** tab in the **Asset Manager**, click the **Sync All Displayed Items** button.  
  
     The asset collections that you auto-synced are removed from the **Downloads** tab and reappear on the **Settings** tab with the auto-sync status icon displaying to the right of each collection.  
  
    > [!NOTE]
    >  When you click the **Sync All Displayed Items** button on the **Downloads** tab to set all asset collections to the auto-sync state, this includes all **OPN Parser** packages.  
  
<a name="BKMK_ShareLibraryItems"></a>   
## Share Local Library Items on a File Share  
 This example shows how to export **Filter** items as an asset collection from the centralized Filter Expression **Library** to a user-configured file share or other designated location to share these items directly with other users. This example also specifies how users can retrieve the asset collections that you post to such a designated location.  
  
#### To export a Filter asset collection  
  
1.  From the **Start** menu, **Start** page, or taskbar of your computer, click the **Microsoft Message Analyzer** icon to start Message Analyzer.  
  
2.  Optionally, load a saved trace file into Message Analyzer through a Data Retrieval Session.  
  
3.  On the default Filter panel of the Filtering toolbar above the  main analysis surface of Message Analyzer, click the **Library** drop-down list to expose the asset collection Library items and management features.  
  
4.  In the **Library** drop-down list, click the **Manage Filters** item to open the **Manage Filter** dialog.  
  
5.  In the **Manage Filter** dialog, select the collection items and/or **Library** categories that contain the items you want to export for sharing by placing a check mark in the appropriate check boxes.  
  
6.  Click the **Export** button on the toolbar of the **Manage Filter** dialog to open the **Save Library** dialog.  
  
7.  In the **Save Library** dialog, enter a name for the asset collection in the **Title** text box and the collection author in the **Author** text box. Optionally, add **Description** and **Organization** information.  
  
8.  Click the **Save** button to exit the **Save Library** dialog and to display the **Select Library Location...** dialog, from where you can navigate to the file share location where you intend to post the asset collection.  
  
9. After you specify a **File name** for the asset collection, click the **Save** button to exit the **Select Library Location...** dialog, at which time your asset collection is posted to the file share location.  
  
    > [!NOTE]
    >  Ensure that users have your file share location information and appropriate permissions to access the share or other location.  
  
#### To import a Filter asset collection  
  
1.  From the **Start** menu, **Start** page, or taskbar of your computer, click the **Microsoft Message Analyzer** icon to start Message Analyzer.  
  
2.  Optionally, load a saved trace file into Message Analyzer through a Data Retrieval Session.  
  
3.  On the default Filter panel of the Filtering toolbar above the main analysis surface of Message Analyzer, click the **Library** drop-down list to expose the asset collection Library items and management features.  
  
4.  In the **Library** drop-down list, click the **Manage Filters** item to open the **Manage Filter** dialog.  
  
5.  In the **Manage Filter** dialog, click the **Import** button on the toolbar to display the **Select Library to Open...** dialog, from where you can navigate to the file share that contains the shared asset collection.  
  
6.  Select the \*.asset file that corresponds to the target asset collection and then click the **Open** button to exit the **Select Library to Open** dialog and to open the **Select Items to Import** dialog.  
  
7.  In the **Select Items to Import** dialog, accept the default selection of the **Use Existing Categories** check box, or optionally deselect this check box and specify the Library category in which to place collection items, by clicking the **Add to Category** drop-down list and selecting a category.  
  
8.  In the **Select Items to Import** dialog, select the collection items and/or categories that contain the items you want to import.  
  
9. Click **OK** to exit the **Select Items to Import** dialog and populate your centralized Filter Expression **Library** with the items you selected.  
  
<a name="BKMK_ManualUpdateSyncing"></a>   
## Manually Configure Asset Collection Update Synchronization on a User Feed  
 This example describes the process that you must follow to manually synchronize an asset collection for updates on a user-configured feed that points to a file share or other location where the collection is posted.  
  
#### To perform manual asset update synchronization  
  
1.  From the **Start** menu, **Start** page, or taskbar of your computer, click the **Microsoft Message Analyzer** icon to start Message Analyzer.  
  
2.  In the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu, click the **Settings** tab to display the list of **Subscribed Feeds**.  
  
3.  Click the link under the feed name containing the asset collection that you want to update, to display the *.asset and \*.metadata files for the collection that exists at the feed location.  
  
4.  For the asset collection that you intend to update, right-click the \*.metadata file and select the **Open With** context menu item so that you can specify an XML editor or the Visual Studio application to open the file.  
  
5.  In the opened metadata file, copy the GUID in the \<UniqueId> or \<GroupId> tag and store it in a temporary location.  
  
6.  Close the file and exit the editor application.  
  
7.  In the Message Analyzer user interface, locate the Library that contains the asset collection items you want to share with other users on your feed, click the Library drop-down list, and then select the **Manage** ***\<AssetType>*** item.  
  
8.  In the **Manage** ***\<AssetType>*** dialog, select the asset collection items you want to include in the update and then click **Export** to display the **Save Library** dialog.  
  
9. In the **Save Library** dialog, specify values for **Title** and **Author**, and optionally provide a **Description** and **Organization** information.  
  
10. Click **Save** to exit the **Save Library** dialog and to display the **Select Library Location...** dialog, from where you can navigate to the feed location. Note that you will be overwriting an existing collection when you click **Save**.  
  
11. Enter the asset collection **Title** that you specified in the **Save Library** dialog as the **File name** for the collection in the **Select Library Location...** dialog.  
  
12. Click **Save** to exit the **Select Library Location...** dialog.  
  
13. Click **Close** to exit the **Manage** ***\<AssetType>*** dialog.  
  
14. On the **Settings** tab in the **Asset Manager** dialog, click the link beneath the feed name that will contain your updated asset collection.  
  
15. Right-click the *.metadata file and \*.asset file for the update collection, and then do the following:  
  
    -   Select the **Open** command to open the files.  
  
    -   Paste the GUID that you obtained from step 5 into the \<UniqueId/> and \<GroupId/> tags in each file.  
  
    -   Incrementally increase the \<Revision/> tag value in each file with a new matched value to indicate that a revision is available to users.  
  
    -   Save the changes and close each file.  
  
16. Inform users that you have an update that they can download if they are subscribed to your feed, which should appear on the **Downloads** tab in the **Asset Manager** dialog of the user’s Message Analyzer installation.  
  
 Users should then be able to use the download or auto-sync option in the **Item Download Options** dialog to update their local Library with the latest version of your asset collection. After users update a Library, the collection items should appear in the Library under a category name that matches the feed name.  
  
## See Also  
 [Downloading Assets and Auto-Syncing Updates](../messageanalyzer_content/downloading-assets-and-auto-syncing-updates.md)