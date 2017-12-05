---
title: "PEF-WFP Dropped Packets | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bafff336-1ec1-470d-a8d4-117be705a16c
caps.latest.revision: 32
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# PEF-WFP Dropped Packets
The **Microsoft-PEF-WFP-MessageProvider** enables you to log dropped packet information, which includes reason and layer statistics. To obtain these statistics, you must select the **Select Discarded Packet Events** check box on the **Provider** tab of the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog. You can access this dialog by clicking the **Configure** link to the right of the **Microsoft-PEF-WFP-MessageProvider** in the **ETW Provider** list on the **Live Trace** tab of the **New Session** dialog, that is, after selecting any **Trace Scenario** that uses the **Microsoft-PEF-WFP-MessageProvider**, for example, the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
 Logged information for discarded packet events consists of dropped packet statistics that are derived from the Discard filter layer of the Statistics callout in the **Microsoft-PEF-WFP-MessageProvider**. Statistics consist of the reason for dropping packets and the layer on which they were dropped. You can view the dropped packet statistics as ETW events in the **Analysis Grid** viewer after a  trace with the **Microsoft-PEF-WFP-MessageProvider** is complete. You can use the **Column Filter** feature for the **Summary** column of the **Analysis Grid** viewer to specify a search term such as "discard" to expose any messages that might indicate that the firewall was involved in blocking traffic. The **Discarded Packet Events** feature can help you troubleshoot whether packets are being dropped by the network, the **Microsoft-PEF-WFP-MessageProvider**, or the firewall.  
  
> [!NOTE]
>  When you select the **Select Discarded Packet Events** check box on the **Provider** tab of the **Advanced Settings** dialog, any **Fast Filters** or **WFP Layer Set** filters that you have specified will not be applied to the discarded packet events.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using **Column Filters**, see [Filtering Column Data](filtering-column-data.md).   
___________________\_