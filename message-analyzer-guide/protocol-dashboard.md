---
title: "Protocol Dashboard | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1058c791-1500-4915-a565-dee5a14d09ff
caps.latest.revision: 25
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Protocol Dashboard

The **Protocol Dashboard** is a **Chart**-style data viewer that enables you to obtain a quick assessment of trace performance from graphic visualizer components that provide top-level summary information. It exists in the **Dashboards** category of your local **Charts** asset collection Library, which is accessible from the locations described in [Chart Viewer Layouts](chart-viewer-layouts.md). A description of the  visualizer components that are contained in the **Protocol Dashboard** follows.  
  
## Using the Protocol Dashboard  

 The **Protocol Dashboard** contains the following visualizer components:  
  
- **Top Level Protocol Summary** grid — consists of a table that provides a summary of the top-level messages retrieved by various modules in a trace, along with the number of top-level messages received from each module.  
  
  > [!NOTE]
  >  If you double-click a table row, all messages in which the module is either a top-level message or part of message origins will display in a separate **Analysis Grid** viewer tab. Because *all* messages are displayed in a separate viewer tab as indicated, the message count in that viewer tab will differ from the top-level message count specified in the **Top Level Protocol Summary** table. To see only the top-level messages in the new **Analysis Grid** viewer tab, you can apply a view **Filter** that isolates top-level messages by using the backslash symbol (“\”) described in [Browsing Message Origins](using-the-filtering-language.md#BKMK_BrowseMessageOrigins), as follows:   
  > `“\<modulename>”`  
  >  — where \<modulename> is a placeholder for the module or protocol of interest.  
  
- **Top Level Protocol Summary** bar **Chart** — this visualizer component illustrates message data in a linear graphic format that provides an at-a-glance view of the relative volume of the top-level messages received from different source modules over the trace timeline. If you double-click any data bar representing a message source in this **Chart**, the details for the top-level messages represented by that particular data bar are rendered in a separate **Analysis Grid** viewer tab for further analysis.  
  
  > [!NOTE]
  >  If you double-click a bar in the bar **Chart** visualizer component, you will see the same message count disparity as described in the previous note. Similar to the table grid, you can see the top-level messages by applying a view **Filter** with the backslash symbol (“\”), as previously indicated.  
  
- **Top Level Protocol Summary** pie **Chart** — similar to the **Top Level Protocol Summary** bar **Chart**, this visualizer component also illustrates the relative volume of top-level messages received from different source modules; however, the data is presented in a pie chart configuration instead. In this **Chart**, message volume for source modules is delineated as a percentage of the whole so you can quickly obtain the top protocol usage-percentage in the trace. You can also double-click any source module in the **Top Level Protocol Summary** pie **Chart** to present the associated top-level message details in the Message Analyzer **Analysis Grid** viewer.  
  
> [!NOTE]
>  Both the bar and pie **Chart** visualizer components can provide an at-a-glance indication of the top bandwidth consumers in a trace.  
  
-   **Top Level Protocols Over Time** timeline **Chart** — this visualizer component provides a graphic, X-Y axis formatted chart. This component depicts message count as X-axis module lines that indicate the number of messages that were captured for a particular module across the entire trace timeline, with individual message nodes indicating the points in time when messages were captured. You can view the message count at any node for any module by hovering over one with your mouse and also in the legend to the right of the graphic viewer surface. In addition, the Y-axis is calibrated to provide an indication of relative message count for any node.  
  
     In addition, if you double-click a node or a module line, all the top-level messages and origins associated with that module will display in a separate **Analysis Grid** viewer tab for further analysis. You can also focus on the messages from a particular module by selecting them in a legend to the right of the timeline, and clearing selections of the message types you do not want to display. Lastly, this visualizer component enables you to adjust selectable time-window slider controls so that you can do the following:  
  
    -   Visually assess the times at which protocol communications occurred within the time range of a trace.  
  
    -   Use manual adjustments to drill down into specific time slots for a more granular view of the message activity that transpired there.  
  
    -   Use **Zoom** presets to automatically create time windows that enable you to drill down into message activity in various time slots, starting from the beginning of a trace.  
  
         These preset values create time windows that are **100 ms**, **1s**, or **5s** in length. After you specify one of these presets, you can return to the full trace time boundaries by clicking the **All** preset, or you can manually expand the trace boundaries with the time window slider controls.  
  
> [!TIP]
>  If you apply a view **Filter** or a **Time Filter** to the **Protocol Dashboard** viewer in a particular session, messages will be appropriately filtered in this viewer only, while the message data in any other viewer opened in the same session remains unaffected.