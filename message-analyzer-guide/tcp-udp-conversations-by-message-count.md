---
title: "TCP-UDP Conversations by Message Count | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f9fea45-7cab-4a83-b0ba-fb275371a59f
caps.latest.revision: 22
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# TCP-UDP Conversations by Message Count

The **TCP/UDP Conversations by Message Count** viewer **Layout** for **Charts** provides a summary of the top Transport Layer conversations that took place within the time boundaries of a set of trace results. The summary data is provided in a **Table** grid visualizer component to expose message details and useful statistics for the top Transport Layer conversations that took place in a set of trace results. The data is sorted in descending order from the highest to lowest message count, per conversation. The grid layout contains the following data columns:  
  
-   **Network** — contains the IPv4, IPv6, and Ethernet addresses of the computer nodes that exchanged messages in each conversation in a set of trace results.  
  
-   **Transport** — contains the TCP or UDP ports that carried the conversations.  
  
-   **Count** — specifies the number of messages that were exchanged in each conversation.  
  
-   **Bytes** — based on the `payloadLength` property of any module that defines this field, the values in this column specify the total payload byte volume of all messages (containing this property) that are associated with each conversation.  
  
-   **KBs** — provides an indication of the data transmission rate in kilobytes-per-second.  
  
-   **Duration** — specifies the delta between the **StartTime** and **EndTime** values, which calculates the duration of each conversation in  a set of trace results.  
  
-   **StartTime** — specifies the time at which the first message in a conversation group began.  
  
-   **EndTime** — specifies the time at which the last message in a conversation group ended.  
  
-   **BPS** — provides an indication of the data transmission rate in bytes-per-second.  
  
-   **K** — a chart constant to facilitate calculation of the KBs values.  
  
## Using the TCP/UDP Conversations by Message Count Layout  

 To maximize analysis effectiveness at the Transport Layer, the **Transport Layers TCP/UDP** **Viewpoint** has been applied to this **Layout** by default, which removes all messages above the Transport Layer. You can observe evidence of this background configuration in the **Viewpoints** drop-down list on the Filtering Toolbar, where you will see that the **Layout ViewPoint** item is selected, that is, after you display the **TCP/UDP Conversations by Message Count** **Layout**. As a result of this applied **Viewpoint**, the values in columns such as **Count**, **Bytes**, **KBs**, and **BPS**, will be based on top-level TCP and UDP messages only. For example, the **Count** column will then indicate the number of top-level TCP or UDP messages in each conversation, while the **Bytes** column will indicate the number of TCP or UDP payload bytes exchanged in each conversation. Note that you can also isolate conversations by TCP or UDP messages if you apply a **TCP** or **UDP** **Viewpoint**, respectively.  
  
 Statistics that you can obtain from this **Layout** that are useful in troubleshooting the Transport Layer include:  
  
-   TCP message volume per conversation  
  
-   Payload volume per conversation  
  
-   Data transmission rates per conversation  
  
-   Duration per conversation  
  
 **Interactive Analysis**   
The **TCP/UDP Conversations by Message Count** view **Layout** for **Charts** is intended to work with the **Analysis Grid** viewer and **Grouping** viewer **Layouts** that are configured in all of the  **Performance Top Down** and **Network Monitor** **Profiles**. These **Profiles** create an interactive and integrated analysis environment for data that exists in various trace file types, for which **Profiles** are configured. For example, the **Performance Top Down** **Profile** for \*.cap files uses the following data viewers and **Layouts** to create an integrated analysis environment.  
  
-   **Analysis Grid** viewer — uses the **Performance Top Down** **Layout** in this **Profile**.  
  
-   **Grouping** viewer — uses the **Process Names and Conversations** **Layout** in this **Profile**.  
  
-   **Chart** viewer — uses the **TCP/UDP Conversations by Message Count** **Layout** in this **Profile**.  
  
 You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. For example, you can interactively drive the display of messages associated with a particular TCP conversation into a new instance of the **Analysis Grid** viewer by double-clicking any table-grid row in the **TCP/UDP Conversations by Message Count** **Layout**. The results enable you to achieve a focused analysis of the messages associated with a particular conversation. The  **Process Names and Conversations** **Layout** for the **Grouping** viewer also enables a greater interactive context with additional enhancements to the analysis process.  
  
---  
  
 **More Information**   
 **To learn more** about the integrated analysis environments that are created by the **Profiles** that use the  **TCP/UDP Conversations by Message Count** view **Layout** for **Charts**, see the **Performance Top Down** and **Network Monitor** **Profiles** in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic. Note that you can also review related usage scenarios and analysis examples for the **Profiles** in this topic.  

---  
  
## See Also  

- [TCP/UDP Conversations by Message Count Top 20](tcp-udp-conversations-by-message-count-top-20.md)