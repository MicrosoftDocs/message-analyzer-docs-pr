---
title: "HTTP Content Type Volumes | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 244e1620-e4de-4451-9ec2-d7849943d123
caps.latest.revision: 14
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
description: "Learn Microsoft's Message Analyzer: Discover HTTP Content Type Volumes, analyze data, and improve web server performance."
---

# HTTP Content Type Volumes

The **HTTP Content Type Volumes** viewer **Layout** for **Charts** displays **HTTP Content Type Volumes** in a horizontal bar element graph. This visualizer component provides the following for a set of trace results:  
  
-   The relative volumes of HTTP content types in terms of payload lengths in bytes for each type.  
  
-   A visual indication that shows the relative distribution of byte volume for each content type.  
  
The labels to the left of the bar graph indicate the content type, the values to the right of the graph represent percentage values that are relative to the total volume in bytes for all payloads, and the bar elements of the graph provide a visual indication of such volumes for each content type. Note that the table in the **HTTP Content Type Payloads** viewer **Layout** repeats some of this data but also includes the total **MessageCount** for each content type.  
  
## Analyzing Volume Data  

 The bar element visualizer component of this **Chart** can help you see at a glance which byte volumes are the largest for any particular content type. In turn, this can provide an indication of the loads being carried by responding web servers. For example, you might double-click the bar element with the highest byte volume to display the associated messages in a separate instance of the **Analysis Grid** viewer. You can then right-click the **Destination** column in the **Analysis Grid** viewer and select the **Group** command to create groups of different web server names along with the number of messages associated with each one. This can tell you immediately which server/s are carrying the highest load for a particular content type, which in turn can provide an indication of web server performance.  
  
## See Also  

[HTTP Content Type Payloads](http-content-type-payloads.md)