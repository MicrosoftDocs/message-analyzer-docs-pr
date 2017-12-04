---
title: "SMB Reads and Writes Bytes-Second | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b9aa1be-1353-4e94-9438-7641eebb962a
caps.latest.revision: 33
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB Reads and Writes Bytes-Second
The        **SMB Reads and Writes Bytes/Second** view **Layout** for **Charts** enables you to obtain a quick assessment of Server Message Block (SMB) protocol performance from a graphic **Timeline** visualizer component. For example, from the **SMB Reads and Writes Bytes/Second** view **Layout**, you can obtain statistics that reflect the network bandwidth being consumed, in **Bytes per Second**, by the file access/sharing activities of the SMB protocol.  
  
> [!NOTE]
>  The **SMB Reads and Writes Bytes/Second** view **Layout** supports each of the SMB, SMB2, and SMB3 protocol versions.  
  
 This **Layout** also has a view **Filter** applied in the background that allows SMB Read, Write, and Open requests to pass while blocking all others, in order to create focus on specific SMB operations.  
  
## Using the SMB Reads and Writes Bytes/Second Layout  
 The main graphic display of this **Layout** provides data in the X-Y coordinate domain, where the X-axis is calibrated in time and the Y-axis is calibrated in bytes/second. You can obtain the  following statistics from the **SMB Reads and Writes Bytes/Second** view **Layout** for analysis purposes:  
  
-   The name of the file being accessed by the SMB protocol, as indicated in the Legend of the **Layout** and in a tool tip.  
  
-   The **Bytes/Second** rate for each SMB request message, as indicated by a Y-axis value and a  tool tip.  
  
-   The count of SMB request messages sent, as indicated by message nodes that appear when you select a line of data.  
  
 Note that you can selectively display or hide data lines  associated with specific files for which SMB operations were performed, by respectively selecting and unselecting  check box nodes in the file name Legend that appears in the right-hand section of the **Layout**. For each  node that you select in  the Legend, a line of data appears in the main graphic display at a particular point in the X-axis timeline. For each line of data, there can be one or more data points that appear after you single-click the line, where information for each data point displays in a tool tip when you hover over it with your mouse. This tool tip information consists of the following:  
  
-   **File name** — the name of the file upon which an SMB operation was performed.  
  
-   **Time** — the time at which the SMB requests occurred.  
  
-   **Value** — the bytes/second rate for the SMB request message that is represented as a data point in the data line. This tool tip value is also reflected by a corresponding Y-axis value.  
  
-   **Count** — the number of messages associated with a particular data point.  
  
 **Using the Adjustable Time Windows and Presets**   
The **SMB Reads and Writes Bytes/Second** view **Layout** has preset **Zoom** values that adjust your view of the data so that you can examine message activity and bytes/second rates within specific windows of time, which includes **1s**, **5s**, **30s**, and **1ms** window presets. After you apply one of these presets, you can return to the original display showing all data lines by clicking the **All** preset. You can also adjust the time-window slider controls in order to zoom into the SMB Read, Write, or Open request activity that occurred in any time slot that you configure.  
  
 **Interactively Correlating the Data**   
 If you want to display only the SMB requests and supporting message stack that comprised a particular SMB file operation, you can double-click a data line in the visualizer component used in the **SMB Reads and Writes Bytes/Second** view **Layout** and Message Analyzer will display all the associated SMB Operations in a new instance of the **Analysis Grid** viewer. This action provides you with immediate access to **Details** **Tool Window** data so that you can review message field data and other details for messages that you select in the **Analysis Grid** viewer.