---
title: "Managing Pattern Expressions | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 179af4d4-1271-405e-ab0d-ea06cd2a9a5e
caps.latest.revision: 30
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing Pattern Expressions
Message Analyzer enables you to save OPN behavior scenarios as **Pattern** expression items that you can share with others. Whenever you create a new **Pattern** expression or edit a copy of an existing one, you can save it to the local **Pattern** expression Library. Message Analyzer enables you to share your **Pattern** expression items with others by providing you with the capability to manage this Library. The management capabilities are provided in the **Manage Pattern** dialog that contains similar functionality that you use to manage any of the Message Analyzer asset collections that are described in [Saving Settings](saving-settings.md).  
  
## Managing and Sharing Pattern Expressions  
 To manage your **Pattern** expression items in the **Message Analyzer Sequence Expressions** asset collection Library, click the **Manage Patterns** button on the toolbar of the **Pattern Match** viewer. This action will display the **Manage Pattern Expression** dialog, from where you can export and import selected **Pattern** expressions. You can also **Delete** any **Pattern** expression in the **My Items** category from the **Manage Pattern Expression** dialog. You can export **Pattern** expressions directly to a file share to provide other users with access to your expressions, or you can import **Pattern** expressions directly from a file share to obtain access to the expressions of other users.  
  
 You can also export **Pattern** expression items through a user feed that you configure from the **Settings** tab of the **Asset Manager** dialog, in which you point your feed to a file share or other designated location where you will export your items; the **Asset Manager** is accessible from the global Message Analyzer **Tools** menu. Thereafter, your **Pattern** expression items are accessible to any Message Analyzer user that can access the feed. Your feed will appear on the **Downloads** tab of the Message Analyzer **Asset Manager** dialog, where other users can access a consistent interface that enables them to download your postings. However, if you want to enable users to synchronize with updates to your **Pattern** expression items, some manual configuration is required, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
 In addition, Microsoft provides a default **Message Analyzer** feed on the **Downloads** tab of the **Asset Manager** dialog that enables you to download the **Message Analyzer Sequence Expression** asset collection from a Microsoft web service and to synchronize with collection updates that are periodically pushed out by the service. At any time, you can perform a download of an auto-synced collection from the **Settings** tab on the **Asset Manager** dialog. Thereafter, you can access and apply the downloaded or synchronized items from the local **Pattern** expression Library in the **AVAILABLE PATTERNS** list of the **Pattern Match** viewer.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the common **Manage** ***\<AssetType>*** dialog and the management capabilities it provides for Message Analyzer Library asset collections, see [Managing User Libraries](managing-user-libraries.md).  
**To learn more** about the Message Analyzer Sharing Infrastructure, see [Sharing Infrastructure](sharing-infrastructure.md), [Creating Custom User Feeds](creating-custom-user-feeds.md), and [Sharing Asset Collections on a User File Share](sharing-asset-collections-on-a-user-file-share.md).   
___________________\_