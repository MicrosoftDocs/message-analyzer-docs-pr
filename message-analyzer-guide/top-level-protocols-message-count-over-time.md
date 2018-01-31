---
title: "Top Level Protocols Message Count Over Time | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 06c224e9-1472-45d7-ae77-c86281d3e130
caps.latest.revision: 16
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Top Level Protocols Message Count Over Time

The **Top Level Protocols Message Count Over Time** viewer **Layout** for **Charts** presents data in  a **Timeline** visualizer component that plots data points in the X-Y coordinate domain. This component depicts message count as X-axis module lines that indicate the number of messages that were captured for a particular module across a set of trace results, with individual message nodes indicating the points in time when messages were captured. You can view the message count at any node for any module by hovering over one with your mouse and also in the legend to the right of the graphic viewer surface. In addition, the Y-axis is calibrated to provide an indication of relative message count for any node. Also, if you double-click a node or a module line, all the top-level messages and origins associated with that module will display in a separate **Analysis Grid** viewer tab for further analysis. You can also focus on the messages from a particular module by selecting them in a legend to the right of the timeline, and clearing selections of the message types you do not want to display.  
  
## Using the Top Level Protocols Message Count Over Time Layout  

 This **Layout** also enables you to adjust selectable time-window slider controls so that you can do the following:  
  
-   Visually assess the times at which protocol communications occurred within the time range of a trace.  
  
-   Use manual adjustments to drill down into specific time slots for a more granular view of the message activity that transpired there.  
  
-   Use **Zoom** presets to automatically create time windows that enable you to drill down into message activity in various time slots, starting from the beginning of a trace.  
  
     These preset values create time windows that are **1s**, **5s**, **30s**, and **1m** in length. After you specify one of these presets, you can return to the full trace time boundaries by clicking the **All** preset, or you can manually expand the trace boundaries with the time window slider controls.  
  
## See Also  

[Top Level Protocols Message Count](top-level-protocols-message-count.md)