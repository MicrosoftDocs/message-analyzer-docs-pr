---
title: "Filtering Captured Input Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 977563b9-d1f8-4450-a750-13290e6c8c2c
caps.latest.revision: 32
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Filtering Captured Input Data
Prior to starting a Live Trace Session with Message Analyzer, there are numerous types of filter configurations that you can create to limit the scope of data that you capture. An overview of the filter types that you can apply to a Live Trace Session is provided in this section.  
  
## Using a Session Filter  
 One of the simplest and most effective methods of filtering is to add a **Session Filter**. A **Session Filter** will allow you to retrieve only the messages that meet the filtering criteria that you define. This conveniently provides a way to target specific message data while reducing the number of retrieved messages for better performance. Just as you can do in a Data Retrieval Session, you can either select a built-in **Session Filter** or configure your own in the **Session Filter** text box of the **New Session** dialog. If you want to use a built-in **Session Filter**, you can select one from the **Message Analyzer  Filters** asset collection **Library** that appears on the toolbar above the **Session Filter** text box in the **New Session** dialog, or you can create your own by entering filter parameters in the indicated text box during Live Trace Session configuration. For additional information about **Session Filters**, see [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md) or [Applying a Session Filter to a Data Retrieval Session](applying-a-session-filter-to-a-data-retrieval-session.md).  
  
## Using Other Filters  
 In addition to specifying a **Session Filter** when you are configuring a Live Trace Session, you can also specify any of the following filter types:  
  
-   **Fast Filters** — if you are configuring a Live Trace Session with a **Trace Scenario** that uses the **Microsoft-PEF-NDIS-PacketCapture** provider, you have the option to specify up to three **Fast Filters** that operate efficiently at the kernel level. You can also specify up to four **Fast Filters** when configuring a Live Trace Session with any **Trace Scenario** that uses the **Microsoft-PEF-WFP-MessageProvider**.  
  
     A **Fast Filter** is a capture-mode filter that offers a significant improvement in performance over user-mode filtering, for example, when applying a **Session Filter**. In the former case, capture-mode filtering is instrumented at the driver level before messages are delivered to the PEF Runtime, while in the latter case, user-mode filtering is applied as part of the Runtime parsing process. User-mode filtering therefore adds more processing time before Message Analyzer can access the data from the PEF Runtime API for display.  
  
-   **Network Adapters and Fast Filter Groups** — if you are configuring a Live Trace Session with a **Trace Scenario** that uses the **Microsoft-PEF-NDIS-PacketCapture** provider on computers running the Windows 7, Windows 8, or Windows Server 2012 operating system, you can also specify the network adapters through which your Live Trace Session will capture messages. For example, you can isolate messages to an Ethernet adapter, a wireless adapter, a combination of adapters, and so on. In addition, you can assign **Groups** of **Fast Filters** to any local adapter.  
  
     When you install Message Analyzer, all the network adapters on your system are enumerated. If you open the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog to configure filters for the **Microsoft-PEF-NDIS-PacketCapture** provider in the **Local Network Interfaces** **Trace Scenario**, you will see that all the network adapters on your system are populated to the **System Network** tree grid under the **Machine** node in the **Advanced Settings** dialog for the **Microsoft-PEF-NDIS-PacketCapture** provider. This dialog contains the configuration features that enable you to create filter **Groups** and assign them to specific adapters.  
  
     In addition, you can selectively enable or disable any network adapter that appears in the **System Network** tree grid of the dialog. By isolating the network adapter on which you capture data, you can block messages from other adapters and focus on capturing the messages of a particular protocol, for example, the Point-to-Point over Ethernet (PpoE) protocol on a WAN Miniport interface connection. Also, you can create filtering configurations that apply to all adapters, a group of selected adapters, or a single selected adapter only.  
  
     The features of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog provide a flexible framework that enables you to focus on capturing very specific data while achieving the performance advantages that are inherent to **Fast Filters**, as described in [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
  
-   **NDIS Layer and Hyper-V-Switch Extension Filtering** — if you are configuring a **Remote Network Interfaces** **Trace Scenario** on computers running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, which uses the **Microsoft-Windows-NDIS-PacketCapture** provider with remote capabilities, you can specify how packets are intercepted on the NDIS filter layers of a remote host adapter or on the extension layers of a Hyper-V-Switch that services virtual machines (VMs) on which you are monitoring traffic. You can also specify the direction that packets traverse these layers along with other special filter configurations that specify a **Truncation** value, **EtherTypes**, **IP Protocol Numbers**, **MAC addresses**, and **IP addresses**. You can also specify particular remote host or VM adapters on which to capture data while excluding others. The configuration for such settings is available in the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog, which is described in detail in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
-   **WFP Layer Set filters** — if you are configuring a Live Trace Session with any **Trace Scenario** that uses the **Microsoft-PEF-WFP-MessageProvider**, you can specify **WFP Layer Set** filters that isolate IPv4 or IPv6 message traffic directionally at the Transport layer. The **WFP Layer Set** consists of kernel-mode TCP/IP stack filters that operate in the receive or send path at the Transport layer. These filters allow you to selectively enable or disable either all inbound or all outbound packets at the Transport layer when capturing IPv4 or IPv6 messages.  
  
-   **HTTP filters** — if you are configuring a Live Trace Session with the **Pre-Encryption for HTTPS** **Trace Scenario** that uses the **Microsoft-Pef-WebProxy** provider, you can specify filters that isolate traffic based on a **Hostname** or **PortFilter** value.  
  
-   **Keyword and Level filters** — if you are configuring a Live Trace Session that uses a particular system **ETW Provider**, you can set event **Keyword** bitmask and **Level** filters to capture events from specific modules of a Windows system component that has been instrumented for ETW via that **ETW Provider**, with **Keyword** bitmask values and **Level** strings that represent its events. By setting an appropriate **Keyword** bitmask or **Level** value, you cause the **ETW Provider** to deliver only the events that are represented by the **Keyword** or **Level** configuration, thereby enabling you to filter for these events in traces that use a particular system **ETW Provider**. Examples of such providers include the **Microsoft-Windows-Dhcp-Client** and **Microsoft-Windows-LDAP-Client**. These ETW providers are accessible from the **Add System Providers** dialog, which you can display from the **Add Providers** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog during Live Trace Session configuration.  
  
    > [!NOTE]
    >  The default **Microsoft-PEF-NDIS-PacketCapture** provider and **Microsoft-PEF-WFP-MessageProvider** both enable you to specify event **Keyword** bitmask and **Level** filter configurations. However, you should note that not all system **ETW Providers** are enabled for event **Keyword** and **Level** configuration, as some **ETW Providers** do not define them.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the functions of built-in Filter Expressions that you can apply as a **Session Filter** or view **Filter**, see [Filtering Live Trace Session Results](filtering-live-trace-session-results.md).  
**To learn more** about creating your own Filter Expressions or modifying existing ones, see [Writing Filter Expressions](writing-filter-expressions.md).  
**To learn more** about the **Fast Filter** configurations that you can apply to PEF providers, see [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).  
**To learn more** about **Network Adapter** filtering, see [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).  
**To learn more** about **Fast Filter** **Groups** for adapters, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
**To learn more** about remote tracing and special NDIS layer and Hyper-V-Switch extension filters, see [Configuring a Remote Capture](configuring-a-remote-capture.md).  
**To learn more** about **WFP Layer Set** filtering, see [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).  
**To learn more** about **Hostname** and **PortFilter** filtering, see [WebProxy Filters](webproxy-filters.md).   
**To learn more** about event **Keyword** bitmask and **Level** filtering, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).   
___________________\_  
  
## See Also  
 [Configuring a Live Trace Session](configuring-a-live-trace-session.md)