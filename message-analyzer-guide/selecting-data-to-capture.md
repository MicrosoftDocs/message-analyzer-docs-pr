---
title: "Selecting Data to Capture | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52fb64de-6050-4eab-869f-f06937961e8a
caps.latest.revision: 28
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting Data to Capture
As part of the browse-select-view (BSV) model, Message Analyzer provides a *data selection* feature that enables you to define the scope of the information that you capture or load through a session. Although the concept of data selection applies equally to capturing data in a Live Trace Session or loading saved data through a Data Retrieval Session, with exception of using different filter types in some cases, this section focuses on selecting data in a Live Trace Session.  
  
## Using Data Selection  
 Data selection is not exactly a specific user interface element that you can locate, but rather, more of an approach you can take to focus on obtaining the precise data you need to work with to quickly solve problems. In Message Analyzer, the goal of data selection is to acquire the least amount of data necessary to resolve an issue, in order to minimize consumption of system resources, improve performance, and streamline the data analysis process.  
  
 Message Analyzer provides several tools that you can use to create this focus, as indicated in the list below. To use these data selection capabilities, you will typically create a Live Trace Session (or Data Retrieval Session) that selects specific data  based on configurable criteria, prior to starting the actual data capture process. During data capture, the selection criteria that you configured is applied. This context enables you to narrow the focus of the data capture process to only the message data that you want to work with.  
  
## Isolating Specific Types of Message Data  
 A very effective means of isolating specific message types in a Live Trace Session consists of using filters to return only the type of message data that you choose, while blocking all data that does not specifically meet your designated filtering criteria. The effects of filtering can be initiated at a   high-level or a low-level to select the data that you want to extract from a Live Trace Session, as described in the subsections that follow.  
  
 **Selecting Data with High-Level Filtering**   
High-level filtering enables you to alter the overall session results that you obtain and will also impact the effects of any low-level filters that you specified. As a result of applying such a  combination  of filter types, you might not return the results you expect unless you consider how to  combine them correctly. For example, if you specify a low-level **Fast Filter** that passes specific traffic on a particular port, you should ensure that you do not also specify a high-level **Session Filter** that somehow overrides  the effects of the specified **Fast Filter**, or you might fail to see the data  you are expecting. However, note that while you have the option of changing or removing a **Session Filter** in  the **Edit Session** dialog for a set of trace results, you cannot alter the effects of an applied **Fast Filter**.  
  
 You might also consider that you can  limit the level to which Message Analyzer parses by specifying a **Parsing Level**. For example, if you specified a low-level **Fast Filter** to pass some  Application Layer traffic on a particular port and you also limit parsing to the Network Layer, Message Analyzer will not parse or display any of the Application Layer traffic.  
  
 During configuration of a Live Trace Session, you can specify the primary high-level filters as follows. Note that a **Session Filter** and the **Parsing Level** drop-down list are shown in the figure of the topic [Using a Session Filter](message-analyzer-tutorial.md#BKMK_UsingSessionFilter).  
  
-   **Session Filter** — select a **Session Filter** item from the **Message Analyzer Filters** asset collection **Library** in the **Session Filter** text box of the **New Session** dialog, in a category that is relevant to the **Trace Scenario** you have selected for your Live Trace Session. For example, if you selected the **Pre-Encrypted for HTTPS** scenario from the **Select Scenario** drop-down list on the **Live Trace** tab in the **New Session** dialog, it could be advantageous to also select the `HTTP.StatusCode >=400`**Session Filter** in the **HTTP** category to focus on HTTP errors that are occurring on the client.  
  
     For further details about how to select data from a Live Trace Session with the use of a **Session Filter**, see [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md).  
  
-   **Parsing Level** filter — choose a **Parsing Level** to return a set of messages that are constrained by the upper stack level to which Message Analyzer parses. This feature simultaneously creates a unique analysis perspective and a focused set of messages, while improving performance by removing all messages above the specified **Parsing Level**.  
  
     For further details about how to select data from a Live Trace Session with the use of a **Parsing Level**, see [Setting the Session Parsing Level](setting-the-session-parsing-level.md).  
  
> [!TIP]
>  You can also filter trace *results* data by applying a view **Filter** in an Analysis Session. Note that while you can remove the effects of a view **Filter** on a set of trace results, the effect of using a **Fast Filter**, as described ahead,  is inherent to a given set of trace results and cannot be changed unless you rerun the trace with a change in the **Fast Filter** configuration. However, you have the option to modify a **Session Filter** or specify a different one and apply those changes to a set of trace results, if you do so through the **Edit Session** dialog, which is accessible only after your initial trace completes.  
  
 **Selecting Data with Low Level Filtering**   
Message Analyzer also enables you to specify  other types of filtering  during Live Trace Session configuration, such as low-level **Fast Filters**, **WFP Layer Set** filters, event **Keyword** bitmask and error **Level** filters, and others, You can even use **Trace Scenarios** to select specific data in a Live Trace Session. These filters consist of the following:  
  
-   **Fast Filter** — configure these filters from the **Advanced Settings** dialog for **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider** or the **Microsoft-PEF-NDIS-PacketCapture** provider. **Fast Filters** work at the provider/driver level, which means that you can isolate the messages you want to focus on without incurring any Message Analyzer parsing time to apply the filtering criteria. This is partly what makes **Fast Filters** so efficient and quick.  
  
     For further details about how to select data from a Live Trace Session with the use of a **Fast Filter**, see the [PEF-NDIS Fast Filters](pef-ndis-fast-filters.md) and [PEF-WFP Fast Filters](pef-wfp-fast-filters.md) topics.  
  
-   **WFP Layer Set** filters — use these filters to specify the direction in which data is captured at the Transport Layer for IPv4 and IPv6, in scenarios that use the **Microsoft-PEF-WFP-MessageProvider**.  
  
     For further details about how to select data from a Live Trace Session with the use of **WFP Layer Set** filters, see the [PEF-WFP Layer Set Filters](pef-wfp-layer-set-filters.md) topic.  
  
-   **WebProxy** filters — use HTTP filters such as **Hostname** and **Port** to isolate HTTP messages from a particular host or on a specified port in scenarios that use the **Microsoft-PEF-WebProxy**/Fiddler provider, such as the **Pre-Encrypted for HTTPS** scenario.  
  
     For further details about how to select data from a Live Trace Session with the use of a **WebProxy** filter, see the [WebProxy Filters](webproxy-filters.md) topic.  
  
-   **Keyword** and **Level** filters — specify event **Keyword** bitmasks and/or error **Level** settings to match system ETW Provider event configurations and thereby select specific events to be returned from a Live Trace Session.  
  
     For further details about specifying **Keyword** bitmasks and **Level** settings, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
  
-   **Adapter** filters — select specific data from a trace by applying **Fast Filter** groups to local host adapters in scenarios that use the **Microsoft-PEF-NDIS-PacketCapture** provider; or apply remote host adapter or Hyper-V-Switch layer, payload, and other special filters in scenarios that use the **Microsoft-Windows-NDIS-PacketCapture** provider.  
  
     For further details about how to select data from a Live Trace Session with the use of an Adapter filter during **Microsoft-PEF-NDIS-PacketCapture** provider configuration, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
    For further details about how to select data from a Live Trace Session with the use of an Adapter filter during **Microsoft-Windows-NDIS-PacketCapture** provider configuration, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
 **Selecting Data with a Trace Scenario**   
The **Trace Scenario** that you select for your Live Trace Session can have an impact on the data that you return. For example, you could select a **Trace Scenario** that uses a message provider that focuses on a particular stack level, such as the **Loopback and Unencrypted IPSEC** scenario. This scenario focuses on messages above the IP/Network Layer while filtering out most lower-level noise at the Data Link Layer, such as broadcast traffic.  
  
 You could also select a **Trace Scenario** that employs predefined filtering to return a specific result, such as the **Local Loopback Network** scenario, which uses two **Fast Filters** and **WFP Layer Set** filters to pass only loopback traffic. Moreover, you might select a **Trace Scenario**, such as the **VPN** scenario, that employs a number of system ETW Providers that focus on returning specific messages and events that are useful when you are troubleshooting VPN issues.  
  
 You might also create your own **Trace Scenario** by selecting one or more system ETW providers from the ***Add Provider*** drop-down list in the **New Session** dialog during Live Trace Session configuration, to create focus on specific types of messages to retrieve during live capture.  
  
 For further details about selecting a **Trace Scenario** to return specific types of data, see the [Selecting a Trace Scenario](selecting-a-trace-scenario.md) section.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the configuration features of the **Advanced Settings** dialogs for the **Microsoft-PEF-WFP-MessageProvider**, **Microsoft-PEF-NDIS-PacketCapture** provider, and the **Microsoft-Windows-NDIS-PacketCapture** provider, see the following topics:  
[Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md) — describes how to configure **Fast Filters**, **Discarded Packet Events**, and **WFP Layer Set** filters (packet direction at the Transport Layer).  
[Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md) — describes how to select adapters, configure **Fast Filters**, and create **Fast Filter** groups to apply to local host adapters.  
[Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) — describes how to configure advanced packet direction and layer filtering configurations for the NDIS stack and Hyper-V-Switch extension layers on remote (or local) hosts, in addition to packet **Truncation** filters and special message payload filtering such as **EtherType** and **IP Protocol Numbers**.  
 ___________________\_  
  
## See Also  
 [Editing Existing Sessions](editing-existing-sessions.md)