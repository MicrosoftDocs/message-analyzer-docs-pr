---
title: "IP Ethernet Conversations by Message Count Top 20 | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93c6538c-cfcd-41bd-b542-d3b20051f44d
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# IP Ethernet Conversations by Message Count Top 20
The **IP/Ethernet Conversations by Message Count Top 20** viewer **Layout** for **Charts** provides a summary of the top Network layer conversations that took place within the time boundaries of a set of trace results. The summary data for this **Layout** is provided in a **Bar** element visualizer component that displays the IP addresses of communicating computers and the number of messages exchanged in each conversation for the top 20 Network layer conversations in a trace. A scale is also provided to the right of the bar element graph that indicates the relative percent volume of messages for each bar element with respect to the overall top 20 conversations message count.  
  
## Using the IP/Ethernet Conversations by Message Count Top 20 Layout  
 To maximize analysis effectiveness, you should apply the **Network** **Viewpoint** to this **Layout**, which removes all messages above the Network layer. When you apply this **Viewpoint** from the **Viewpoint** drop-down list on the Filtering toolbar, the **Layout** values will then be based on IP and Ethernet messages only. This can result in changing the number of messages associated with one or more conversations.  
  
 Statistics that you can obtain from this **Layout** that are useful in troubleshooting the Network layer include:  
  
-   Message volume per conversation  
  
-   Top bandwidth consumers  
  
-   Relative distribution of message count per conversation as a percentage of all the messages displayed in the **Layout**.  
  
> [!NOTE]
>  You can double-click any bar element in the **Layout** to display the messages for the associated conversation in the **Analysis Grid** viewer for further analysis.  
  
## See Also  
 [IP/Ethernet Conversations by Message Count](ip-ethernet-conversations-by-message-count.md)