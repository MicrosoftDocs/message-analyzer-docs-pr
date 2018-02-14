---
title: "IP-Ethernet Conversations by Message Count | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1cb7ad39-95fc-40e8-a135-350e15e938c3
caps.latest.revision: 15
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# IP-Ethernet Conversations by Message Count

The **IP/Ethernet Conversations by Message Count** viewer **Layout** for **Charts** provides a summary of the top Network layer conversations that took place within the time boundaries of a set of trace results. The summary data is presented in a **Table** grid visualizer component that provides message details in tabular format and exposes useful statistics for the top Network layer conversations that took place in a set of trace results. The data is sorted in descending order from the highest to lowest message count, per conversation. The **Table** grid contains the following data columns:  
  
-   **Network** — contains the IP or Ethernet addresses of the computer nodes that exchanged messages.  
  
-   **Count** — specifies the number of messages that were exchanged in each conversation.  
  
-   **Bytes** — based on the `payloadLength` property of any module that defines this field, the values in this column specify the total payload byte volume of all messages (containing this property) that are associated with each Network conversation.  
  
-   **KBs** — provides an indication of the data transmission rate in kilobytes-per-second for the messages in a conversation.  
  
-   **Duration** — specifies the delta between the **StartTime** and **EndTime** values.  
  
-   **StartTime** — specifies the time at which the first message in a conversation group began.  
  
-   **EndTime**— specifies the time at which the last message in a conversation group ended.  
  
-   **BPS** — provides an indication of the data transmission rate in bytes-per-second for the messages in a conversation.  
  
-   **K** — a chart constant to facilitate calculation of the KBs values.  
  
## Using the IP/Ethernet Conversations by Message Count Layout  

 To maximize analysis effectiveness, you should apply the **Network** **Viewpoint** to this **Layout**, which removes all messages above the Network layer. When you apply this **Viewpoint** from the **Viewpoint** drop-down list on the Filtering toolbar, the values in columns such as **Count**, **Bytes**, **KBs**, and **BPS**, will then be based on IP and Ethernet messages only. For example, the **Count** column will then indicate the number of IP or Ethernet messages in each conversation, while the **Bytes** column will indicate the number of IP or Ethernet payload bytes exchanged in each conversation.  
  
 Statistics that you can obtain from this grid visualizer component that are useful in troubleshooting the Network layer include:  
  
-   Message volume per conversation  
  
-   Top bandwidth consumers  
  
-   Data transmission rates  
  
-   Time to complete conversations  
  
> [!NOTE]
>  You can double-click any conversation row in the grid to display the messages for the associated conversation in the **Analysis Grid** viewer for further analysis.  
  
## See Also  

[IP Ethernet Conversations by Message Count Top 20](ip-ethernet-conversations-by-message-count-top-20.md)