---
title: "Selecting a Data Retrieval Session Viewer | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab0b162e-7af8-4495-8793-28c7046d4b12
caps.latest.revision: 35
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting a Data Retrieval Session Viewer
After you configure a Data Retrieval Session with the files that contain the data you are targeting to load into Message Analyzer, you can choose a viewer in which to display the session results data. You can choose any data viewer that exists in the **Start With** drop-down in the **New Session** dialog for a Data Retrieval Session, including data viewer assets that you import through the Message Analyzer sharing infrastructure. For a list of the data viewers that Message Analyzer provides by default, see the topic [Selecting a Session Data Viewer](../messageanalyzer_content/selecting-a-session-data-viewer.md).  
  
## Changing Data Viewers  
 You can start loading data into Message Analyzer through a Data Retrieval Session any time after you create a selected input file configuration in the files list on the **Files** tab of the **New Session** dialog. Unless you specify otherwise, Message Analyzer will use the default data viewer to display your data, which is typically the **Analysis Grid** viewer. However, you can change the default data viewer setting that will be used by Message Analyzer for all sessions by specifying a viewer in the **Default Viewer** drop-down list on the **Default Profile** pane of the global **Options** dialog that is accessible from the Message Analyzer **Tools** menu.  
  
 Note that you have the option to override the default data viewer prior to starting a session, by explicitly specifying a different one that might have certain properties that are more useful for the data you are loading and/or the type of analysis you are planning to do. You can do this by clicking the **Start With** drop-down list in the **New Session** dialog and then selecting a data viewer of choice.  
  
 **Specifying a Default Data Viewer**   
The default data viewers that are available from the **Start With** drop-down list during Data Retrieval Session configuration, consist of the following:  
  
-   **Analysis Grid**  
  
-   **Grouping**  
  
-   **Pattern Match**  
  
-   **Gantt**  
  
-   **Chart** — displays a default Bar element graph with message volumes per module only when chosen from the **Start With** drop-down.  
  
 Note that the data viewers  in the following list are Preview features. To make these viewers available for selection during session configuration, you must select them on the **Features** tab of the **Options** dialog, which is accessible from the Message Analyzer **Tools** menu, and then you will need to restart Message Analyzer.  
  
-   **Interaction**  
  
-   **Message Summary Tiles**  
  
-   **Message Summary Lists**  
  
-   **Perfmon**  
  
 **Selecting Data Viewers After Data Retrieval**   
After you retrieve your data and it displays in the viewer that you initially selected, you can present your data in any of the other available viewers by selecting them from a context menu that is accessible by right-clicking any session node in the **Session Explorer** **Tool Window**. You can also access these same viewers by clicking the **New Viewer** drop-down list on the global Message Analyzer toolbar. By selecting different data viewer configurations, you can achieve unique data analysis perspectives to assist in problem solving.  
  
 Note that for many of the data viewers that are available from the **New Viewer** drop-down list, a submenu displays to enable you to select a **Layout** for a chosen viewer. For example, this could be a **Layout** for the **Analysis Grid**, **Chart**, or **Grouping** viewer that each  expose different message fields  to create a focused analysis environment. Some examples of analysis environments that view **Layouts** can create include the following:  
  
-   SMB file sharing and performance  
  
-   Event log and Cluster log analysis  
  
-   HTTP Operations response time analysis  
  
-   Traffic volume distributions per module or conversation  
  
-   TCP diagnosis  
  
-   IP conversation bandwidth consumption  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the data viewers and **Layouts** that are available in Message Analyzer, along with the **Tool Windows** with which they interact, see the [Data Viewers](../messageanalyzer_content/data-viewers.md) and [Tool Windows](../messageanalyzer_content/tool-windows.md) sections of this Operating Guide.  
**To learn more** about the integrated and interactive analysis environments that Message Analyzer provides with preset configurations of data viewers, **Layouts**, and **Tool Windows**, see [Working With Message Analyzer Profiles](../messageanalyzer_content/working-with-message-analyzer-profiles.md).  
___________________\_  
  
## See Also  
 [Session Data Viewer Options](../messageanalyzer_content/session-data-viewer-options.md)