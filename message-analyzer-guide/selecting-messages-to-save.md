---
title: "Selecting Messages to Save | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: af97753d-0ae7-46d3-bd66-fab760d822d3
caps.latest.revision: 26
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting Messages to Save
Message Analyzer enables you to select specific messages from a session that you want to save by allowing you to specify one of the following save options in the **Save/Export Session** dialog:  
  
> [!NOTE]
>  When you save data with either the **Filtered Messages** or **Selected Messages** option, the option descriptions will indicate the type of viewer or session, respectively, for which you are saving data.  
  
-   **All Messages** — enables you to save all messages that have been loaded from a Data Retrieval Session or captured in a Live Trace Session. The data that you save depends on which viewer session tab that you select.  
  
-   **Filtered Messages** — enables you to save a filtered message set that is displayed in a viewer such as the **Analysis Grid** or a **Chart** viewer **Layout**, for example, messages that display following application of a view **Filter** or **Viewpoint**. However, note that when you open a trace file that you saved, it initially opens in the **Analysis Grid** viewer, even if you saved the data while a different viewer was displaying it.  
  
-   **Selected Messages** — enables you to save only specific messages that you select in a session, for example, in the **Analysis Grid** viewer.  
  
     Note that the message count that displays when you save with this option, as parenthetically indicated in the option description, refers to top-level parent messages only and does not specify the total count of included underlying origins messages that supported such top-level messages or operations.  
  
> [!TIP]
>  If you want to select specific messages to save, you can do so by selecting a message in the **Analysis Grid** viewer and using the keyboard shortcut `Shift+Down Arrow` until you highlight all the messages you want include in the save. You can then right-click the message selection and select the **Save Selected Messages…** command in the context menu. Thereafter, the Windows **Save As** dialog opens to the default save location for Message Analyzer traces. You can then specify a file name in the .matp format and save your selected messages by clicking the **Save** button in the dialog.  
>   
>  Note that you can also export any messages you want with the use of the **Export** feature on the **Analysis Grid** viewer toolbar. However, this feature saves your messages in comma separated value (CSV) format.