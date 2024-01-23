---
title: "Top Talkers | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c356042-2621-4666-866c-0ff7526559fd
caps.latest.revision: 19
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Top Talkers

The built-in **Top Talkers** view **Layout** for **Chart** provides a summary of the endpoint conversation address pairs that had the top message volume and payload bytes values in a set of trace results. This **Layout** also displays additional statistics that provide an indication of the data transmission rate and the distribution of network busyness with respect to traffic volume and duration for each endpoint address pair. The summary data is contained in a **Table** grid visualizer component that provides endpoint address pairs, message and byte count, and other traffic details in a column layout that is tailored to provide statistics that are useful for analysis. The grid data is sorted in descending order from the highest to lowest message count and by highest to lowest payload byte count. The **Layout** contains the following data columns:  
  
-   **AddressPair** — values in this column specify the endpoint address set for which traffic statistics are generated.  
  
-   **Count** — values in this column specify the total volume of messages for each endpoint address.  
  
-   **Bytes** — based on the `payloadLength` property of any module that defines this field, the values in this column specify the total payload byte volume of all messages (containing this property) that are associated with each endpoint address.  
  
-   **KBPS** — provides an indication of the data transmission rate in kilobytes per second.  
  
-   **Duration** — specifies the delta between the **Start** and **End** time values.  
  
-   **Start** — specifies the time at which the first message in an endpoint address pair set began.  
  
-   **End**— specifies the time at which the last message in an endpoint address pair set ended.  
  
-   **K** — a chart constant to facilitate calculation of the KBPS values.  
  
-   **BPS** — provides an indication of the data transmission rate in bytes per second.  
  
## Using the Top Talkers Layout  

 To enable you to focus on message volume and payload byte count at different layers, you can set a **Viewpoint** such as **TCP** or **Ethernet**. To apply a **Viewpoint**, click the **Viewpoint** drop-down list on the Filtering toolbar and then select the **TCP** or **Ethernet** item. You will notice that values such as the message count, payload byte count, and data transmission rates may change in the **Layout** as you set these **Viewpoints**.  
  
 From this **Layout**, you can obtain statistics such as the following to assist in the troubleshooting process:  
  
-   Message volume per endpoint address pair.  
  
-   Top bandwidth/data consumers  
  
-   Traffic density in terms of payload byte count per endpoint address pair  
  
-   Data transmission rates for each endpoint address pair  
  
> [!NOTE]
>  You can double-click any IP **AddressPair** set and display all the messages for a particular set in the **Analysis Grid** viewer for further analysis.  
  
## See Also  

[Top Talkers Top 20](top-talkers-top-20.md)