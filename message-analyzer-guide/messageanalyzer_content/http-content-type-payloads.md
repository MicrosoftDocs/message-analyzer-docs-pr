---
title: "HTTP Content Type Payloads | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b2ed2f79-a3c1-4983-b3a0-04d8c9d47649
caps.latest.revision: 13
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# HTTP Content Type Payloads
The **HTTP Content Type Payloads**  viewer **Layout** for **Charts** displays payloads in bytes and message count data that is associated with HTTP content types detected in a set of trace results. From this  visualizer component, you can obtain the following data for analysis:  
  
-   The volumes of HTTP content types in terms of payload lengths in bytes for each type.  
  
-   The count of messages associated with each content type.  
  
 The  **HTTP Content Type Payloads** data is displayed in tabular format and includes **ContentType**, **PayloadBytes**, and **MessageCount** columns that contain the data. Note that the bar element graph in the **HTTP Content Type Volumes** viewer **Layout** repeats some of this data but does not include the **MessageCount** for each content type.  
  
## Analyzing Payload Data  
 The tabular data of this **Chart** can help you see at a glance which payload byte values and message counts are the largest for any particular content type. In turn, this can provide an indication of the loads being carried by responding web servers. For example, you might double-click a table row with the highest payload byte value to display the associated messages in a separate instance of the **Analysis Grid** viewer. You can then right-click the **Destination** column in the **Analysis Grid** viewer and select the **Group** command to create groups of different web server names along with the number of messages associated with each one. This can tell you immediately which server/s are carrying the highest load for a particular content type, which in turn can provide an indication of web server performance.  
  
## See Also  
 [HTTP Content Type Volumes](../messageanalyzer_content/http-content-type-volumes.md)