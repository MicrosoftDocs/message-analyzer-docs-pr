---
title: "Saving Message Data | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 282be3f1-97ae-48ea-9bb1-99d2fe5b60c6
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Saving Message Data
After you have loaded data through a Data Retrieval Session or captured data in a Live Trace Session and displayed it in a viewer such as the **Analysis Grid** viewer, in most cases you will manipulate the data in some way to isolate specific information and analyze the issues on which you are working. For example, you might have modified your Data Retrieval Session or Live Trace Session results data in one or more of the following ways:  
  
-   Displayed additional message fields by adding specific columns to the **Analysis Grid** viewer to contain new field data.  
  
-   Applied a view **Filter** to isolate specific message data.  
  
-   Created **Color Rules** for a data set, to highlight messages based on various protocol names, field values, states, and so on.  
  
-   Set **Viewpoints** or changed a viewer **Layout**.  
  
 However, although you may have modified your data display in an Analysis Session, Message Analyzer will allow you to save only certain settings that you configured for a set of trace results. These settings include the following:  
  
-   **Filtered data** — you can save the results of applying a view **Filter** to a set of messages. You can also save the results that display in a separate **Analysis Grid** viewer tab, for example, a set of messages that display in an **Analysis Grid** viewer tab after you have double-clicked a visualizer component in another data viewer such as the **Protocol Dashboard** or some **Chart** viewer **Layout**.  
  
-   **Selected messages** — you can save any set of messages that are currently highlighted.  
  
-   **Bookmarks** — you can save bookmarks that you configured in a set of trace results, but only if you save your data in the Message Analyzer native .matp format.  
  
-   **Comments** — you can save comments that you configured in a set of trace results, but only if you save your data in the Message Analyzer native .matp format.  
  
-   **Time Shifts** — you can save a **Time Shift** that you applied in a set of trace results, but only if you save your data in the Message Analyzer native .matp format.  
  
> [!NOTE]
>  In a future release of Message Analyzer, you may be able to save more settings.  
  
---  
  
 **What You Will Learn**   
In this section, you will learn about saving session data to the default location, the selection options for saving messages, specifying file formats, and naming files, as indicated by the topics below.   
---  
  
## In This Section  
 **[Saving Session Data](saving-session-data.md)**  — learn how to use the **Save As/Export Session** dialog to save trace results data in the *.matp file format, or to export trace results to a \*.cap file for compatibility with other applications, such as Network Monitor.  
  
 **[Selecting Messages to Save](selecting-messages-to-save.md)**  — review the save options that are available, which includes saving **All Messages**, **Filtered Messages**, and **Selected Messages**.  
  
 **[Saving Files in Native Format](saving-files-in-native-format.md)**  — learn about saving data in the default native file formats, saving settings such as comments and bookmarks, and the advantages of reloading data from trace files that you save in the default *.matp format. Also learn about external compatibility with other applications, such as Wireshark.  
  
 **[Naming Saved Files](naming-saved-files.md)**  — review some tips and suggestion on naming the trace and log files that you save.