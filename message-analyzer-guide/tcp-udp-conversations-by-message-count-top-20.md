---
title: "TCP-UDP Conversations by Message Count Top 20 | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44f06567-4d6a-4889-933c-f669f64c417d
caps.latest.revision: 25
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# TCP-UDP Conversations by Message Count Top 20
The **TCP/UDP Conversations by Message Count Top 20** viewer **Layout** for **Charts** provides a summary of the top Transport Layer conversations that took place within the time boundaries of a set of trace results. The summary data is provided in **Bar** element visualizer component and label format for the top 20 Transport Layer conversations in a trace that displays the IP addresses of the communicating computers, the TCP/UDP communication ports and module ports that the messages transited in each conversation, and the number of messages exchanged in each conversation. A scale is also provided to the right of the bar elements of the **Layout** that indicates the relative percent volume of messages for each conversation bar with respect to the overall top 20 conversations message count.  
  
## Using the TCP/UDP Conversations by Message Count Top 20 Layout  
 To maximize analysis effectiveness, you should apply the **Transport Layers UDP/TCP** **Viewpoint** to the **Layout**, which removes all messages above the Transport Layer. When you apply this **Viewpoint** from the **Viewpoint** drop-down list on the Filtering toolbar, the values for message count in each conversation can change, as the data will now be based on TCP and UDP messages only. However, by applying this **Viewpoint**, you will create  focused set of message data for analysis.  
  
 Statistics that you can obtain from this **Layout** that are useful in troubleshooting the Transport Layer include:  
  
-   Message volume per conversation  
  
-   Top bandwidth consumers  
  
-   Relative distribution of message count per Transport Layer conversation as a percentage of all the messages displayed in the **Layout**.  
  
> [!NOTE]
>  You can double-click any bar chart element to display the messages for the associated Transport Layer conversation in the **Analysis Grid** viewer for further analysis.  
  
## See Also  
 [TCP/UDP Conversations by Message Count](tcp-udp-conversations-by-message-count.md)