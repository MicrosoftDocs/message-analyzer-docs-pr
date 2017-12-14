---
title: "PEF Message Providers | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0232b3d1-5675-418b-bab1-b84776081c42
caps.latest.revision: 35
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# PEF Message Providers
Message Analyzer can make use of many different message providers when capturing data. Certain providers are specifically designed by Microsoft to create inspection points into the network protocol stack so that you can focus on retrieving and analyzing messages at predefined levels. For example, you can use the **Microsoft-PEF-WFP-MessageProvider** to retrieve network traffic above the IP/Network layer while minimizing lower level network noise, so that you can focus on troubleshooting TCP and application messages. You can also use the **Microsoft-PEF-NDIS-PacketCapture** provider to retrieve network traffic on the wire at the Data Link layer to obtain a full representation of all messages captured in a trace. In addition, you can use the **Microsoft-PEF-WebProxy** provider to capture HTTP client browser traffic at the Application Layer, prior to encryption.  
  
 This section briefly describes the functions of Microsoft Protocol Engineering Framework (PEF) providers that are native to Message Analyzer and which enable you to partition the capture of network traffic in the indicated manner. The filters that you can configure for these providers are also described in the sections below:  
  
---  
  
 [Microsoft-PEF-NDIS-PacketCapture Provider](microsoft-pef-ndis-packetcapture-provider.md)   
 [Microsoft-PEF-WFP-MessageProvider](microsoft-pef-wfp-messageprovider.md)   
 [Microsoft-PEF-WebProxy Provider](microsoft-pef-webproxy-provider.md)   

---  
  
> [!TIP]
>  Note that you can also use the **Microsoft-Windows-NDIS-PacketCapture** provider to capture messages locally or remotely at Link Layer.  
  
## About Provider Manifests  
 Each Microsoft PEF provider has an ETW manifest that installs with Message Analyzer. A provider manifest is an XML file that specifies a formal description of the events a provider raises. It identifies the event provider, specifies the event types, and also describes the events.  
  
 A manifest can also associate its events with **Keywords** and **Levels**, which is a way to enable events and filter them as they are written for consumption:  
  
-   **Keywords** — group events together that are logically related.  
  
-   **Level** — indicates the severity or verbosity of an event, for example, critical, error, warning, or informational.  
  
> [!TIP]
>  Keywords are different for many ETW providers. You might therefore consider consulting the community knowledge base for optimized configurations.  
  
 In addition, event consumers such as the PEF Runtime can make use of a manifest’s structured XML data to perform queries and analysis. Manifests for all PEF providers reside in the following location:  
  
 `c:\Windows\System32\`  
  
---  
  
## See Also  
 [Event Manifest](etw-framework-conceptual-tutorial.md#BKMK_EventManifest)