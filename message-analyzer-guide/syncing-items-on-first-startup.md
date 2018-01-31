---
title: "Syncing Items on First Startup | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8efe1274-79ad-4540-9aca-8456aeb214b9
caps.latest.revision: 16
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Syncing Items on First Startup

This section describes the syncing options that you can utilize upon first Message Analyzer startup following installation. These options enable you to opt-in or opt-out of auto-syncing updates to your asset collection Libraries from a Microsoft web service. When you auto-sync a collection for updates, it is automatically downloaded to your Message Analyzer installation as new versions of existing collection items become available. This includes updates for asset collection Libraries, OPN Parser packages, and news items on the Message Analyzer **Start Page**.  
  
## Choosing to Opt In or Out of Auto-Synced Updates  

 When you first start Message Analyzer following your initial installation, you are presented with a **Welcome to Message Analyzer** dialog that prompts you to opt-in or out-out of auto-synced updates. The prompt indicates that while your PC is online, you can automatically receive updates to the previously indicated entities. The dialog options that are presented and the effect each one has consist of the following:  
  
-   **Update items** — if you select this option, the default asset collection Libraries are all set to the auto-sync state and moved to the **Settings** tab in the **Asset Manager** dialog, where the auto-sync state is indicated by a grey button containing circular arrows to the right of each asset collection. However, you can only receive updates that are pushed out by the web service if you have Message Analyzer set to the **Online** mode, which is the default setting in the **Asset Manager**. Moreover, if you toggle the **Online** button to the **Offline** mode, asset collections still retain the auto-sync status, but your local Libraries will not be updated until you reset to the **Online** mode.  
  
-   **Do not update items** — if you select this option, the default asset collection Libraries are not set for auto-syncing updates and they appear as un-synced on the **Downloads** tab of the **Asset Manager**, where the un-synced state is indicated by a server download status icon. However, even after choosing the **Do not update items** option, you can still set the default asset collection Libraries to auto-sync, either by clicking the **Sync All Displayed Items** button on the **Downloads** tab of the **Asset Manager** to auto-sync all collections, or by clicking the server download status icon of one or more individual collections, to display the **Item Download Options** dialog. From this dialog, you can select the **Automatically sync item updates when available** option to set the auto-sync state for any asset collection Library. Thereafter, any asset collection that you set for auto-syncing is moved to the **Settings** tab of the **Asset Manager**, where it displays the auto-synced status button.  
  
## See Also  

[Starting Message Analyzer for the First Time](installing-and-upgrading-message-analyzer.md#BKMK_StartingMAFirstTime)