---
title: "SMB Top Talkers | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: da5907fe-4edb-4bc6-a5d3-77157bc0362d
caps.latest.revision: 14
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB Top Talkers
The **SMB Top Talkers** view **Layout** for **Charts** provides statistical summary data  for the top IP conversations in a set of trace results. It enables you to obtain statistics such as the message count, conversation payload length in bytes, data transmission rate, conversation duration, and others, for the top IP conversations (denoted by address pairs) in a set of trace results. The **Layout** uses a **Table** grid visualizer component that provides this information in the following columns of data:  
  
-   **AddressPair** — specifies the IP address of the computers that participated in an IP  conversation.  
  
-   **Count** — specifies the number of messages that were exchanged in each conversation.  
  
-   **Bytes** — based on the **PayloadLength** property of any module that defines this field, the values in this column specify the total payload byte volume of all messages (containing this property) that are associated with each IP conversation.  
  
-   **KBPS** — provides an indication of the data transmission rate in kilobytes-per-second for the messages in an IP conversation.  
  
-   **Duration** — specifies the delta between the **StartTime** and **EndTime** values.  
  
-   **StartTime** — specifies the time at which the first message in a conversation group began.  
  
-   **EndTime** — specifies the time at which the last message in a conversation group ended.  
  
-   **K** — a chart constant to facilitate calculation of the KBPS values; can be ignored.  
  
-   **BPS** — provides an indication of the data transmission rate in bytes-per-second for the messages in an IP conversation.  
  
 This **Layout** also contains an `SMB or SMB2` view **Filter** that is automatically applied in the background in order to focus the results on SMB and SMB2 messages only.  
  
## Using the SMB Top Talkers Layout  
 The statistics  you can obtain from this **Table** visualizer component that are useful in troubleshooting the SMB/SMB2 protocols include:  
  
-   Message volume per conversation  
  
-   Top bandwidth consumers  
  
-   Data transmission rates  
  
-   The time taken to complete conversations  
  
 **Interactive Analysis**   
This **Layout** is intended to work with the **SMB Flat** view **Layout** of the **Analysis Grid** viewer and the **File Sharing SMB/SMB2** view **Layout** of the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in all four of the **File Sharing SMB** **Profiles** and will display after you  load data from a .cap, .etl, .pcapng, or .pcap file, provided that you enabled the appropriate **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 For example, to interactively analyze SMB and SMB2 messages, you can  drive the display of these messages into the **Analysis Grid** viewer by double-clicking any row of data for a particular conversation in the **SMB Top Talkers** view **Layout**. Thereafter, you can review SMB status information for any message in the **Summary** column of the **Analysis Grid** viewer along with message fields and values in the **Details** **Tool Window**. The **File Sharing SMB/SMB2** **Layout** for the **Grouping** viewer also enables a greater interactive context with additional enhancements to the analysis process.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about interactively analyzing SMB/SMB2 data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **SMB Flat** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **File Sharing SMB/SMB2** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **File Sharing SMB** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  
___________________\_  
  
## See Also  
 [SMB Top Commands](smb-top-commands.md)