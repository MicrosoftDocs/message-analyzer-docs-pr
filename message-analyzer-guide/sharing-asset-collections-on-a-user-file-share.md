---
title: "Sharing Asset Collections on a User File Share | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ceb7fca2-7989-48d1-9034-56585e842f50
caps.latest.revision: 14
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Sharing Asset Collections on a User File Share

You and other team members can directly share the items that are contained in your local asset collection Libraries. Message Analyzer provides a simple way to expose these assets so that you and others can retrieve them for collaboration and mutual use. To share asset collection items directly with others, you can use the **Export** command in the **Manage** ***\<AssetType>*** dialog for the Library to save one or more items to a designated SMB file share or other location. In addition, you can use the **Import** command in the same dialog to access asset collection items that have been shared by others at the designated location. When exporting assets, you have the option to select specific collection items that you want to distribute to others, including any items that you have created or modified. When importing collection items, you can select which items you want to retrieve and the category in which to place them in an associated local asset collection Library.  
  
> [!NOTE]
>  It is advisable to only import asset collections to your local Libraries through the Message Analyzer downloads and auto-sync features, because any duplicate items in a direct import will not overwrite existing items in your Libraries, which can result in duplicate Library items.  
  
## See Also  

[Creating Custom User Feeds](creating-custom-user-feeds.md)   
[Managing User Libraries](managing-user-libraries.md)