---
title: "Creating Custom User Feeds | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72d36617-8744-492d-a505-0621e742016c
caps.latest.revision: 20
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Creating Custom User Feeds
Although Message Analyzer enables you to stay current with the latest asset collections and **OPN Parser** packages through the download and auto-syncing features, it also enables you to share asset collections directly with other users for collaboration and mutual use, as part of the Sharing Infrastructure capabilities. You can do this by configuring your own custom feeds. After you configure a user feed, you can export one or more items from any user Library as an asset collection and post it to a file share or other location to which the feed points. To perform an export, you must use the **Manage** ***\<AssetType>*** dialog for the particular asset collection Library with which you are working. After you export an asset collection to a user feed, other team members can then acquire the collection by importing it into their local user Library for the specific collection type, by using the same **Manage** ***\<AssetType>*** dialog for the particular Library. When exporting asset collection items, you can select specific collection items that you want to distribute to others, including any items that you have created or modified. When importing asset collection items, users can select which items they want to retrieve and the category in which to place them in their local user Library.  
  
## Configuring a User Feed  
 When you configure your own feed you must specify a feed **Location**, such as an SMB file share, web service, or other designated location, and you must also specify a **Feed Name**. The name you provide can be at your own discretion, but you might consider naming it in accordance with the team that will access the asset collection. To configure a user feed, go to the **Settings** tab in the **Asset Manager** dialog and click the **Add New Feed** button to display the **Add Feed Location** dialog. In the dialog, enter the name of the feed in the **Feed Name** text box and specify the file share path or other designated location in the **Location** text box. After you have entered this information, click the **Add** button to exit the dialog and create the new feed.  
  
 Note that you can create a feed and then place asset collections at the feed location; or you can place asset collections in a directory location that you intend to designate as the feed location, and then point to that location when you actually configure the **Location** value in the **Add Feed Location** dialog. However, if you use a file share as the location, keep in mind that you will need to configure the share with user permissions.  
  
## Working with a User Feed  
 After you configure a user feed, it displays on the **Downloads** tab of the **Asset Manager** in the feeds row, and on the **Settings** tab beneath the **Subscribed Feeds** label. When you click the user feed name on the **Downloads** tab, all the asset collections that exist on the feed are displayed in the **Downloads** list along with status icons to the right of each collection, just as it does for collections that are sourced from the default **Message Analyzer** subscriber feed. Thereafter, you can update existing collections or add others and make them available to team members or other users who subscribe to your feed. Other users can add your feed to their Message Analyzer installation by using the **Add New Feed** feature on their **Settings** tab. For others to subscribe to your feed, you will need to provide the feed location to them and ensure that they have permissions to the feed location, as appropriate. They can then view and download your asset collections by clicking the server download status icon for an asset collection and then selecting the download option to retrieve the collection for use in a particular local user Library.  
  
 However, for users to synchronize with asset collection *updates*, some manual configuration is necessary in the current Message Analyzer release, as described in [Manual Item Update Synchronization](../messageanalyzer_content/manual-item-update-synchronization.md). In future Message Analyzer releases, the Sharing Infrastructure publishing features will automatically enable others to synchronize to updates that you make to your asset collections on any user feed that you create.  
  
 _____________\_  
  
## See Also  
 [Manual Item Update Synchronization](../messageanalyzer_content/manual-item-update-synchronization.md)