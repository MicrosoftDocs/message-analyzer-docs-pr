---
title: "Manual Item Update Synchronization | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59ef69ba-0ade-437e-9942-65223650f905
caps.latest.revision: 18
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Manual Item Update Synchronization
This topic describes how to manually configure update synchronization for an asset collection that is published to a user-configured feed. In the Message Analyzer Sharing Infrastructure, the synchronization function of the publishing process relies upon consistency between the GUIDs of a published asset collection and the corresponding asset collection update version. This process occurs automatically whenever a default asset collection is set to the auto-sync state in the **Asset Manager** dialog. However, to successfully synchronize updates of asset collection items on a user-configured feed, some manual configuration is necessary to ensure that the GUID of the update asset collection is identical to the existing user asset collection on the user feed. To ensure that this occurs, it is incumbent upon the author of the collection update to manually assign the GUID of the existing user asset collection on the feed to the collection update version, so that users do not lose any items in their existing collection/s.  
  
 These GUIDs are specified in the *.metadata and \*.asset file pair that exists for every user Library asset collection. You can manually configure these files for a collection update by copying the existing asset collection GUID into specific XML tags within these files, as described in the procedure that is referenced in [Manually Configure Asset Collection Update Synchronization on a User Feed](procedures-using-the-asset-management-features.md#BKMK_ManualUpdateSyncing).