---
title: "System ETW Provider Event Keyword-Level Settings | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c7f6ca1-6e07-460e-829f-4229faec6784
caps.latest.revision: 76
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# System ETW Provider Event Keyword-Level Settings

All PEF providers are instrumented with Event Tracing for Windows (ETW) technology so that Message Analyzer can leverage its infrastructure for data collection, session control, buffer configuration, and so on, as described in the [ETW Framework Conceptual Tutorial](etw-framework-conceptual-tutorial.md). As a result, all PEF providers contain a core ETW Provider component that interacts with an enabling ETW Session where it writes events that Message Analyzer can capture. Other ETW Providers that are registered on your system were originally created by instrumenting various Windows components with ETW technology; as a result, they too can leverage the ETW infrastructure and Message Analyzer can capture their events. In this documentation, these are referred to as *system* ETW Providers, and in general, they write events from various applications and components on your system, such as Dynamic Host Configuration Protocol (DHCP), Domain Name System (DNS), Lightweight Directory Access Protocol (LDAP), and so on.  
  
 These system ETW Providers are accessible from the **Add System Provider** dialog, which you can display by clicking the **Add System Providers** item in the **Add Providers** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog  during Live Trace Session configuration.  
  
 **Filtering Events with Keywords and Level Settings**   
Most system ETW Providers from which Message Analyzer can capture event data are instrumented with  filters that enable you to return specific  provider events that you want to capture. The mechanism that allows you to do this is the provider event configuration which is specified in the provider manifest as **Keywords**, where each **Keyword** represents one of the provider's events. Message Analyzer enables you to select specific data from a Live Trace Session by specifying a low-level **Keyword** bitmask that matches the **Keyword** value of one or more system ETW Provider events, therefore effectively acting as a filter that tells the provider to write such  events to the ETW session that enabled it. Another setting that you can configure for ETW Provider events is the error **Level**, which allows you to return events that correspond to a specified severity level, for example, **Critical**, **Error**, **Warning**, **Information**, and so on.  
  
> [!IMPORTANT]
>  Some system ETW Providers may specify only a **Level** value  for their events without  also specifying a **Keyword** configuration for such events, and vice-versa. In addition, not all system ETW Providers that you add to your Live Trace Session configuration have event **Keyword** or error **Level** filtering available at all. In the latter case, this simply means that when the provider/manifest was created to instrument a particular Windows component with ETW technology, **Keyword** and/or **Level** filtering configurations were not specified by the developer. In this scenario, an ETW Provider will usually deliver all the triggered events from a particular component to the enabling ETW session, as there are no event **Keyword** and **Level** configurations specified for which a bitmask can filter.  
>   
>  If event **Keyword** and error **Level** filter configurations are available for a chosen system ETW provider and you want to configure such filters, see the sections that follow to understand how to set and use them.  
  
The conceptual section that follows provides some brief background information on event tracing to help clarify the meaning of these **Keyword** and **Level** filtering features.  
  
## Conceptual Background  

 Event tracing is built upon an API that exposes the following ETW components:  
  
-   **ETW Session** — provides an environment that accepts events, buffers them, and creates a trace file for logging the events or delivers them live in real-time to an ETW Consumer.  
  
-   **ETW Controller** — enables providers, starts and stops event tracing sessions, defines log files, obtains execution statistics, sets the buffer configuration, and so on. Note that a provider is turned on only when it is enabled for an ETW Session by the ETW Controller.  
  
-   **ETW Provider** — provides events to an event tracing session.  A provider defines its interpretation of being enabled or disabled.  In general, an enabled provider generates events, whereas a disabled provider does not.  
  
-   **ETW Consumer** — consumes the events from an event tracing session.  
  
When an ETW Controller enables an ETW Provider, it exposes the provider event configuration to the ETW Session to enhance the provider’s filtering instrumentation. An ETW Provider event configuration is specified with the use of the following two elements:  
  
-   **Level** — a 1-byte integer that enables filtering based on the severity or verbosity of events.  
  
-   **Keywords** — an 8-byte bitmask that enables the filtering of events from specific provider subcomponents.  
  
For example, by selectively enabling these filtering features, the ETW Controller can enable providers to log the following:  
  
-   Only the error events from a particular provider subcomponent.  
  
-   All events from specific provider subcomponents.  
  
-   Specific events from provider subcomponents.  
  
> [!NOTE]
>  When an ETW Controller enables a particular event **Level**, all provider events with a **Level** value that is less than or equal to what the ETW Controller specified are also enabled. For further details, see the Table ahead entitled "System ETW Provider Keyword and Level Filter Configurations".  
  
<a name="BKMK_KeywordFiltering"></a>   
## Filtering with System ETW Provider Event Keywords and Levels  
 Message Analyzer provides the following filtering settings for system ETW Providers that appear in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. The settings are accessible on the **ETW Core** tab of the **Advanced Settings** dialog that displays when you click the **Configure** link for any provider in the **ETW Providers** list:  
  
-   **Keywords(Any)** — enables you to specify an 8-byte, hexadecimal bitmask value that represents one or more **Keywords**, in order to set the category of events that an ETW event provider writes. The provider will write a particular event if the provider's event **Keyword** bits match *any* of the bits set in the **Keywords(Any)** bitmask.  
  
-   **Keywords(All)** — an optional 8-byte, hexadecimal bitmask that further restricts the category of events that an ETW event provider writes. If the provider **Keyword** for an event meets the **Keywords(Any)** condition, the provider writes the event only if the provider's event **Keyword** bits also match *all* of the bits set in the **Keywords(All)** bitmask. Note that this mask is not used if **Keywords(Any)** is set to zero.  
  
> [!NOTE]
>  **Keyword** bitmask filters and provider event **Keyword** values are typically subjected to a  logical ANDing process to validate whether an event should be written and returned to the ETW consumer (Message Analyzer) in an ETW session. For example, if the same bit positions in a provider event **Keyword** and the **Keywords(Any)** bitmask that you set are both logic 1, then the ANDing process signals that the associated event should be returned in the ETW session.  
  
 **Using the ETW Keyword Filter Property Dialog**   
The figure that follows shows the **ETW Core** tab of the **Advanced Settings** dialog that you can display for any ETW Provider, as previously described. From this location, you can access **Keyword** bitmask configurations in the **ETW Keyword Filter Property** dialog, which displays after you click one of the ellipsis buttons (**...**) on the **ETW Core** tab of the **Advanced Settings** dialog. In the **ETW Keyword Filter Property** dialog, you can manually configure a **Keyword** bitmask, or you can select event **Keyword** presets to automatically create a **Keyword** bitmask.  
  
 In the figure, note that the  **ETW Keyword Filter Property** dialog displays a **Keyword** bitmask value in the lower text box, which  is the result of selecting several events in the **Automatic** list for the **Windows-NDIS-PacketCapture** provider, as indicated by check marks. Also note that you can view the decimal values of the listed events for this (or any) system ETW provider by using the *Windows Events Provider Explorer* tool described in  [Finding System ETW Provider Metadata](system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords). With this type of information, you can convert decimal values to hexadecimal values with an appropriate tool, should you ever need to manually configure  **Keyword** bitmask settings.  
  
 ![Advanced Settings Dialog&#45;ETW Keyword and Level Settings](media/fig24-advanced-settings-dialog-etw-keyword-and-level-settings.png "Fig24-Advanced Settings Dialog-ETW Keyword and Level Settings")  
  
 **Figure 24:  Advanced Settings Dialog ETW Keyword and Level Settings**  
  
 **Automatic vs Manual  Keyword Bitmask Configuration**   
The easiest way to set a **Keyword** bitmask is to take advantage of the automatic configuration that is available in the **ETW Keyword Filter Property** dialog. However, you can also perform this process manually if you are familiar with (and can specify) the **Keyword** bitmask values that match the specific events of an ETW provider. In either case, you should understand the meaning of the events that are distinguished by the provider **Keywords** for which you are specifying bitmasks, to enable a  coherent  interpretation of results. The subsections that follow  provide some examples of manual **Keyword** bitmask configuration to return the events  of a simple, but hypothetical  provider. From this, you should be able to better understand what occurs during **Automatic** configuration, which is the feature you will  likely use the most.  
  
 **Manually Specifying a Keyword Bitmask  Value**   
In many cases, if you leave the **Keywords(Any)** bitmask set to the default value of zero (0x0000000000000000) in the  **ETW Keyword Filter Property** dialog, the associated ETW Provider will write all of its events, that is, those that are triggered.  To return only specific events, you will need to set the **Keywords(Any)** bitmask to a value that will pass those provider events, which are typically defined in the ETW Provider manifest (see the [System ETW Provider Event Configuration](etw-framework-conceptual-tutorial.md#BKMK_SysETWProviderEventConfig) topic  of the [ETW Framework Conceptual Tutorial](etw-framework-conceptual-tutorial.md) for  details).  To arrive at a value that will pass specific events, you will need to create a bitmask that is *inclusive* of all the provider events you want to return. The subsection that follows illustrates how a provider might define events with specific **Keyword** values and how you can return such events with a specific   **Keyword** bitmask.  
  
 **Provider Event Configuration** — the table that follows shows some hypothetical **Keyword** definitions that could be specified in a manifest that is associated with an event provider.  
  
### Table 6. Example Provider Event Configuration  
  

|**Event Name**|**Configuration**|**Binary Value**|**Hexadecimal Value**|  
|-|-|-|-|  
|Initialization|Sets first binary bit.|000**1**|0x0000000000000001|  
|File Read Operation|Sets second  binary bit.|00**1**0|0x0000000000000002|  
|File Write Operation|Sets third binary bit.|0**1**00|0x0000000000000004|  
  
 **Returning the Provider Events** — in this hypothetical configuration of provider events, the inclusive binary value for all events written by this provider is 0x0000000000000007 (equivalent to 0**111** binary, or 7 in decimal). If you wanted to receive all of the above provider events, you would set the **Keywords(Any)** bitmask in the Message Analyzer **ETW Keyword Filter Property** dialog to a hex value of 0x0000000000000007. However, if  you were interested in receiving  Initialization and File Read Operation events only, you would set the **Keywords(Any)** bitmask in the **ETW Keyword Filter Property** dialog to a hexadecimal value of 0x0000000000000003 (equivalent to 00**11** in binary, or 3 in decimal).  
  
 Note that in the earlier scenario with the **Keywords(Any)** bitmask set to 0x0000000000000007, any of the above specified provider events will be returned, if they are triggered. However, if you also set the **Keywords(All)** bitmask to a hex value of 0x0000000000000004 (**0100** binary), this restriction would allow only the File Write Operation events to be returned, if they are triggered, as described earlier in this section.  
  
 **Setting the Error Level**   
For events that are delivered to an enabling ETW session, you can obtain an indication of the  severity or verbosity of event errors by setting the error **Level** that the session will report for the events of a particular ETW Provider. To do this, select a particular value from the **Level** drop-down list on the **ETW Core** tab of the **Advanced Settings** dialog for a any ETW provider. The values that you can set are described in the table that follows, along with some further details about **Keyword** configuration options.  
  
> [!TIP]
>  You may be able to discover event **Keyword** and error **Level** settings for various trace providers on your system by referring to the topic [Finding System ETW Provider Metadata](system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords).  
  
### Table 7. System ETW Provider Keyword and Level Filter Configurations  
  
|Configuration Setting|Values|Description|  
|---------------------------|------------|-----------------|  
|**Level**|You can configure this setting to one of the following values:<br /><br /> -   **LogAlways** (0x0)<br />-   **Critical** (0x1)<br />-   **Error** (0x2)<br />-   **Warning** (0x3)<br />-   **Information** (0x4)<br />-   **Verbose** (0x5)|Specifies the level of detail included in the ETW provider event.  Levels indicated in the **Values** column to the left are inclusive. For example, if you set the **Level** to **Verbose**, the provider will write all **Critical**, **Error**, **Warning**, and **Information** events as well.  If you set the **Level** to **Warning**, the provider will also write all **Critical** and **Error** events.<br /><br /> Note that if you set the **Level** to **LogAlways**, it ensures that all error events will always be written.|  
|**Keywords(Any)**|You can configure this setting in either of the following ways:<br /><br /> -   **Manual** — you can manually specify an 8-byte hexadecimal bitmask value to enable a system ETW Provider to write events whose **Keyword** bits match *any* of the bits in the specified **Keyword (Any)** bitmask.<br />-   **Automatic** — you can select one or more preset keywords to automatically configure an 8-byte hexadecimal bitmask value, to enable a system ETW Provider to write events whose **Keyword** bits match *any* of the bits in the specified **Keyword (Any)** bitmask.|Provides a convenient way to add filtering at the kernel level, which enhances performance as follows:<br /><br /> -   The provider selects specific data to retrieve, thereby reducing the number of messages being captured, which subsequently increases the speed at which data is captured.<br />-   Filtering at kernel level is inherently faster than user mode filtering (following the parsing process).<br /><br /> You can set a **Keywords(Any)** bitmask filter by clicking the ellipsis [**…**] to the right of the current hexadecimal **Keywords(Any)** value, to display the **ETW Keyword Filter Property** dialog.  From this dialog, you can either select **Manual** to specify a **Keywords(Any)** bitmask value, or you can select **Automatic** to choose a bitmask based on a preset bitmask **Value**, which indicates a subcomponent of the provider. **Note:**  Before setting this value, you should be familiar with the **Keyword** settings of the provider event for which you are trying to filter. You may obtain some of this information by consulting the system ETW Provider manifest, as described in [Finding System ETW Provider Metadata](system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords).|  
|**Keywords(All)**|You can configure this setting in either of the following ways:<br /><br /> -   **Manual** — you can manually specify an 8-byte, hexadecimal bitmask value, to enable a system ETW Provider to write events whose **Keyword** bits match *all* of the bits in the specified **Keyword (All)** bitmask.<br />-   **Automatic** — you can select one or more preset keywords to automatically configure an 8-byte, hexadecimal bitmask value, to enable a system ETW Provider to write events whose **Keyword** bits match *all* of the bits in the specified **Keyword (All)** bitmask.|Provides a convenient way to add filtering at the kernel level, which enhances performance as described above.<br /><br /> You can set a **Keywords(All)** bitmask  by clicking the ellipsis [**…**] to the right of the current hexadecimal **Keywords(All)** value, to display the **ETW Keyword Filter Property** dialog.  From this dialog, you can either select **Manual** to specify a **Keywords(All)** bitmask value, or you can select **Automatic** to choose a bitmask based on a preset **Value**, which indicates a subcomponent of the provider.<br /><br /> As indicated earler, using this filter further restricts the events that will be written by the system ETW Provider.  Only if a provider's event **Keyword** matches the **Keywords(Any)** condition and only if all bits in the **Keywords(All)** bitmask also exist in the provider's event **Keyword** configuration will the provider write the specific event/s.|  
  
<a name="BKMK_FindingKeywords"></a>   
## Finding System ETW Provider Metadata  
 This topic describes several possible ways  to locate the event **Keywords** that a system ETW Provider writes. These methods are discussed in the  subsections that follow.  
  
 **Opening the ETW Keyword Filter Property Dialog**   
You can view predefined event **Keyword** configurations in the **ETW Keyword Filter Property** dialog that displays when you click the ellipsis on the **Keywords(Any)** or **Keywords(All)** drop-downs that appear on the **ETW Core** tab of the **Advanced Settings** dialog for any particular ETW provider. Although, you may need to do some research to discover the meaning of the events.  
  
 **Using the WEPExplorer Graphic Utility**   
Each system ETW Provider that is installed and registered on your system contains metadata that is stored in a manifest. To locate this metadata, which includes event **Keywords**, error **Levels**, **Opcodes**, **Channels**, and so on, you might consider using a graphic utility such as the *Windows Events Provider Explorer* (WEPExplorer) to obtain this information, as described in [Windows Events Provider Explorer](http://lallouslab.net/2016/01/25/windows-events-providers-explorer/) on the web. If you are a programmer, you can also return this information programmatically, as described in [Getting a Provider's Metadata](https://msdn.microsoft.com/library/windows/desktop/dd996925\(v=vs.85\).aspx) on MSDN.  
  
 **Opening Performance Monitor**   
You also might be able to review the **Keyword** configuration of a  system ETW Provider for which you are looking by opening the **Performance Monitor** tool and locating the provider as it running in a live Windows Event Tracing Session. To view the event **Keyword** and error **Level** configuration for events that such a provider writes, follow the steps below.  
  
1.  From the **Start** menu or from the desktop, right-click **Computer** or the **Computer** icon, respectively, and select the **Manage** item to display the **Computer Management** console.  
  
2.  In the **Computer Management (Local)** pane, expand the **Performance** node, expand the **Data Collector Sets** node, and then click **Event Trace Sessions**.  
  
     The name and status of event trace sessions that are running on your machine are displayed.  
  
3.  Right-click an event trace session such as **EventLog-System** and select the **Properties** item from the menu.  
  
     The **EventLog-System Properties** dialog displays. This may take a few moments.  
  
4.  Select the **Trace Providers** tab and then double-click a provider in the **Providers** list box.  
  
     The current **Keyword** and **Level** configuration of the provider you clicked displays in the **Properties** list box.  
  
5.  In the **EventLog-System Properties** dialog, click the **Edit** button to display a list of all the **Keywords** that define the events that the selected provider can write to a trace consumer, which are typically specified in the provider manifest.  
  
## See Also  
[Generating a Provider Manifest](generating-a-provider-manifest.md)