---
title: "NTP Time Offset | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f917c457-33dc-41de-a804-546765a45b15
caps.latest.revision: 9
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# NTP Time Offset

The **NTP Time Offset** view **Layout** for the  **Chart** viewer  enables you  to observe Time Offset data over the timeline of a set of trace results per network conversation, which you can select in a legend to the right of the **Timeline** graphic visualizer component. This will help you understand time offset from the network perspective and to troubleshoot time-related issues. This view **Layout** is accessible from the **Chart** drop-down list that appears when you click **Chart** in the **New Viewer** list on the global Message Analyzer toolbar.  
  
 Message Analyzer also provides a **Profile** that displays the **NTP Time Offset** view **Layout** for the  **Chart** viewer by default whenever you load a \*.cap, \*.pcap, \*.etl, or \*.pcapng file while the **NTP Time Offset** **Profile** is enabled in the **Options** dialog. This dialog is accessible from the global Message Analyzer **Tools** menu. The **NTP Time Offset** **Profile** also configures the **NTP Time Offset** **Layout** for the **Analysis Grid** viewer  and the **NTP Source** **Layout** for the **Grouping** viewer. However, you will need to manually select these **Layouts** as the **Default** in the respective **Layout** lists for these viewers in the **New Viewers** drop-down list on the global Message Analyzer toolbar. Note that these viewers are integrated and interactive so that you can correlate the data through the different viewing perspectives that they create.  
  
> [!NOTE]
>  To obtain meaningful results with the **NTP Time Offset** view **Layout**, the above supported  file types must contain time offset data that is captured by the **NTP** module.  
  
---  
  
 **More Information**   
 **To learn more** about the Message Analyzer **Profiles**, see  [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md).  

---