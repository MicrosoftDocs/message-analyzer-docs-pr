---
title: "PEF-NDIS Fast Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 919ab9fd-eddd-4440-bf2f-575cd8cdeb7c
caps.latest.revision: 35
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# PEF-NDIS Fast Filters

The **Microsoft-PEF-NDIS-PacketCapture** filter driver enables you to select messages from a trace that meet certain criteria. You can select specific message data from a trace by configuring a **Fast Filter** on the **Provider** tab of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, which is accessible by clicking the **Configure** link to the right of the provider **Id** in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. Messages that pass the filtering criteria are then passed to Message Analyzer Runtime processing. Driver-level filtering can lower system loads by passing less data, reducing CPU processing, and writing fewer events, which prevents costly disk I/O.  Driver filtering enables significant improvements in speed over copying messages to the Runtime and then filtering with its parsing engine.  
  
> [!TIP]
>  Following the use of a **Fast Filter** in a Live Trace Session, you still have the option to further filter your trace results with a view **Filter**, for analysis purposes. You can specify a view **Filter** from the Filter panel **Library** that displays when you click  **Add Filter** in the **Add Filter** drop-down list on the Filtering toolbar.  
  
 The different types of **Fast Filters** for the **Microsoft-PEF-NDIS-PacketCapture** provider are described in the following topics:  
  
---  
  
[OLP Filters](olp-filters.md)   
[LinkLevelAddress Filters](linkleveladdress-filters.md)   
[IPv4Address Filters](ipv4address-filters.md)   
[IPv6Address Filters](ipv6address-filters.md)   

---  
  
 By using these filters, you can direct the **Microsoft-PEF-NDIS-PacketCapture** provider to isolate message traffic based on values of specific types of addresses or offset length patterns (OLPs).  
  
---  
  
 **More Information**   
 **To learn more** about the settings for **Microsoft-PEF-NDIS-PacketCapture** **Fast Filters**, see the [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).  
**To learn more** about **Fast Filter** configuration capabilities, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).   

---