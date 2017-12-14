---
title: "Microsoft-PEF-WFP-MessageProvider | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2bed79eb-c0d5-4e3a-beb0-34d8322af901
caps.latest.revision: 43
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Microsoft-PEF-WFP-MessageProvider
Similar to the **Microsoft-PEF-NDIS-PacketCapture** provider, the **Microsoft-PEF-WFP-MessageProvider** is instrumented to work with the ETW infrastructure, as described in the [ETW Framework Conceptual Tutorial](etw-framework-conceptual-tutorial.md). This infrastructure provides the mechanisms for controlling ETW Sessions, buffering trace data, and delivering events to a consumer. Because the **Microsoft-PEF-WFP-MessageProvider** provider is integrated into this infrastructure, it can deliver the packets that it captures as events. The **Microsoft-PEF-WFP-MessageProvider** also has an option that enables you to log discarded packet events.  
  
## Provider Functions  
 The **Microsoft-PEF-WFP-MessageProvider** is based on the Windows Filtering Platform (WFP) which is typically used to create firewall applications, but in Message Analyzer, it provides an entry point into the stack that enables you to capture traffic above the IP/Network Layer. Capturing message data with the **Microsoft-PEF-WFP-MessageProvider** is less noisy than capturing at the Data Link Layer with either the **Microsoft-PEF-NDIS-PacketCapture** or **Microsoft-Windows-NDIS-PacketCapture** provider, as most low-level and broadcast traffic is ignored in the case of the **PEF-WFP-MessageProvider**. Therefore, with the use of the **Microsoft-PEF-WFP-MessageProvider** you can focus your analysis on messages above the Network Layer. Note that messages at and below the Network Layer in a **Microsoft-PEF-WFP-MessageProvider** capture are typically represented in your trace results as **WFPCapture**, and below that there is an **ETW** layer.  
  
 Although most lower-level noise is removed by the **Microsoft-PEF-WFP-MessageProvider**, other noise can be introduced by this provider in terms of diagnosis errors and loopback traffic. However, you can specifically filter out this noise by configuring **Fast Filters** in the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog, as described in [Provider Fast Filtering Configurations](microsoft-pef-wfp-messageprovider.md#BKMK_ProviderFastFiltering). The provider configuration in this dialog is accessible by clicking the **Configure** link in the **New Session** dialog in **Trace Scenarios** that use this provider.  
  
 The **Microsoft-PEF-WFP-MessageProvider** provides the first entry point (chokepoint) into the network stack above the Data Link Layer in Message Analyzer, which creates a unique inspection point into the stack that enables you to do the following:  
  
-   **Capture loopback traffic** — for example, if you have an HTTP and SQL server on the same machine, you can use the **Local Loopback Network**  **Trace Scenario** to capture communication traffic between these applications, that is, if they are using the loopback IP addresses for such communications.  
  
-   **Capture IPSec/ESP traffic** — in pre-encrypted, encrypted, and decrypted formats, for example, with the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
-   **Capture VPN and Direct Access traffic** — for example, with the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario**.  
  
-   **Capture hardware offload traffic** — offloaded from the network adapter.  
  
-   **Log discarded packet events** — by setting the **Select Discarded Packet Events** option, Message Analyzer can capture packets that are being dropped at the firewall.  
  
-   **Improve performance** — use less Message Analyzer parsing to get at upper-layer protocols.  
  
## Associated Trace Scenarios  
 The **Microsoft-PEF-WFP-MessageProvider** provider is used in the following Message Analyzer **Trace Scenarios**, where each scenario has a different capture focus. Operating system dependencies are also specified where applicable; otherwise, you can assume that the **Microsoft-PEF-WFP-MessageProvider** works in the listed **Trace Scenarios** on Windows 7 and later computers:  
  
-   **Local Loopback Network**  
  
-   **Loopback and Unencrypted IPSEC**  
  
-   **Network Tunnel Traffic and Unencrypted IPSEC**  
  
-   **SASL LDAP pre-encryption with WFP**  
  
-   **SMB Client and Firewall** — on computers running the Windows 8, Windows Server 2012, or Windows 10 operating system.  
  
> [!IMPORTANT]
>  Note that you can use any **Trace Scenario** in which the **Microsoft-PEF-WFP-MessageProvider** exists on computers running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, to capture traffic remotely on computers running the Windows 10 operating system. Capture of remote traffic on target Windows 10 computers is possible because the **Microsoft-PEF-WFP-MessageProvider** is now instrumented to support remote scenarios on Windows 10 computers.  
>   
>  This means that on computers running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, you can successfully launch a remote capture that targets a Windows 10 computer, while on computers with other operating systems earlier than Windows 8.1, you cannot. Conversely, from a computer running the Windows 10 operating system, you cannot capture remote traffic from a computer running the Windows 8.1, Windows Server 2012 R2, or earlier operating system, since the **Microsoft-PEF-WFP-MessageProvider** is not instrumented to support remote scenarios on these computers. Moreover, it is the target computer with the remote-enabled **Microsoft-PEF-WFP-MessageProvider** alone that determines where you can capture remote traffic.  
  
<a name="BKMK_ProviderFastFiltering"></a>   
## Provider Fast Filtering Configurations  
 Similar to the **Microsoft-PEF-NDIS-PacketCapture** provider, you can configure the **Microsoft-PEF-WFP-MessageProvider** to use **Fast Filters** to improve trace performance. For example, you might create a **Fast Filter** that focuses on messages from a specified IP address or TCP port only. You can also specify **Fast Filters** that remove loopback traffic, for example, with **IPv4** and **IPv6** filters such as `!127.0.0.1` and `!::1`, respectively. You can access the configuration for **Fast Filters** on the **Provider** tab of the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog, which is accessible by clicking the **Configure** link to the right of the **Microsoft-PEF-WFP-MessageProvider**  **Id** in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog.  
  
> [!NOTE]
>  The **WFP Layer Set** filter configuration is also specified on the **Provider** tab of the **Advanced Settings** dialog, as described in the [PEF-WFP Layer Set Filters](pef-wfp-layer-set-filters.md) topic.  
  
## Event Keyword and Error Level Filtering  
 Similar to other system ETW providers that are registered on your system, you have the option to specify ETW event **Keyword** configurations and **Level** filter settings for the **Microsoft-PEF-WFP-MessageProvider**, to further refine the scope of events to be captured. The settings for these filters are available on the **ETW Core** tab of the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog. By default, as with the **Microsoft-PEF-NDIS-PacketCapture** provider, all events are delivered by the **Microsoft-PEF-WFP-MessageProvider** provider when no **Keywords** are selected. If you specify any particular **Keyword**, then the provider will deliver the events that are enabled by that **Keyword** only, if they occur in a trace. It also follows that multiple events are delivered when multiple **Keywords** are selected.  
  
---  
  
 **More Information**   
 **To learn more** about configuring system ETW Providers, including event **Keyword** and error **Level** filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md)  
**To learn more** about specifying **Fast Filters** and **WFP Layer Set** filters for the **Microsoft-PEF-WFP-MessageProvider**, see the following topics:   
[PEF-WFP Fast Filters](pef-wfp-fast-filters.md)  
[PEF-WFP Layer Set Filters](pef-wfp-layer-set-filters.md)  
[Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md)  
---  
  
## See Also  
 [Built-In Trace Scenarios](built-in-trace-scenarios.md)   
 [Microsoft-PEF-NDIS-PacketCapture Provider](microsoft-pef-ndis-packetcapture-provider.md)   
 [Microsoft-PEF-WebProxy Provider](microsoft-pef-webproxy-provider.md)