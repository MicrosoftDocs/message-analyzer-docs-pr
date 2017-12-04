---
title: "SMB Reads and Writes Bytes Sent | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24db674-8b4a-4559-88e5-87e578625eda
caps.latest.revision: 17
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB Reads and Writes Bytes Sent
The **SMB Reads and Writes Bytes Sent** view **Layout** for **Charts** provides a summary of byte values associated with SMB/SMB2 read, write, and open requests for file operations across a set of trace results. The summary data is presented in a **Table** grid visualizer component that provides an overview of the average and maximum request size in bytes for the SMB/SMB2 message/s associated with each file operation. The table contains the following columns of data:  
  
-   **FileName** — specifies the name and path of files upon which an SMB operation was performed.  
  
-   **Count** — specifies the number of SMB/SMB2 request messages associated with an operation.  
  
-   **Average** — calculates the average size in bytes of the messages sent in  an operation.  
  
-   **Max** — specifies the highest message size in bytes among all messages sent in an operation.  
  
 This **Layout** also has a view **Filter** applied in the background that allows the indicated types of SMB or SMB2 requests to pass while blocking all others, in order to create focus on specific SMB/SMB2 operations.  
  
## Using the SMB Reads and Writes Bytes Sent Layout  
 You can create an interactive analysis context by driving the display of data into the **Analysis Grid** viewer. For example, you can double-click any row of data in the **SMB Reads and Writes Bytes Sent** Table to display the associated messages in a new instance of the **Analysis Grid** viewer for further assessment of **Summary** information and message **Details**.  
  
 If you redock the **SMB Reads and Writes Bytes Sent** view **Layout** so that it displays next to the **Analysis Grid** viewer with its default **Layout** in which your original data appears, you can then correlate the data in the **SMB Reads and Writes Bytes Sent** Table with the corresponding messages in the **Analysis Grid** viewer, by simply clicking a row in the Table. Each time you select a Table row, you will have immediate access to **Details** **Tool Window** data for the corresponding message that is automatically selected and highlighted in the **Analysis Grid**.  
  
 You might also consider displaying the **Analysis Grid** viewer with its **File Sharing SMB/SMB2** **Layout** to create a grouped viewing configuration that organizes the SMB/SMB2 data by **SessionId** at top-level, **TreeId** at the first nested level, and **FileName** nested below that. You could also drag-and-drop the **FileName** label above the group message nodes in the **Analysis Grid** all the way to the leftmost position in the label order to reorganize the group display with **FileName** nodes at top-level and then use the **Expand All Groups** context command for each group to expose all the messages. You can then easily correlate **FileName** data in the **SMB Reads and Writes Bytes Sent** view **Layout** with corresponding messages in the  **Analysis Grid** viewer by simple selection of Table rows.  
  
 The advantage of this viewing configuration is that it enables you to correlate the nested **SessionId** and **TreeId** data with the **FileName** row that you select in the  **SMB Reads and Writes Bytes Sent** Table. Note that you can also sort the **FileName** column of the **SMB Reads and Writes Bytes Sent** view **Layout** to enable faster location of specific file names.