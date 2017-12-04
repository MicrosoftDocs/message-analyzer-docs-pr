---
title: "Common Provider Configuration Settings Summary | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca19caa0-f5ed-4adf-b98a-7d5916ab05b4
caps.latest.revision: 81
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Common Provider Configuration Settings Summary
This topic provides an overview of the types of filters that you can apply to the core providers that are used in the most common **Trace Scenarios** that Message Analyzer provides. Examples of settings for such filters are included in the [Common Provider Configuration Settings](../messageanalyzer_content/common-provider-configuration-settings-summary.md#BKMK_CommonProvSettings) table of this topic.  
  
<a name="BKMK_SelectingDataWithProviderFiltering"></a>   
## Selecting Data with Trace Provider Filtering  
 Message Analyzer enables you to select specific data from a Live Trace Session by modifying the settings of ETW providers that are included in Message Analyzer **Trace Scenarios**. These settings enable you to configure key filter configurations for Message Analyzer providers in the following common **Trace Scenarios**:  
  
-   **Local Network Interfaces (Windows 8 and earlier)** — you can configure the following types of filtering for the **Microsoft-PEF-NDIS-PacketCapture** provider that is used in this scenario:  
  
    -   **Fast filtering** — enables you to filter message traffic based on offset-length patterns (OLPs), LinkLevelAddress, IPv4 address, and IPv6 address.  
  
    -   **Adapter filtering** — enables you to isolate traffic on specific adapters.  
  
    -   **Chained filtering** — enables you to create **Groups** of logically chained **Fast Filters** and assign them to specific adapters on your system.  
  
-   **Remote Network Interfaces** — you can configure the following types of filtering for the **Microsoft-Windows-NDIS-PacketCapture** provider:  
  
    -   **Adapter filtering** — enables you to isolate traffic to specific adapters, including remote host adapters and adapters for virtual machines (VMs) that are serviced by a Hyper-V-Switch.  
  
    -   **Driver filtering** — enables you to isolate inbound or outbound traffic to remote host adapters and to specify the NDIS filter layers on which to intercept packets that traverse the NDIS stack contained in the adapter.  
  
    -   **Switch filtering** — enables you to specify the filter layers on which to intercept packets that traverse a remote Hyper-V-Switch Extension stack and you can also specify the direction in which packets traverse this stack.  
  
    -   **Packet filtering** — other filters that you can specify to modify the trace configuration on a remote host with the **Microsoft-Windows-NDIS-PacketCapture** provider include **Truncation**, **EtherTypes**, **IP Protocol Numbers**, **MAC Addresses**, and **IP Addresses**.  
  
     **Note:** You can specify these same remote filtering configurations in *local* **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider, for example, the **Local Network Interfaces (Windows 8.1 and later)** scenario. However, in this scenario, you will be applying the indicated filters to host or VM adapters that exist on the local computer by default.  
  
     You can review the user interface for setting these filtering configurations in the figure that is provided in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
-   **Loopback and Unencrypted IPSEC** — you can configure the following types of filtering for the **Microsoft-PEF-WFP-MessageProvider** that is used in this scenario:  
  
     **Note:** The **Network Tunnel Traffic and Unencrypted IPSEC**, **Local Loopback Network**, and **SMB Client and Firewall** scenarios also use the **Microsoft-PEF-WFP-MessageProvider** and can utilize the same type of filtering specified below.  
  
    -   **Transport Layer filtering** — enables you to isolate inbound and outbound Transport Layer message traffic for IPv4 and IPv6 transports, by using the **WFP Layer Set** filters.  
  
    -   **Fast filtering** — enables you to filter messaging traffic based on IPv4 address, IPv6 address, TCP port, and UDP port values.  
  
     **Note:** You can also choose to select discarded packet events for logging.  
  
     You can review the user interface for setting these filtering configurations in the figure that is provided in [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  
  
-   **Pre-Encryption for HTTPS**— you can configure the following types of filtering for the **Microsoft-PEF-WebProxy** provider that is used in this scenario:  
  
    -   **HTTP filtering** — enables you to specify a **Hostname Filter** and/or a **Port Filter** so that you can isolate HTTP message data to specified host names and port numbers.  
  
     **Note:** You can also specify a certificate file to use for server authentication on HTTPS connections, as required by some sites. In addition, you can keep client or server connections alive for performance improvements, by selecting the **Reuse Client Connections** and/or   **Reuse Server Connections** check boxes on the **Provider** tab of the **Advanced Settings - Microsoft-PEF-WebProxy** dialog, which is accessible in the previously described manner.  
  
<a name="BKMK_FastFilters"></a>   
## Fast Filters  
 You can modify the provider configuration in the **Local Network Interfaces (Win 8 and earlier)**, **Local Loopback Network**, and **Loopback and Unencrypted IPSEC** **Trace Scenarios** by specifying low-level **Fast Filters**. Message Analyzer enables you to add simple filtering values as part of your **Fast Filter** configuration, as described in the [Common Provider Configuration Settings](../messageanalyzer_content/common-provider-configuration-settings-summary.md#BKMK_CommonProvSettings) table. **Fast Filters** reduce the data volume that is transported from kernel to user mode (Runtime parsing engine), which saves system resources and also improves Message Analyzer efficiency under heavy traffic loads.  
  
 You can apply **Fast Filters** in any **Trace Scenario** that uses the **Microsoft-PEF-WFP-MessageProvider** or the **Microsoft-PEF-NDIS-PacketCapture** provider. **Fast Filters** for the **Microsoft-PEF-WFP-MessageProvider** are configurable from the **Provider** tab of the **Advanced Settings – Microsoft-PEF-WFP-MessageProvider** dialog that is accessible by clicking the **Configure** link for the **Microsoft-PEF-WFP-MessageProvider** that displays in the **ETW Providers** list when you select one of the applicable **Trace Scenarios** in the **New Session** dialog. **Fast Filters** for the **Microsoft-PEF-NDIS-PacketCapture** provider are configurable from the **Provider** tab of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog that is accessible by clicking the **Configure** link for the **Microsoft-PEF-NDIS-PacketCapture** provider that displays in the **ETW Providers** list when you select a **Local Network Interfaces** **Trace Scenario** in the **New Session** dialog. These filters enable you to focus a provider’s message retrieval action at a lower level than a **Session Filter**, which makes them faster and more efficient.  
  
 For example, you can configure up to three **Fast Filters** per **Group** in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, and each filter can be any of the four filter types described earlier in [Selecting Data with Trace Provider Filtering](../messageanalyzer_content/common-provider-configuration-settings-summary.md#BKMK_SelectingDataWithProviderFiltering). If you specify more than one **Fast Filter** per **Group**, then you can choose to logically AND or OR the filters together. Thereafter, you can assign the filter **Groups** to specific adapters that are listed in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog. Also note that filter **Groups** are logically ANDed together by default.  
  
 You can learn more about configuring **Groups** of **Fast Filters** and adapter assignment in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapture** provider by reviewing the topic [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md). However, some of the settings for adapter and **Fast Filter** configuration are briefly described in the configuration settings table in this section.  
  
## Applying Filters in Local and Remote Scenarios  
 This section provides a quick overview of applying host adapter filtering and low-level **Fast Filters** in **Trace Scenarios** that capture traffic locally; and host adapter filtering, packet filters, and other special filters in **Trace Scenarios** that capture traffic remotely. To specify these filtering configurations, you will need to click the **Configure** link in the **ETW Providers** list in the **New Session** dialog for the particular provider with which you are working in order to display the associated **Advanced Settings** dialog.  
**Local Trace Scenarios**  
You can modify the **Microsoft-PEF-NDIS-PacketCapture** provider configuration for the **Local Network Interfaces** scenario in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, to isolate traffic by the following:  
  
-   Selecting a particular local adapter on which to capture traffic.  
  
-   Specifying the direction in which traffic is captured, either incoming, outgoing, or in both directions.  
  
-   Configuring up to two **Fast Filter Groups**, each with up to three **Fast Filters** specified.  
  
 **Local Filtering Configuration** — you can specify filtering configuration settings in the **Advanced Settings** dialog for the **Microsoft-PEF-NDIS-PacketCapture** provider whenever you run the **Local Network Interfaces** scenario to capture data on the local computers running the Windows 7 or Windows 8 operating system.  
  
 For example, you can effectively create an adapter filter by selecting at least one or both of the **In** and **Out** check boxes for a chosen local host adapter. in the **System Network** section of the dialog. This action will define the adapter that passes the packet traffic and in the direction/s that you specified.  
  
 You can also create one or two logically-related **Fast Filter Groups** and apply the configuration to a selected adapter to isolate  specific data based on the filtering criteria, as described in [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
  
 **Remote Trace Scenarios**   
You can specify filtering configuration settings in the **Advanced Settings** dialog for the **Microsoft-Windows-NDIS-PacketCapture** provider whenever you run the **Remote Network Interfaces** or **Remote Network Interfaces with Drop Information** **Trace Scenarios**, to isolate traffic by the following:  
  
-   Selecting remote host adapters on which to capture traffic.  
  
-   Selecting a remote virtual machine (VM) adapter that is serviced by a Hyper-V-Switch, on which to capture traffic.  
  
-   Specifying the traffic direction and NDIS filter layers on which to intercept packet traffic for remote host adapters.  
  
-   Specifying the packet traversal path and Hyper-V-Switch extension layers on which to intercept packet traffic.  
  
-   Specifying other special filters that modify the scope of data retrieval, such as **Truncation**, **EtherType**, **IP Protocol Number**, **MAC Address**, and **IP Address** filters.  
  
 **Tip:** You can also apply these settings in other **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider, which includes capturing data on a local host.  
  
 **Remote Filtering Configuration** — you can specify filtering configuration settings in the **Advanced Settings** dialog for the **Microsoft-Windows-NDIS-PacketCapture** provider, after you select any **Trace Scenario** that uses the **Microsoft-Windows-NDIS-PacketCapture** provider to capture data on a target remote (or local) computer.  
  
 For a detailed explanation of all the filtering configurations that you can apply  for the **Microsoft-Windows-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
 **Keyword Filters** — although you can specify event **Keyword** and error **Level** filters for any provider that defines them, you have the option to specify a considerable number of **Keyword** filters from the **ETW Core** tab of the **Advanced Settings** dialog for the  **Microsoft-Windows-NDIS-PacketCapture** provider in both local and remote scenarios. For example, you can specify event **Keywords** for dropped packets, response time, and diagnostics.  
  
 For further details on applying event **Keyword** and error **Level** filters, see [System ETW Provider Event Keyword/Level Settings](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md).  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about capturing data from a remote host, see the [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md) section. However, some of the configuration settings for remote tracing are briefly described in the configuration settings table that is included in this section.   
___________________\_  
  
<a name="BKMK_CommonProvSettings"></a>   
## Common Provider Configuration Settings  
 The table that follows provides the details for  specifying filtering configuration settings for ETW message providers in the following common **Trace Scenario** types:  
  
-   **Local Network Interfaces** — using the **Microsoft-PEF-NDIS-PacketCapture** provider.  
  
-   **Remote Network Interfaces** — using the **Microsoft-Windows-NDIS-PacketCapture** provider.  
  
-   **Loopback and Unencrypted IPSEC** — using the **Microsoft-PEF-WFP-MessageProvider**.  
  
-   **Pre-Encryption for HTTPS** — using the **Microsoft-PEF-WebProxy** with Fiddler provider.  
  
 **Note:** The built-in **Trace Scenarios** included with Message Analyzer can contain a combination of PEF and Windows system ETW providers. By understanding how to configure settings for these provider types, as used in the common **Trace Scenarios** and described in the table that follows, you will also understand how to modify the providers in other default **Trace Scenarios**, as appropriate to your requirements.  
  
### Table 5. Common Provider Configuration Settings  
  
|Default Trace Scenarios|Configuration Settings|Property or Feature|Description|  
|-----------------------------|----------------------------|-------------------------|-----------------|  
|**Local Network Interfaces** <br />Capture local Link Layer traffic from NDIS|**Adapters**|**In, Out**|This feature is accessible from the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog. By selectively enabling or disabling the **In** and **Out** check boxes for adapters listed in this dialog, you can both enable specific adapters through which to capture message traffic and the direction in which to capture it. The adapters you can select in the dialog are enumerated on your system when the **Microsoft-PEF-NDIS-PacketCapture** provider is installed. By default, Message Analyzer enables local adapters for capturing data in both directions.<br /><br /> To prevent an adapter from capturing message traffic, simply deselect its **In** and **Out** check boxes.<br /><br /> **Note:** You can also isolate message traffic to a specific adapter by configuring a **Fast Filter** to contain its **LinkLevelAddress**, as described in the Fast Filters section of this table.|  
|**Local Network Interfaces** <br />Capture local Link Layer traffic from NDIS|**Fast Filters**|**Filter type**|This feature is accessible from the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog. It enables you to use a drop-down list to select the type of filters you want to configure, a **Group** to contain them, and the adapters to assign them to when configuring a **Local Network Interfaces** scenario. The **Fast Filters** that you can specify consist of the following:<br /><br /> -                      **OLP** — enables you to specify an offset length pattern (OLP) that filters for messages containing the pattern. For example, you might set an OLP to *34:8:7F* to return only messages that contain this particular OLP.<br /><br /> Operators that function with the OLP filter type consist of equal (=), not equal (!=), less than (\<), and greater than (>).<br /><br /> **Note:** As a result of complexities and the impact on performance, you should only configure a single OLP filter per adapter in the **Microsoft-PEF-NDIS-PacketCapture** provider settings, although different adapters can have different filters.<br /><br /> ____________________<br /><br /> **More Information** <br /> **To learn more** about OLP filtering, see [OLP Filters](../messageanalyzer_content/olp-filters.md).<br />____________________<br /><br /> -                      **LinkLevelAddress** — enables you to specify a Media Access Control (MAC) hardware address for which inbound and outbound traffic is targeted to a particular adapter device.  You can specify a **LinkLevelAddress** in a six-byte, hexadecimal format, similar to the following example:  *01-23-45-67-89-AB*.<br /><br /> -                      **IPv4Address** — enables you to isolate message traffic to a specified IPv4 address, by specifying a value such as the following in the text box to the right of the **Filter** type drop-down menu:  *192.168.1.1*<br /><br /> -                      **IPv6Address** — enables you to isolate message traffic to a specified IPv6 address, by specifying a value such as the following in the text box to the right of the **Filter** type drop-down menu:  *fe80::9de5:fc31:8856:58a8%11*<br /><br /> ____________________<br /><br /> **More Information** <br /> **To learn more** about configuring **Fast Filters** for the **Microsoft-PEF-NDIS-PacketCapture** provider and assigning them to specific adapters, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md). <br />____________________|  
|**Remote Network Interfaces** <br />Remote capture on Link Layer|**Adapters**|**Enabling**|This feature is accessible from the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog. By selecting the **Enabled** check boxes in this dialog for host adapters and/or adapters for virtual machines (VMs) that are serviced by a Hyper-V-Switch, you can specify the adapters through which to capture remote traffic, and in so doing, enable those adapters to receive any filtering configurations that you specify in the **Advanced Settings** dialog.<br /><br /> **Important:** If you want to capture traffic from a specific remote VM, you will need to select the VM in the Interface Selection  section of the **Advanced Settings** dialog and then specify a filter based on the VM's **MAC Address** to isolate the data. Otherwise, you will capture Hyper-V-Switch traffic that is destined for all VMs that are serviced by the switch, given that a Hyper-V-Switch driver cannot of itself distinguish between VMs.<br /><br /> The adapters that you can select in the dialog are enumerated on your system when you connect to a specified remote host. By default, Message Analyzer enables all adapters in the **Advanced Settings** dialog. To prevent traffic from being captured on a listed adapter, you can simply deselect it.<br /><br /> **Note:** You can also capture remote (or local) traffic in Promiscuous Mode, for adapters that support it, by simply selecting a **P-Mode** check box for a supporting adapter.|  
|**Remote Network Interfaces** <br />Remote capture on Link Layer|**Filters**|The types of filtering configurations that you can apply in remote tracing scenarios consist of the following:<br /><br /> -                      **All Layers** filter<br /><br /> - Packet **Truncation** filter<br /><br /> -                      **Direction** filter –<br /><br /> -                          **Ingress**/**Egress** packet direction path through NDIS filter stack when applied to host adapters.<br /><br /> -                          **Ingress**/**Egress** packet traversal path on the Hyper-V-Switch extension stack when applied to a switch adapter.<br /><br /> -                      **EtherType** filter<br /><br /> -                      **IP protocol number** filter<br /><br /> -                      **MAC Address** filter<br /><br /> -                      **IP Address** filter|The configuration for these filters is located in the **Filters** pane of the **Advanced Settings** dialog. From the dialog, you can choose the NDIS filter layers on which packets are intercepted in remote host adapters or on the Extension layers of a Hyper-V-Switch that services a remote VM adapter, for troubleshooting purposes. You can also set the direction in which to capture data on remote host adapters, and the packet traversal paths through a remote Hyper-V-Switch Extension stack. Other filters that you can specify include **Truncation**, **EtherType**, **IP Protocol Numbers**, **MAC Address**, and **IP Address** filters.<br /><br /> ____________________<br /><br /> **More Information** <br /> **To learn more** about how to configure such filters for a remote trace, see the [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md) and [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) topics. <br />____________________|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**WFP Layer Set**||Provides the following **WFP Layer Set** filters for **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**, so that you can control the direction in which packets are configured to pass at the Transport Layer for IPv4 and IPv6 traffic:<br /><br /> -                      **INBOUND_TRANSPORT_V4**<br /><br /> -                      **OUTBOUND_TRANSPORT_V4**<br /><br /> -                      **INBOUND_TRANSPORT_V6**<br /><br /> -                      **OUTBOUND_TRANSPORT_V6**|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**INBOUND_TRANSPORT_V4**|**Check box select/unselect**|A kernel-mode TCP/IP stack filter that operates in the *receive* path at the Transport Layer before any processing occurs at that layer. This layer is above IPsec processing at the Network layer and below Application Level Enforcement (ALE) layers. Therefore when selected, this filter enables capture of all *inbound* packets at the Transport Layer, with the exclusion of any that are dropped at the Network layer.<br /><br /> You can select or unselect this filter to capture or not capture TCP/IPv4 packets, respectively, at the Transport Layer.|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**OUTBOUND_TRANSPORT_V4**|**Check box select/unselect**|A kernel-mode TCP/IP stack filter that operates in the *send* path at the Transport Layer before any processing occurs at that layer. This layer is above IPsec processing at the Network layer and below Application Level Enforcement (ALE) layers. Therefore when selected, this filter enables capture of all *outbound* packets at the Transport Layer, with the exclusion of any that are dropped at the Network layer.<br /><br /> You can select or unselect this filter to capture or not capture TCP/IPv4 packets, respectively, at the Transport Layer.|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**INBOUND_TRANSPORT_V6**|**Check box select/unselect**|Functionally similar to the inbound IPv4  version of this filter type, this is a kernel-mode TCP/IP stack filter layer in the *receive* path that you can select or unselect to capture or not capture inbound TCP/IPv6 packets, respectively, at the Transport Layer.|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**OUTBOUND_TRANSPORT_V6**|**Check box select/unselect**|Functionally similar to the outbound IPv4  version of this filter type, this is a kernel-mode TCP/IP stack filter layer in the *send* path that you can select or unselect to capture or not capture inbound TCP/IPv6 packets, respectively, at the Transport Layer.|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing|**Fast Filters**  <sup>2</sup>|**FilterType**|Improves performance — for example, when processing large volumes of traffic — by enabling you to filter out unwanted traffic via IP address and port filters. You can specify the type of **Fast Filter** you want to apply to a **Loopback and Unencrypted IPSEC** trace, by selecting it from a drop-down list that includes the following items:<br /><br /> -                      **IPv4** —should be specified in a format similar to the following:  *192.168.1.1*.<br /><br /> -                      **IPv6** — should be specified in a format similar to the following:  *2001:4898:2b:3:d824:99e9:7371:31d9* or *fe80::6e9c:edff:fe94:ec0011*<br /><br /> -                      **TCP port** — should be specified in integer format, for example:  *80*.<br /><br /> -                      **UDP port** — should be specified in integer format, for example: *53*.<br /><br /> **Note:** For tracing with the **Microsoft-PEF-WFP-MessageProvider**, the specified filter is applied only to the corresponding layer(s).  For example:   *IPv4Address==192.168.1.1* is applied to Transport_V4 inbound and outbound layers.  There is no filter on the V6 counter parts.  If the V6 layers are enabled, you will see frames of IPv4 and IPv6 packets.  If you want to see only IPv4 messages, then enable only the IPv4 layers in the **WFP Layer Set**; then configure a **Fast Filter** with an **IPv4** address.<br /><br /> TCP and UDP port numbers should be integers between 0 and 65535.|  
|**Loopback and Unencrypted IPSEC** <br />Windows Filtering Platform Tracing||**Filter text box**|Provides the entry point where you specify a value for the type of filter that you selected in a **Fast Filter** drop-down list.|  
|**Pre-Encryption for HTTPS** <br />Capture HTTPS client-side unencrypted traffic with the **Microsoft-Pef-WebProxy** with Fiddler provider|**HostnameFilter**|Host address in the format: *www.bing.com*|Filters HTTP packets from a web server based on the host name.|  
|**Pre-Encryption for HTTPS** <br />Capture HTTPS client-side unencrypted traffic with the **Microsoft-Pef-WebProxy** with Fiddler provider|**PortFilter**|Port number in a format similar to the following: *80*|Filters packets by numbered ports only.|  
|**Pre-Encryption for HTTPS** <br />Capture HTTPS client-side unencrypted traffic with the **Microsoft-Pef-WebProxy** with Fiddler provider|**HTTPS Client Certificate**|A certificate file in *.cer format.|Specifies the .cer file for Fiddler to provide to a web server that requires certification validation.|  
|**Pre-Encryption for HTTPS** <br />Capture HTTPS client-side unencrypted traffic with the **Microsoft-Pef-WebProxy** with Fiddler provider|**Reuse Server Connections**<br /><br /> **Reuse Client Connections**|**Enabling check boxes**|When selected, keeps server and/or client connections alive to improve performance, rather than re-creating new connections.|  
|**System ETW Providers**|Event **Keyword** filter|**Keywords(All)**<br /><br /> **Keywords(Any)**|Select event **Keywords** from the **ETW Keyword Filter Property** dialog that is accessible from the **ETW Core** tab of the **Advanced Settings** dialog for a particular message provider. Predefined **Keywords** in the **ETW Keyword Filter Property** dialog are selectable by **Value** name and translate to 16-digit hexadecimal numbers, for example:  *0x00000000000000C0*.|  
|**System ETW Providers**|**Level** filter|**LogAlways**<br /><br /> **Critical**<br /><br /> **Error**<br /><br /> **Warning**<br /><br /> **Information**<br /><br /> **Verbose**|Settings enable filtering based on the severity or verbosity of error events., or in the case of the **LogAlways** level, ensures that logging of all **Levels** will always occur.|  
  
 <sup>2</sup> When capturing data in **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**, setting a **Fast Filter** such as **IPAddress** == *192.168.1.1* does not prevent IPv6 traffic from being captured because IPv4 and IPv6 messages are retrieved from separate layers in these scenarios and the **Fast Filter** applies only to the IPv4 layer.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about creating **Fast Filter** and adapter filter configurations for a Live Trace Session that uses the **Local Network Interfaces** **Trace Scenario**, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
**To learn more** about how to select adapters and specify filters for a Live Trace Session that uses the **Remote Network Interfaces** **Trace Scenario**, see [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md) and [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](../messageanalyzer_content/using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
**To learn more** about configuring system ETW Providers with event **Keyword** and **Level** filters, see [System ETW Provider Event Keyword/Level Settings](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md).   
___________________\_  
  
## See Also  
 [PEF Message Providers](../messageanalyzer_content/pef-message-providers.md)