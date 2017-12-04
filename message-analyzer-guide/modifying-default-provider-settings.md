---
title: "Modifying Default Provider Settings | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5eb04a5a-f9d4-4f84-86e5-79959363dfc0
caps.latest.revision: 39
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Modifying Default Provider Settings
To enhance the capture configuration of a Live Trace Session, you can modify the following aspects of ETW-instrumented providers:  
  
-   **Driver/provider-level filtering** — as described in [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md), you can configure various low-level **Fast Filters** for PEF providers to introduce a selectivity factor to your Live Trace Sessions that improves performance, for example, with the **Microsoft-PEF-NDIS-PacketCapture** provider.  You can also configure special stack filters and packet traversal paths at the driver level for **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider. In addition, you can employ **WFP Layer Set** filters in **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider** in order to control  the direction in which packets are passed or blocked at the Transport Layer.  
  
     Filtering at the driver/provider level improves speed because it reduces the number of messages that will be subject to the Message Analyzer Runtime parsing process, which includes **Session Filtering** that requires additional parsing — providing that a **Session Filter** is configured prior to running a Live Trace Session.  
  
-   **Event filtering** — as described in [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md), you can specify event **Keyword** and error **Level** filter settings for numerous system ETW Providers to enable selective event logging via ETW, which subsequently focuses the events that Message Analyzer captures.  
  
## Configuring Provider-Level Filters  
 The indicated provider setting types are accessible from the **Provider** or **ETW Core** tab of the **Advanced Settings** dialog that you can open by clicking the **Configure** link for message providers that display in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog in Live Trace Session configuration. The following is an overview of the filtering features that enable you to create the indicated configurations:  
  
-   **Fast Filter Groups** — configure **Groups** of logically chained **Fast Filters** and assign them to selected adapters in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapture** provider, for example, the **Local Network Interfaces** scenario on computers running the Windows 7 or Windows 8 operating system. Specify these settings in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog during Live Trace Session  configuration.  
  
-   **Multiple Fast Filters** — configure one or more **Fast Filters** in **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**, for example, the **Loopback and Unencrypted IPSEC** scenario. Specify these settings in the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog during Live Trace Session  configuration.  
  
-   **WFP Layer Set Filters** — selectively enable or disable filters that pass or block inbound, outbound, or bidirectional packet traffic at the Transport Layer in **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**. Specify these settings in the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog during Live Trace Session  configuration.  
  
    > [!NOTE]
    >  You also have the option to log dropped packet information, which includes reason and layer statistics. Enable this function by placing a check mark in the **Select Discarded Packet Events** check box in the **Advanced Settings** dialog for the **Microsoft-PEF-WFP-MessageProvider**.  
  
-   **NDIS and Extension Stack Filters** — specify the layers on which packets are intercepted in the NDIS stack or Hyper-V-Switch extension stack, in **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider, for example, the **Local Network Interfaces (Win8.1 and later)** scenario. You can also configure special filters such as **Truncation**, packet traversal **Direction**, **EtherTypes**, **IP Protocol Numbers**, **Mac Addresses**, and **IP Addresses**. Specify these filtering configurations  in the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog during Live Trace Session  configuration.  
  
-   **Hostname and Port Filters** — configure a **Hostname Filter** to restrict the capture of HTTP operations initiated by the client browser to requests and responses to and from a single web host, in **Trace Scenarios** that use the **Microsoft-PEF-WebProxy** provider, for example, the **Pre-Encryption for HTTPS** scenario. Configure a **Port Filter** to limit the traffic you capture to a particular HTTP port, such as 80, 443, or 8080. Specify these filtering configurations in the **Advanced Settings - Microsoft-PEF-WebProxy** dialog during Live Trace Session  configuration.  
  
-   **ETW Event and Error Filters** — set the event **Keyword** and/or error **Level** configuration of system ETW providers by specifying settings on the **ETW Core** tab of the **Advanced Settings** dialog for any provider that displays in the **ETW Providers** list of the **New Session** dialog.  
  
> [!NOTE]
>  For *system* ETW Providers (Windows components that have been instrumented as ETW event providers), the only additional configuration  that you can specify are  modifications to the event **Keyword** and error **Level** filtering settings; however, not all system ETW Providers make **Keyword** settings available for filtering. System ETW Providers, such as the **Microsoft-Windows-LDAP-Client**, are listed in the **Add System Providers** dialog, which is accessible from the **Add Providers** drop-down list on the **ETW Providers** toolbar on the **Live Trace** tab of the **New Session** dialog, as described in [Adding a System ETW Provider](adding-a-system-etw-provider.md).  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about how to configure common provider settings, see the [Common Provider Configuration Settings  Summary](common-provider-configuration-settings-summary.md).  
**To learn more** about how to configure settings for the **Microsoft-PEF-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
**To learn more** about how to configure settings for the **Microsoft-Windows-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
**To learn more** about how to configure settings for the **Microsoft-PEF-WFP-MessageProvider**, see [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  
**To learn more** about configuring ETW event **Keyword** and error **Level** settings, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
___________________\_