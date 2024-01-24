---
title: "Microsoft-Windows-NDIS-PacketCapture Provider | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40c4aafe-5937-4124-8b29-4ae64875e587
caps.latest.revision: 23
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Microsoft-Windows-NDIS-PacketCapture Provider
The **Microsoft-Windows-NDIS-PacketCapture** provider works with several **Trace Scenarios** that are optimized to capture traffic on either a local or remote computer. The **Microsoft-Windows-NDIS-PacketCapture** provider is instrumented to support these capture scenarios on computers running the Windows 8.1, Windows Server 2012 R2, Windows 10, or later operating system. This means that you can use any **Trace Scenario** that includes this provider to target the capture of traffic from any local or remote host, as long as they are running one of these operating systems. You can even target local and remote traffic at the same time, as long as you specify the local host and target remote computer names in the **Target Computers** list in the **New Session** dialog during Live Trace Session configuration. However, you cannot successfully target any computer for remote capture if it is running a down-level operating system such as Windows 7, Windows 8, or Windows Server 2012. The **Microsoft-Windows-NDIS-PacketCapture** is also instrumented to work with the ETW infrastructure, which provides the mechanisms for controlling ETW Sessions, buffering captured data, and delivering events. Because the **Microsoft-Windows-NDIS-PacketCapture** filter driver works with this infrastructure, it can deliver the frames it captures at the Data Link Layer as ETW events.  
  
> [!NOTE]
>  Message Analyzer uses Windows Management Instrumentation (WMI) remoting facilities for capturing data on remote computers.  
  
## Provider Functions  
 Message Analyzer provides several built-in **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider, in which there are special features that enable you to create unique capture configurations. For example, in the **Microsoft-Windows-NDIS-PacketCapture** provider configuration, you can specify **ETW Core** provider settings, interface selection, and advanced filtering configurations when capturing traffic on local or remote hosts, virtual machine (VM) adapters, and Hyper-V-Switches, as described in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
 You can use the previously indicated configuration features when capturing messages with this provider in scenarios that are optimized for capture on local computers. However, note that because the **Microsoft-Windows-NDIS-PacketCapture** provider supports remote capture on computers running the Windows 8.1, Windows Server 2012 R2, Windows 10, and later operating systems, you can target hosts that are running any of these operating systems for remote capture with *any* **Trace Scenario** that uses the **Microsoft-Windows-NDIS-PacketCapture** provider, for example, even the **Local Network Interfaces** scenario.  
  
## Associated Trace Scenarios  
 The scenarios that use the **Microsoft-Windows-NDIS-PacketCapture** provider are described as follows. With these scenarios, you can capture message data at and above the Data Link Layer on computers that are running the Windows 8.1, Windows Server 2012 R2, Windows 10, or later operating system:  
  
-   **Local Network Interfaces** scenario — as previously indicated, you can apply the advanced provider settings and filtering configurations described in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) to local traffic captures; however, some settings will have a different meaning, such as the **All Layers** setting, depending on whether you are capturing from the local host versus a VM that is serviced by a local Hyper-V-Switch. For more information about advanced filtering, see [Configuring Host Adapter and Hyper-V-Switch Filters](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md#BKMK_HostSwitchFilterConfig).  
  
-   **Remote Network Interfaces** scenario — for more information about the requirements for capturing remote traffic, see [Configuring a Remote Capture](configuring-a-remote-capture.md). Use this scenario to capture traffic from a remote host or virtual machine that is serviced by a Hyper-V-Switch.  
  
-   **Remote Network Interfaces with Drop Information** scenario — also includes several other ETW Providers that are configured with **Keyword** filters to provide event information that identifies dropped packets. Use this scenario to capture traffic from a remote host or virtual machine (VM) that is serviced by a Hyper-V-Switch, when you are interested in determining whether packets are being dropped, possibly by the NDIS stack of a host adapter or the extension layers of a Hyper-V-Switch that is servicing one or more VMs.  
  
-   **VPN** scenario — also includes several other ETW Providers which specify **Keyword** configurations that optimize the capture configuration for exposing events associated with VPN communications. Use this scenario to troubleshoot VPN-related issues.  
  
-   **Wired Local Area Network** scenario — also includes several other ETW Providers that specify **Keyword** configurations that optimize the capture configuration to expose Windows component events associated with the LAN. Use this scenario to troubleshoot a wired LAN and to expose operating system issues.  
  
-   **Wireless Local Area Network** scenario — also includes several other ETW Providers that specify **Keyword** configurations that optimize the capture configuration to expose Windows component events associated with the LAN. Use this scenario to troubleshoot a wireless LAN and to expose operating system issues.  
  
<a name="BKMK_WindowsNDISProviderFilters"></a>   
## Provider Filtering Configurations  
 The special filter types that you can configure in the **Advanced Settings** dialog for the **Microsoft-Windows-NDIS-PacketCapture** provider consist of the following:  
  
-   Adapter filters  
  
-   Layer filters  
  
-   Truncation filters  
  
-   Direction filters  
  
-   EtherType filters  
  
-   IP Protocol Number filters  
  
-   MAC Address filters  
  
-   IP Address filters  
  
---  
  
 **More Information**   
 **To learn more** about configuring these special filters, see the [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) topic, which also includes a figure that shows the **Advanced Settings** dialog for this provider.  
 
---  
  
<a name="BKMK_NDISKeywordErrorLevelFilters"></a>   
## Event Keyword and Error Level Filtering  
 Similar to other system ETW providers that are registered on your system, you have the option to specify ETW event **Keyword** configurations and error **Level** filter settings for the **Microsoft-Windows-NDIS-PacketCapture** provider, to further refine the scope of events to be captured. The settings for these filters are available on the **ETW Core** tab of the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog. By default, all events are delivered by the **Microsoft-Windows-NDIS-PacketCapture** provider when no **Keywords** are selected. If you specify any particular **Keyword**, then the provider will deliver the events that are enabled by that **Keyword** only, if they occur in a trace. It also follows that the provider will deliver multiple events when you select multiple **Keywords**, if they occur in a trace.  
  
---  
  
 **More Information**   
 **To learn more** about configuring ETW Providers, including event **Keyword** and error **Level** filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  

---  
  
<a name="BKMK_CaptureInPMode"></a>   
## Capturing Data in P-Mode  
 To enable capturing messages in Promiscuous Mode with the **Microsoft-Windows-NDIS-PacketCapture** provider, you can select any adapter that supports P-Mode captures in the Interface Selection section of the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog. You can perform such captures in P-Mode with the use of this provider on the local computer or on a specified remote computer.  
  
---  
  
 **More Information**   
 **To learn more** about capturing data in P-Mode, see [Capturing Remotely in Promiscuous Mode](configuring-a-remote-capture.md#BKMK_PromiscuousMode).  

---  
  
## See Also  
 [Built-In Trace Scenarios](built-in-trace-scenarios.md)