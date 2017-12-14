---
title: "Microsoft-PEF-WebProxy Provider | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5a6d8ca-b3fe-4dad-b205-56b67b8fe7a6
caps.latest.revision: 34
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Microsoft-PEF-WebProxy Provider
The **Microsoft-PEF-WebProxy** provider enables you to focus on capturing traffic at the Application layer of the network stack.  It is based on Fiddler and enables you to capture unencrypted HTTP traffic  to and from a client web browser on computers running the Windows 7 and later operating systems. However, the **PEF-WebProxy** provider will not capture unencrypted HTTP browser traffic unless you configure **Internet options** to use a proxy server for the LAN.  
  
> [!IMPORTANT]
>  To use the **PEF-WebProxy** provider, you must have the Fiddler library from Telerik installed. If you have not already installed this library, you can download it [here](http://fiddler2.com/fiddlercore). Note that if you select the **WebProxy** provider without having this library installed when you are configuring a Live Trace Session, or when specifying it in a PowerShell script, you will receive an error message that asks you to download the Fiddler library.  
  
## Provider Functions  
 The **Microsoft-PEF-WebProxy** provider is used by the Message Analyzer **Pre-Encryption for HTTPS** **Trace Scenario** to capture client browser traffic. When you use this provider, it also installs and registers the HTTP proxy on the machine that is running Message Analyzer, where it is configured as a system proxy for Microsoft Windows Internet (WinInet) Services. The HTTP proxy is then substituted for the proxy server when a trace is started so that it can intercept and capture unencrypted HTTPS traffic. The proxy server target is restored when the trace is complete.  
  
 As the system proxy, all HTTPS requests from WinInet flow through the HTTP proxy before reaching target web servers. Similarly, all HTTPS responses flow through the HTTP proxy before being returned to the client application.  
  
## Provider Filtering Configurations  
 The settings that you can configure for the **WebProxy** provider are described in [WebProxy Filters](webproxy-filters.md). This includes settings that you can specify for **Hostname Filter** and **Port Filter** in the **Advanced Settings-Microsoft-Pef-WebProxy** dialog. In addition, you have the option to specify **HTTPS Client Certificate** information in this dialog as well, which includes the capability to reuse client and server connections.  
  
## Event Keyword and Error Level Filtering  
 Similar to other system ETW providers that are registered on your system, you have the option to specify ETW event **Keyword** configurations and error **Level** filter settings for the **Microsoft-Pef-WebProxy** provider, to further refine the scope of events to be captured. The settings for these filters are available on the **ETW Core** tab of the **Advanced Settings – Microsoft-Pef-WebProxy** dialog. By default, all events are delivered by the **Microsoft-Pef-WebProxy** provider when no **Keywords** are selected. If you specify a particular **Keyword**, then the provider will deliver the events that are enabled by that **Keyword** only, if they occur in a trace. It also follows that multiple events are delivered when multiple **Keywords** are selected.  
  
---  
  
 **More Information**   
 **To learn more** about configuring system ETW Providers, including event **Keyword** and error **Level** filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
**To learn more** about configuring PEF providers, including filters for the **Microsoft-PEF-WebProxy** provider, see the following topics:   
[Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md)  
[WebProxy Filters](webproxy-filters.md)  
---  
  
## See Also  
 [Built-In Trace Scenarios](built-in-trace-scenarios.md)   
 [Microsoft-PEF-NDIS-PacketCapture Provider](microsoft-pef-ndis-packetcapture-provider.md)   
 [Microsoft-PEF-WFP-MessageProvider](microsoft-pef-wfp-messageprovider.md)