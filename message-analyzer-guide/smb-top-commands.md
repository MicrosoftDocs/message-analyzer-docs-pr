---
title: "SMB Top Commands | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 9c02abea-33a1-4c59-8f84-bc8d5fe34644
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB Top Commands
The **SMB Top Commands** view **Layout** for **Charts** enables you to obtain a high-level summary view that depicts the relative distribution of traffic volume, from the highest to the lowest volume, for SMB commands in a set of trace results. The **Layout** uses a **Bar** element visualizer component that provides a label to the left of each bar element to display the type of SMB command. Each horizontal graphic bar element in this **Layout** extends to a certain length corresponding to the command volume level and is tagged with a number that represents the total number of a particular type of SMB command.  To the right of each bar element there is also a label that indicates what percent of the total number of SMB commands each bar element represents. In the bottom right sector of the **Layout**, the total number of SMB commands is displayed for the current set of trace results.  
  
 Note that this **Layout** has an **SMB/SMB2** **Viewpoint** applied by default so that you can isolate SMB and SMB2 messages and create a focused  analysis environment with no Application Layer nuances above those messages.  
  
## Using the SMB Top Commands Layout  
 The summary data of this **Layout** enables you to quickly evaluate the SMB commands that are consuming the most bandwidth, as indicated by the longer length bar elements. For example, you could have SMB commands such as **QueryInfo**, **Create**, **Read**, **Close**, **SessionSetup**, **Negotiate**, and others displaying in the **SMB Top Commands** view **Layout** at different volume levels. You might be interested in investigating the source and destination computers that are generating a high volume of Operational messages for a particular type of SMB command. To do this, you can interactively drive the display of messages into a new instance of the **Analysis Grid** viewer by double-clicking any bar element of interest in the **Layout**. Thereafter, you can review the following in the **Analysis Grid** viewer for messages that comprise a particular type of SMB command:  
  
-   The IP addresses of the source and destination computers.  
  
-   Command status, which includes success and failure indications, along with other information in the **Summary** column.  
  
-   Message field names and values in the **Details** **Tool Window**.  
  
## See Also  
 [SMB Top Talkers](smb-top-talkers.md)