---
title: "Top Talkers Top 20 | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c96e51c7-2d45-48eb-817f-fdafb8da416c
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Top Talkers Top 20

The built-in **Top Talkers Top 20** view **Layout** for **Charts** provides a summary of the endpoint  conversation address pairs that had the top message volume in a set of trace results. The summary data is provided in a **Bar** element  visualizer component for the top 20 talkers in a trace and displays the endpoint conversation address pairs and the traffic volume for each pair in a label to the right of the bar elements. A scale is also provided to the far right of the Bar element visualizer that indicates the relative percent volume of messages for each endpoint address pair bar with respect to the overall top 20 talker message count.  
  
## Using the Top Talkers Top 20 Chart  

 To enable you to focus on message volume at different layers, you can set a **Viewpoint** such as **TCP** or **Ethernet**. To apply this **Viewpoint**, click the **Viewpoint** drop-down list on the Filtering toolbar and then select the **TCP** or **Ethernet** item. You will notice that the message count value for the address pair bar elements may change in the **Layout** as you set these **Viewpoints**.  
  
 From this **Layout**, you can obtain statistics such as the following to assist in the troubleshooting process:  
  
-   Message volume per endpoint address pair  
  
-   Top bandwidth/data consumers  
  
-   An at-a-glance assessment of how message volume is distributed across the timeline of a trace, from where you can easily identify the top conversations and the endpoints involved.  
  
> [!NOTE]
>  You can double-click any IP address pair set and display all the messages for that set in the **Analysis Grid** viewer for further analysis.  
  
## See Also  

- [Top Talkers](top-talkers.md)