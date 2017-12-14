---
title: "Microsoft-PEF-NDIS-PacketCapture Provider | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15046768-0fbb-493d-ad8c-2d2ae44060a6
caps.latest.revision: 56
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Microsoft-PEF-NDIS-PacketCapture Provider
The **Microsoft-PEF-NDIS-PacketCapture** filter driver is primarily used by the Message Analyzer **Local Network Interfaces** **Trace Scenario** on computers running the Windows 7, Windows 8, and Windows Server 2012 operating systems. It is instrumented to work with the ETW infrastructure, which provides the mechanisms for controlling ETW Sessions, buffering data, and delivering captured events to a consumer. Because the **Microsoft-PEF-NDIS-PacketCapture** filter driver works with this infrastructure, it can deliver the frames it captures as ETW events. In addition to enabling the capture of frames, the **Microsoft-PEF-NDIS-PacketCapture** provider also inspects and infuses frames at the Data Link miniport level. Each network interface is represented by a miniport driver that performs Data Link Layer frame operations.  
  
## Provider Functions  
 The **Microsoft-PEF-NDIS-PacketCapture**<sup>1</sup> provider is a light-weight filter (LWF) Network Driver Interface Specification (NDIS) driver that uses the Data Link Layer as its entry point into the message stack. It captures frames at the Data Link Layer and stack messages above that level, in addition to low level events from the underlying ETW provider with which the **Microsoft-PEF-NDIS-PacketCapture** driver is instrumented. Because it is instrumented for ETW, the **Microsoft-PEF-NDIS-PacketCapture** provider can take advantage of the ETW infrastructure to deliver its events and messages to an enabling ETW Session. The ETW Session model consists of interaction between the following three components:  
  
-   ETW Event Provider  
  
-   ETW Session Controller  
  
-   ETW Event Consumer  
  
 The ETW event provider in this model is the **Microsoft-PEF-NDIS-PacketCapture** filter driver, while the ETW event consumer is the Protocol Engineering Framework (PEF) Runtime, which parses/processes the message and event data that is delivered by the  **Microsoft-PEF-NDIS- PacketCapture** provider and exposes the processed data in an API that the Message Analyzer user interface (UI) consumes for   the display of data.  
  
## Associated Trace Scenarios  
 The **Microsoft-PEF-NDIS-PacketCapture** provider is used in the following Message Analyzer **Trace Scenarios**, where each scenario has a different capture focus. The **Microsoft-PEF-NDIS-PacketCapture** provider is available in these scenarios on computers running the Windows 7, Windows 8, or Windows 2012 operating system only:  
  
-   **Local Network Interfaces**  
  
-   **VPN**  
  
-   **Wired Local Area Network**  
  
-   **Wireless Local Area Network**  
  
## Provider Fast Filtering Configurations  
 The **Microsoft-PEF-NDIS-PacketCapture** driver also provides a filtering mechanism known as **Fast Filters**. These filters enable you to apply frame filtering based on offset length patterns (OLPs), MAC addresses (LinkLevelAddress), and IP addresses. Because **Fast Filters** operate at the driver level, they are typically very efficient and performant. However, a disadvantage of these filters is that you cannot recover any data that was filtered out of a Live Trace Session by a **Fast Filter**. **Fast Filters** for the **Microsoft-PEF-NDIS-PacketCapture** provider are described in [PEF-NDIS Fast Filters](pef-ndis-fast-filters.md).  
  
> [!TIP]
>  One exception to recovering data that was previously filtered-out is when you have a Message Analyzer Data Retrieval Session in which a **Session Filter** was applied. In this case, after you load data into Message Analyzer with a **Session Filter** applied, you can reopen the session configuration and remove the existing **Session Filter** and then reload the data with no filtering applied,  as described in [Editing Existing Sessions](editing-existing-sessions.md).  
  
 You can specify up to three **Fast Filters** in two logically chained Groups for any Live Trace Session that uses the **Microsoft-PEF-NDIS-PacketCapture** provider. Note that you can use up to four **Fast Filters** for Live Trace Sessions that use the **Microsoft-PEF-WFP-MessageProvider**. Frames that pass the **Fast Filter** criteria are delivered to the enabling ETW Session as events.  
  
 When configuring a Live Trace Session that uses the **Microsoft-PEF-NDIS-PacketCapture** provider, you can specify **Fast Filter** settings on the **Provider** tab of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, which is accessible by clicking the **Configure** link next to the provider **Id** (GUID) in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. You can access this dialog from the Message Analyzer **File** menu, the global Message Analyzer toolbar, or from the **Start Page**.  
  
## Event Keyword and Error Level Filtering  
 Similar to other system ETW providers that are registered on your system, you have the option to specify ETW event **Keyword** configurations and **Level** filter settings for the **Microsoft-PEF-NDIS-PacketCapture** provider, to further refine the scope of events to be captured. The settings for these filters are available on the **ETW Core** tab of the **Advanced Settings – Microsoft-PEF-NDIS-PacketCapture** dialog. By default, all events are delivered by the **Microsoft-PEF-NDIS-PacketCapture** provider when no **Keywords** are selected. If you specify any particular **Keyword**, then the provider will deliver the events that are enabled by that **Keyword** only, if they occur in a trace. It also follows that multiple events are delivered when multiple **Keywords** are selected.  
  
---  
  
 **More Information**   
 **To learn more** about configuring system ETW Providers, including event **Keyword** and error **Level** filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
**To learn more** about configuring PEF providers, including setting **Fast Filters** for the **Microsoft-PEF-NDIS-PacketCapture** provider, see the following topics:   
[Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md)  
[Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md)  
**To learn more** about the ETW session model, see the [ETW Framework Conceptual Tutorial](etw-framework-conceptual-tutorial.md).   
---  
  
 <sup>1</sup> Computers that are running the Microsoft Windows 8 and Microsoft Windows Server 2012 64-bit operating systems use the Microsoft-PEF-NDIS-PacketCapture v6.3 provider. Computers running the Microsoft Windows 7 operating system or the 32-bit version of the Microsoft Windows 8 operating system use the Microsoft-PEF-NDIS-PacketCapture v6.0 provider. Computers running the Microsoft Windows 8.1, Windows Server 2012 R2, Windows 10, and later operating systems use the Microsoft-Windows-NDIS-PacketCapture (NDISCAP) provider only, which has remote capabilities.  
  
## See Also  
 [Built-In Trace Scenarios](built-in-trace-scenarios.md)   
 [Microsoft-PEF-WFP-MessageProvider](microsoft-pef-wfp-messageprovider.md)   
 [Microsoft-PEF-WebProxy Provider](microsoft-pef-webproxy-provider.md)