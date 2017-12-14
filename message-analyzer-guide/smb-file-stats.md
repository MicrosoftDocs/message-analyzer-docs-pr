---
title: "SMB File Stats | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84972c54-c93e-4a5a-bc4a-26a089d88de6
caps.latest.revision: 19
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB File Stats
The **SMB File Stats** view **Layout** for **Charts** provides some basic file access statistics. This **Layout** provides this information in a **Table** grid visualizer component from which you can obtain the following types of data for troubleshooting file access operations:  
  
-   The duration of file or folder access operations  
  
-   The total bytes for each operation  
  
-   The data transmission rate  
  
## Using the SMB File Stats Layout  
 With the statistics provided by this **Layout**, you may be able to determine whether there are bottlenecks occurring during file access operations, network latency issues, or perhaps a poorly responding server. This **Layout** provides the following columns of information:  
  
-   **FileName** — a sortable column of data that specifies the name of the file or folder being accessed by the SMB protocol.  
  
-   **Duration** — for each row of data, this column provides the time expired during file or folder access operations, in values that resolve to 7 decimal places.  
  
-   **Bytes** — for each row of data, this column indicates the total number of bytes for each file or folder access operation.  
  
-   **BPS** — for each row of data, this column specifies the data transmission rate in bytes-per-second. The **BPS** values are calculated by dividing the **Bytes** values by the **Duration**.  
  
-   **Start** — for each row of data, this column provides a low-resolution timestamp that reflects when the transaction began.  
  
-   **End** — for each row of data, this column provides a low-resolution timestamp that reflects when the transaction ended.  
  
    > [!NOTE]
    >  The **Duration** values are extrapolated from the **Start** and **End** timestamps.  
  
 **Interactive Analysis**   
You can also interactively drive the display of messages into the **Analysis Grid** viewer by double-clicking any row of data in the **SMB File Stats** view **Layout**. This results in specific messages in a standard environment for detailed analysis that includes quick access to diagnosis errors and top-level messages that encapsulate message stacks, fragments, and Operations, in addition to the data that is available from the default column **Layout** of the **Analysis Grid** viewer.  However,  you might also consider using other **Layouts** for the **Analysis Grid** viewer to expose different data sets related to the SMB protocol such as the **File Sharing Perf SMB2/SMB** and **File Sharing SMB/SMB2** view **Layouts**. A particularly useful viewing configuration for analyzing SMB data might be to employ the viewers and **Layouts** that are specified in the table that follows.  
  
### Table 13. Interactive Viewing Configuration Example for SMB Data  
  
|||  
|-|-|  
|**Viewer**|**Layout**|  
|Analysis Grid|File Sharing Perf SMB2/SMB|  
|Grouping|File Sharing SMB/SMB2|  
|Chart|SMB File Stats|  
  
 With this viewing configuration, you can redock the **SMB File Stats** view **Layout** for **Charts** next to the **Analysis Grid** viewer, and then select group nodes in the **Grouping** viewer to simultaneously drive the display of associated messages in the **Analysis Grid** viewer and related rows of data in the **SMB File Stats** view **Layout**. Conversely, you can also select a row of data in the **SMB File Stats** view **Layout** and automatically detect and highlight the messages associated with a particular SMB file operation in the **Analysis Grid** viewer. In addition, message fields and values in the **Details** **Tool Window** snap to whatever message selections are made through these interactions. In each case, you can obtain focused analysis environments for correlating different aspects of the data.  
  
---  
  
 **More Information**   
 **To learn more** about interactively analyzing SMB data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **File Sharing Perf SMB2/SMB** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **File Sharing SMB/SMB2** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **File Sharing SMB Perf** **Profile** in the table of this topic to review a related usage scenario and brief analysis example.  
---