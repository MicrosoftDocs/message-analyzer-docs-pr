---
title: "Session Explorer Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc6670b3-a62f-4430-8a1c-9f500a3f6ac5
caps.latest.revision: 27
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Session Explorer Tool Window
The **Session Explorer** **Tool Window** is a single-instance, interactive, and dockable window that drives the selection of Message Analyzer session viewers that can contain data from Live Trace Sessions and/or Data Retrieval Sessions in different view configurations. The **Session Explorer** window also provides a **New Viewer** context menu that enables you to select numerous types of data viewers and **Layouts** to assist your data analysis process.  
  
 The **Session Explorer** window configuration contains session nodes and viewer subnodes, along with associated progress indicators that display when messages are being loaded, captured, or processed by Message Analyzer. All viewer subnodes in the **Session Explorer** window are contained under top-level session nodes, and can consist of one or more viewers for each Live Trace Session and/or Data Retrieval Session in display.  
  
 Whenever you have session data for which there are multiple data viewers displayed, you can bring the data contained in a particular viewer into focus by clicking the appropriate viewer subnode in the **Session Explorer** window. For example, a session node for a Live Trace Session might have **Analysis Grid** and **Gantt** session viewer subnodes under it that represent the corresponding data viewers that you opened for that session. If you successively select these subnodes, the selection action drives the display of data in the **Analysis Grid** viewer tab and then in the **Gantt** viewer tab. Note that you can also bring the data of a particular viewer into focus by simply selecting its session viewer tab in an Analysis Session.  
  
## Using Session Explorer Features  
 The functions and features of the **Session Explorer** window enable you to do the following:  
  
-   **Select new session data viewers** — **Session Explorer** has a context menu that displays when you right-click any session node, viewer subnode, or anywhere in the white space of the **Session Explorer** window. The **New Viewers** command in the context menu opens a submenu that provides a selection of numerous  data viewers that you can choose to enhance your data analysis perspectives. For some viewers, such as the **Analysis Grid**, **Grouping**, and **Chart** viewers, you can specify a **Layout** from a drop-down list that displays when you highlight one of these viewers in the indicated submenu.  
  
     From the **New Viewers** submenu, you can select any of the data viewers that are described in the [Data Viewers](data-viewers.md) section of this documentation. After you select one or more viewers, Message Analyzer displays data from the current session in a separate viewer tab for each different type of viewer.  
  
     The **Session Explorer** context menu also has a **Close** command that closes the session represented by a selected top-level session node, along with all open viewers in such a session. Note that if you have more than one data viewer open in a particular session, you can close a single data viewer only, without closing the session, by right-clicking its node and selecting the **Close** command.  
  
-   **Navigate session viewer tabs** — after you open different data viewers for one or more sessions and data displays in separate session tabs, the **Session Explorer** window enables you to quickly navigate through the data contained in each session viewer tab. For example, by selecting any viewer subnode in **Session Explorer**, you can instantly display the session viewer tab containing the data that corresponds to the selected viewer subnode. By polling through your data viewers and presentation formats in this manner, you achieve different data perspectives that can enhance your analysis experience.  
  
     In addition, for each session that you open and display data in a selected Message Analyzer viewer, a color-coded dot is configured in the top-level session node in **Session Explorer**, for ease of identification. Thereafter, all data viewers that you open in an identical session will also contain the same color-coded dot in its viewer node in **Session Explorer**, thus automatically organizing the applicability of your data viewers. Note that the same color code is also applied to the associated session viewer tabs that display in the data analysis surface of the Message Analyzer UI.  
  
-   **Observe session and viewer tooltip information** — if your mouse hovers over a top-level session node in **Session Explorer**, a tooltip displays to indicate the number of messages in the session. Also, if your mouse hovers over a session viewer node in **Session Explorer**, you can see the analytical assets that are applied to the associated session viewer. For example, the tooltip can display the currently applied filtering configuration, which can include a **Viewpoint**, **Viewpoint Filter**, **Time Filter**, **Message Range Filter** (from the **Gannt** viewer), and/or view **Filter**.  
  
-   **Monitor session performance and status** — you can monitor session performance by observing *relative* progress indicators that display when you are loading saved trace and log file data into Message Analyzer through a Data Retrieval Session, or you can observe *ambiguous* progress indicators when you are capturing data in a Live Trace Session. Relative progress indications are also provided whenever you apply data manipulation functions to a set of messages, which includes filtering, sorting, finding, grouping, and pattern matching. Relative progress indicators are more definitive because Message Analyzer can determine the number of messages being loaded; whereas for ambiguous progress indicators, this is not the case.  
  
     You can also monitor session statistics such as the following in the Message Analyzer status bar area:  
  
    -   **Session status** — for example, you might see an indication such as “Ready” or “Processing”.  
  
    -   **Session Total** — the total number of messages in a session.  
  
    -   **Available** — the number of available messages in a session after operations such as **Viewpoints** and view **Filters** are applied to a set of trace results.  
  
    -   **Selected** — the number of messages that are currently selected in a set of trace results.  
  
    -   **Viewpoint** — the current **Viewpoint** that is applied to a set of trace results.  
  
    -   **Truncated Session** — indicates with a **True** or **False** label whether or not a session has truncated messages.  
  
    -   **Parsing Level** — the current **Parsing Level** that is applied to a set of trace results.  
  
## Displaying Session Explorer  
 If the **Session Explorer** window is not displayed, click the global Message Analyzer **Tools** menu, click the **Windows** item, and then select the **Session Explorer** item to restore it. Note that you can also undock and reposition the **Session Explorer** window by taking advantage of the docking navigation control that displays after you drag the **Session Explorer** window away from its default docking location. You might do this to configure a location for the window that is more convenient for the analysis environment in which you are working.  
  
---  
  
 **More Information**   
 **To learn more** about selecting data viewers, see [Session Data Viewer Options](session-data-viewer-options.md).  
**To learn more** about progress monitoring and session statistics, see [Viewing Session Statistics and Progress](viewing-session-statistics-and-progress.md).  
**To learn more** about docking and redocking tool windows, see [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md).  
---