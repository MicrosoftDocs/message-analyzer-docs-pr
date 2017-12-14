---
title: "TCP Stevens Graph | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 99529411-be1f-499b-be09-1562c25e49e2
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# TCP Stevens Graph
The built-in **TCP Stevens Graph** view **Layout** for **Charts** provides a graph of TCP sequence numbers versus time, along with a **Source Diagnoses** statistics table, which together can reveal certain patterns that indicate specific TCP traffic issues. The data provided by this chart can help you determine whether or not TCP traffic is transiting freely without interruptions, significant delays, or loss of packets.  
  
 The graphic portion of the **TCP Stevens Graph** view **Layout** consists of IP conversation lines of connected message nodes that correlate with y-axis sequence numbers, while the x-axis is calibrated to show message timestamps. You can click a conversation line to view the dispersion of message nodes and then hover over any message node with your mouse to see details such as the endpoints that participated in the IP conversation, the message module, source and destination ports, the timestamp, and a sequence number suffix in the current series. You can also zoom into the conversation lines to obtain greater resolution for analysis purposes. The standard zoom presets that come with Message Analyzer timeline visualizers are included. Lastly, you can hide or display conversation lines in the **TCP Stevens Graph** by unselecting or selecting the check boxes, respectively, in the legend to the right of the **TCP Stevens Graph**.  
  
## Understanding the Source Diagnoses Information  
 The **Source Diagnoses** table provides supplementary information that enhances your graphic chart analysis by providing you with statistics that show the IPv4 and IPv6 conversations that took place, the associated port numbers, the message count in each conversation segment, the number of diagnosis messages that occurred in each conversation segment, and a decimal value that expresses the ratio of the number of diagnosis messages to the total number of messages in each conversation segment. Note that the Message Analyzer **Grouping** feature is applied behind the scenes in this chart to create the IP conversation groups. This data is presented in tabular form by the columns of information indicated below:  
  
> [!NOTE]
>  Observe that the graphic portion of the **TCP Stevens Graph** view **Layout** shows IP conversation *segments*, for example: a request/response pair can display as two separate segments; the graph legend correlates the conversation groups; and the **Source Diagnoses** table breaks the conversation groups into conversation segments for analysis.  
  
-   **Source** — specifies the IP addresses of source computers that participated in IP conversations.  
  
-   **Destination** — specifies the IP addresses of destination computers that participated in IP conversations.  
  
-   **SourcePort** — specifies the computer source ports that carried messages in an IP conversation.  
  
-   **DestinationPort** — specifies the computer destination ports that carried messages in an IP conversation.  
  
-   **Rate** — specifies the ratio of the number of diagnosis messages to the total message count for an IP conversation segment. This value measures diagnosis error messages as a fraction of the total message count. A high **Rate** value can be an indication of TCP issues such as retransmits, duplicate ACKs, lost segments, dropped packets, application glitches, and so on.  
  
-   **Count** — indicates the total number of messages in each IP conversation segment. This value is also reflected in the **Stevens** graph as the number of message nodes that display when you click a IP conversation segment line in the graph.  
  
-   **Diagnoses** — indicates the total number of diagnosis messages in each IP conversation segment. The higher this number, the more TCP issues are present in a particular conversation.  
  
## Using the TCP Stevens Graph Layout  
 As indicated at the bottom of this chart, you should apply the **TCP** **Viewpoint** to this **Layout** to isolate TCP messages at top level with no messages above it, so that you can analyze your trace data from the perspective of TCP. To apply the **TCP** **Viewpoint**, click the **Viewpoint** drop-down list on the Filtering toolbar and then select the **TCP** item in the list. By applying this **Viewpoint**, the **TCP Stevens Graph** will be redrawn with data that is filtered by the **TCP** **Viewpoint** and the **Source Diagnoses** table will be appropriately repopulated with the filtered data. You can then begin analysis of values for signs of TCP traffic issues. Some typical patterns that you might encounter with the use of this **TCP Stevens Graph** and the issues they can expose consist of the following:  
  
-   Long gaps between message sequence numbers can indicate times when TCP message throughput is low or nonexistent.  
  
-   Long intervals between message nodes/sequence numbers can indicate transmission delays.  
  
-   Conversation segment lines that have a more vertical orientation with message nodes in close proximity on the lines indicate traffic is moving quickly. This is the ideal case.  
  
-   Conversation segment lines with a more horizontal orientation where message nodes are not in close proximity indicate it is taking more time for messages to transit. This is the problem case.  
  
-   Because the **Source Diagnoses** table indicates traffic in two directions, you can correlate the associated source and destination traffic with conversation segment lines in the **TCP Stevens Graph**, to determine whether traffic is moving faster or slower in one direction or the other.  
  
> [!NOTE]
>  You can double-click a **Source Diagnoses** table row to display the associated messages in a separate **Analysis Grid** viewer tab.