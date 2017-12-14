---
title: "IIS Log Server Bytes by Host over Time | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 61f7a23d-b0a6-41e0-85c0-5302fa7c8084
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# IIS Log Server Bytes by Host over Time
The **IIS Log Server Bytes by Host over Time** view **Layout** for **Charts** enables you to obtain a high-level view of specific data from an IIS log consisting of HTTP traffic volume in bytes over time. This **Layout** uses a **Timeline** visualizer component that plots byte volume data points in time, with reference to the Y-axis calibrated in bytes and the X-axis calibrated in time. The **Layout** includes a time slider control in the lower section of the **Layout** that enables you to zoom into a configured time window to create a focused analysis context. Several **Zoom** presets are also included, such as **30s**, **1m**, **30m**, and **All**.  
  
## Using the IIS Log Server Bytes by Host over Time Layout  
 The data that displays in this **Layout** can give you a quick summary of the points in time where HTTP traffic volumes are the highest and how those volumes varied over the timeline. You can also perform the following actions to display the indicated data:  
  
-   **Host or site name** — mouse-hover over a data line in the x-y coordinate domain of the graph to display the name of the host or site for which the data was collected.  
  
-   **Data points** — single-click a line of data to expose the data points that exist at different times.  
  
-   **Log entries** — double-click a data line to display all related log entries in the **Analysis Grid** viewer.  
  
 Along with the **IIS Log Server Bytes by Host over Time** view **Layout**, you might also consider using the **Grouping** viewer with the **IIS** **Layout** and the **Analysis Grid** viewer with the **IIS** **Layout** to achieve an integrated and interactive analysis context that can significantly enhance your analysis process.  
  
## See Also  
 [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)   
 [Grouping Viewer](grouping-viewer.md)   
 [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)