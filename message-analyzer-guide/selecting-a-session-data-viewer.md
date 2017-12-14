---
title: "Selecting a Session Data Viewer | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 286db9d7-4753-40d0-baa4-d41b221a9baa
caps.latest.revision: 42
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting a Session Data Viewer
Message Analyzer provides a set of native data viewers for all Message Analyzer installations. The features and functions of these data viewers are described in detail in the [Data Viewers](data-viewers.md) topic. This section  briefly describes the viewers that are available, selection locations, selection criteria, and how to identify multiple viewers that are common to a particular session.  
  
## Choosing a Session Viewer  
 Before you start a Live Trace Session or Data Retrieval Session, you can select the data viewer with which to view your trace results data. These data viewers are available from the **Start With** drop-down list that appears in the **New Session** dialog that you open when configuring a Live Trace Session or Data Retrieval Session. The data viewers that you can select from this location consist of the following:  
  
-   **Analysis Grid**  
  
-   **Grouping**  
  
-   **Pattern Match**  
  
-   **Gantt**  
  
-   **Chart** — displays a default **Bar** element graph only when chosen from this location.  
  
-   **Interaction**  
  
-   **Message Summary Tiles***  
  
-   **Message Summary Lists***  
  
-   **Perfmon***  
  
 Note that the data viewers in this list that are marked with an asterisk (\*) are **Preview** features. To make these viewers available for selection during session configuration, you must select them on the **Features** tab of the **Options** dialog, which is accessible from the Message Analyzer **Tools** menu, and then you will need to restart Message Analyzer.  
  
> [!NOTE]
>  If you do not specify a data viewer prior to starting a Live Trace Session or Data Retrieval Session, then Message Analyzer uses the current default viewer to display data, for example, the **Analysis Grid** viewer. You can set the default viewer for all session results in the **Default Profiles** pane on the **Profiles** tab of the **Options** dialog.  
  
## Other Viewer Selection Locations  
 You can also select the previously indicated viewers from either of the following alternate locations to change the data view for a set of trace results during an Analysis Session:  
  
-   **New Viewer** drop-down list — after you start a Live Trace Session or Data Retrieval Session, you can specify a different viewer for your data by clicking the **New Viewer** item in the global Message Analyzer **Session** menu or by clicking the **New Viewer** button on the global Message Analyzer toolbar to display a drop-down list that contains all the viewer selections.  
  
-   **Session Explorer** **Tool Window** context menu — after you start a Live Trace Session or Data Retrieval Session, you can specify a different viewer for your data by right-clicking anywhere in the **Session Explorer** window, clicking the **New Viewer** item in the context menu that appears, and then selecting a data viewer of choice along with a **Layout** if appropriate.  
  
 **Selecting Layouts**   
When you select data viewers from these alternate locations, the viewers listed immediately below will also enable you to choose a built-in view **Layout** in which to present the data. The built-in **Layouts** are custom designed by Microsoft to expose data that is relevant to specific types of analysis. For example, if you are interested in analyzing file sharing performance data after performing a capture, you might choose the **File Sharing Perf SMB/SMB2 Layout** for the **Analysis Grid** viewer in the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
-   **Analysis Grid**  
  
-   **Grouping**  
  
-   **Chart**  
  
-   **Charts (Deprecated)**  
  
## Selection Criteria  
 Depending on what you wish to achieve, there may be some things to consider when selecting a viewer in which to display message data that you captured live or retrieved from saved files. For example, the selected viewer should to some degree reflect the type of data being captured and should be considered in terms of the problem/s you are trying to isolate.  
  
 For example, if you simply want to expose data in a standard analysis environment, you can display data in the default **Analysis Grid** viewer **Layout**, as described in the [Analysis Grid Viewer](analysis-grid-viewer.md) topic. If you want to analyze process IDs and the associated IP conversations, you could choose the **Network Conversation Tree with Process ID** **Layout** for the **Analysis Grid** viewer, as described in [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md). Moreover, you can make similar choices for the **Grouping** viewer and the **Chart** viewer, which are each accessible from the same **New Viewer** drop-down list during analysis of session results.  
  
 If you want to look at high-level data summaries and statistics, you might consider using one of the many **Layouts** for the **Chart** viewer, for example, the **IP/Ethernet Conversations by Message Count Top 20** layout that provides a graphic **Bar** element representation of the relative distribution of message volume for each IP conversation in  a set of trace results. If you suspect network connection or latency issues, you might want to open the **TCP Diagnosis with Stevens** and/or **Top TCP/UDP Conversations** **Layouts** for the **Chart** viewer.  
  
## Identifying Session Viewer Data  
 Whenever you select a data viewer for a *new* session, it displays in a new and separate session viewer tab with a unique name just below the global Message Analyzer toolbar. If you select a new data viewer for an *existing* session, it displays in a new session viewer tab with the same name as the existing session, also just below the global Message Analyzer toolbar. To maintain correlation between data viewers of the same session, Message Analyzer provides an identical colored dot on the session tab of each data viewer in the same session, for ease of identification.  
  
---  
  
 **More Information**   
 **To learn more** about the different types of data viewers that are available, along with the **Tool Windows** with which they interact, see the [Data Viewers](data-viewers.md) and [Tool Windows](tool-windows.md) topics of this Operating Guide.  
**To learn more** about creating custom **Layouts** for the **Chart** viewer, see [Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md).  
---  
  
## See Also  
 [Selecting a Data Retrieval Session Viewer](selecting-a-data-retrieval-session-viewer.md)   
 [Session Data Viewer Options](session-data-viewer-options.md)