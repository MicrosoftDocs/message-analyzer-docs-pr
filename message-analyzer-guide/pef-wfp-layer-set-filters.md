---
title: "PEF-WFP Layer Set Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5242b85e-6463-4a03-86a6-23af42457e81
caps.latest.revision: 28
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# PEF-WFP Layer Set Filters
When configuring  settings for the **Microsoft-PEF-WFP-MessageProvider** in **Trace Scenarios** that use it, you can create a **WFP Layer Set** filter configuration that enables you to directionally isolate inbound or outbound TCP packets at the Transport layer for IPv4 or IPv6 traffic. You can access the configuration for the **WFP Layer Set** filters on the **Provider** tab of the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog, which is accessible by clicking the **Configure** link to the right of the **Id** for the  **Microsoft-PEF-WFP-MessageProvider** in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog, which is accessible from the Message Analyzer **File** menu, the **Start Page**, or the global Message Analyzer toolbar. The **WFP Layer Set** contains the following filters, which you can enable or disable, respectively, by selecting or unselecting filter check boxes as appropriate:  
  
-   INBOUND_TRANSPORT_V4  
  
-   OUTBOUND_TRANSPORT_V4  
  
-   INBOUND_TRANSPORT_V6  
  
-   OUTBOUND_TRANSPORT_V6  
  
 These filters are kernel mode TCP/IP stack filters that operate in the receive or send path (inbound or outbound, respectively) at the Transport Layer before any processing occurs at that layer. When set, these filters selectively enable or disable the capture of all inbound, outbound, or bidirectional packet traffic at the Transport Layer.  
  
## Capturing Loopback Traffic  
 If you are capturing loopback (local application) traffic, you should disable either inbound or outbound traffic with **WFP Layer Set** filters in the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog, as the default configuration of the **Local Loopback Network** **Trace Scenario** does; otherwise, you will get duplicate messages. However, for regular network traffic, you should always enable both inbound and outbound packet directions.  
  
---  
  
 **More Information**   
 **To learn more** about configuring **WFP Layer Set** filters for the **Microsoft-PEF-WFP-MessageProvider**, see the [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).   
---