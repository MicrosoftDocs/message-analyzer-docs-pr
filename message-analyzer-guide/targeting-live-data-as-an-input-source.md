---
title: "Targeting Live Data as an Input Source | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70e5a727-4837-45e7-9ddc-da8d0cbaa31c
caps.latest.revision: 31
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Targeting Live Data as an Input Source
Message Analyzer enables you to capture live traffic from network protocols, ETW-instrumented Windows system components, certain devices, and application communications. To capture this traffic, Message Analyzer makes use of several Microsoft Protocol Engineering Framework (PEF) providers that are designed to capture messages at different stack entry points (layers), which includes the capture of events at the ETW layer, along with a host of other Windows ETW-instrumented message providers that capture events from various Windows components at the ETW layer, for example, DNS, DHCP, Active Directory, and many other providers that are available from the **Add System Providers** dialog.  As such, these message providers and various combinations thereof are the means of targeting live data of different types as input to Message Analyzer. Moreover, certain message providers are combined and included in built-in **Trace Scenarios** to optimize each scenario for capturing specific data. These scenarios are available for selection when you are configuring a Live Trace Session.  
  
## Using Trace Scenarios as an Input Source  
 The following are a few examples of built-in **Trace Scenarios** that serve as input sources for Message Analyzer. They use one or more message providers to return specific types of message data after you start a Live Trace Session:  
  
-   **Local Network Interfaces** scenario — uses the **Microsoft-PEF-NDIS-PacketCapture** provider on computers running the Windows 7, Windows 8, or Windows Server 2012 operating systems, or uses the **Microsoft-Windows-NDIS-PacketCapture** provider on computers running Windows 8.1, Windows Server 2012 R2, Windows 10, or later. Captures traffic at and above the Link Layer. Note that the **Microsoft-PEF-NDIS-PacketCapture** provider has an **Advanced Settings** dialog that enables you to configure **Fast Filter** groups. The **Microsoft-Windows-NDIS-PacketCapture** provider also has an **Advanced Settings** dialog that provides special features and capabilities, for example, specifying advanced filtering configurations when capturing traffic from remote hosts and virtual machines (VMs) that are serviced by a Hyper-V-Switch.  
  
    > [!IMPORTANT]
    >  The **Microsoft-Windows-NDIS-PacketCapture** provider uses Windows Management Instrumentation (WMI) to capture remote traffic from any target host that is running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, from any computer that is also running one of these operating systems.  
  
-   **Loopback and Unencrypted IPSEC** scenario — uses the **Microsoft-Pef-WFP-MessageProvider** to capture local traffic above the IP/Network layer, which includes transport messages such as TCP, UDP, and anything above these; this includes other messages above the IP layer, for example, those that are issued by the DNS protocol, SOAP, and RPC. Note that the **Microsoft-Pef-WFP-MessageProvider** has an **Advanced Settings** dialog that enables you to configure **Fast Filters** and **WFP Layer Set** filters.  
  
    > [!IMPORTANT]
    >  The **Microsoft-Pef-WFP-MessageProvider** uses WMI to facilitate remote capabilities on Windows 10 (and later) computers only. In practice, this means that you can target a Windows 10 computer from which to capture remote traffic and return it to a computer that is running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, where you started a **Trace Scenario** that contains the **Microsoft-Pef-WFP-MessageProvider**.  
  
-   **Pre-Encryption for HTTPS** scenario — uses the **Microsoft-Pef-WebProxy** provider, which is based on Fiddler, to capture local HTTP client browser traffic at the Application Layer prior to HTTPS encryption. Note that the **Microsoft-Pef-WebProxy** provider has an **Advanced Settings** dialog that enables you to configure **Hostname** and **Port** filters.  
  
    > [!NOTE]
    >  To enable this scenario, you must have Fiddler installed on your computer. If you do not, then go  [here](http://fiddler2.com/fiddlercore) to download and install the Fiddler Library from Telerik.  
  
-   **USB2** scenario — uses the **Microsoft-Windows-USB-USBPORT** and **Microsoft-Windows-USB-USBHUB** providers to capture events related to USB2 devices plugged into a USB port, for troubleshooting such devices.  
  
-   **SMB Client and Firewall** scenario — uses the **Microsoft-Windows-SMBClient** and **Microsoft-Pef-WFP-MessageProvider** to capture SMB2 client traffic with message headers only, along with capturing network traffic above the IP layer for correlation with the SMB2 traffic, respectively.  
  
> [!NOTE]
>  To learn more about PEF message providers and the **Microsoft-Windows-NDIS-PacketCapture** provider, see the **More Information** section below.  
  
## Selecting a Built-In Trace Scenario  
 You can locate the built-in **Trace Scenarios** in the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog, as shown in the figure that follows.  
  
 ![Message Analyzer Built&#45;In Trace Scenarios for Live Trace Session Configuration](media/03bd68cc-4bec-4ece-8aae-5f40a6d1be93.png "Fig19-Message Analyzer Built-In Trace Scenarios for Live Trace Session Configuration")  
  
 **Figure 19:  Message Analyzer Built-In Trace Scenarios for Live Trace Session Configuration**  
  
 These **Trace Scenarios** encapsulate built-in message provider configurations that are optimized to capture specific types of data in a Live Trace Session. To add a basic **Trace Scenario** with no additional configuration required for a Live Trace Session, you can select a scenario in the **Select Scenario** drop-down list in the **New Session** dialog. The scenario that you choose should contain the provider/s that capture data at a particular stack layer, or should focus on capturing messages from some device, application, or system component in which you are interested. Note that a description is provided with each **Trace Scenario** in the **Select Scenario** drop-down list so that you can get a sense of its functionality. After you select a scenario, you can begin capturing data immediately with a single click on the **Start** button of the **New Session** dialog. Thereafter, the message data displays in the data viewer that is set as the default, for example, the **Analysis Grid** viewer.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the functions of the **Trace Scenarios** provided by default in every Message Analyzer installation, see the [Built-In Trace Scenarios](built-in-trace-scenarios.md) topic.  
___________________\_  
  
## Quick Start Trace Scenarios  
 Message Analyzer also enables you to use a few different methods to start a live trace immediately, with no initial configuration required. These methods also make use of built-in **Trace Scenarios**, which contain message providers that are tailored to capture specific types of data, as follows:  
  
-   **Start Local Trace** — click this button on the **Start Page** to begin capturing messages at and above the Link Layer with the **Microsoft-Windows-NDIS-PacketCapture** provider in the **Local Network Interfaces** scenario on your Windows 8.1, Windows Server 2012 R2, or Windows 10 computer, or with the **Microsoft-PEF-NDIS-PacketCapture** provider in the **Local Network Interfaces** scenario on your local Windows 7, Windows 8, or Windows Server 2012 computer.  
  
-   **Favorite Scenarios** — click this drop-down list on the Message Analyzer global toolbar and then click one of the favorited **Trace Scenarios** in the list, or select a **Trace Scenario** from the **Favorite Scenarios** list on the **Start Page**. The **Trace Scenarios** that are included in the **Favorite Scenarios** list by default are the **Local Network Interfaces**, **Loopback and Unencrypted IPSEC**, and **Pre-Encryption for HTTPS** scenarios, which capture messages at and above the Link Layer, above the IP/Network Layer, and unencrypted at the Application Layer, respectively. **Favorite Scenarios** are also accessible from the Message Analyzer **File** menu. Note that you can set other **Trace Scenarios** to Favorite status as you discover their compatibility with your needs.  
  
<a name="BKMK_ETWProvidersInputSource"></a>   
## Using System ETW Providers as an Input Source  
 In a Live Trace Session, instead of capturing message data through a built-in **Trace Scenario**, you have the option to specify one or more Windows system ETW Providers from the **Add System Providers** dialog, which is accessible by clicking the **Add System Providers** item in the **Add Providers** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog. Although there are no restrictions on using these providers, you should be familiar with the type of data they capture before you use them. Otherwise, it might be difficult to make sense of the data you capture.  
  
 Possible information sources that you might consult to learn more about the type of data that system ETW Providers capture consist of the following:  
  
-   **Advanced Settings** dialog — click an ellipsis (**…**) on the **ETW Core** tab of the **Advanced Settings** dialog for any message provider to view a list of **Keyword** filters that such providers make available for selection, as described in [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
  
-   **Provider manifest files** — these are typically cached on your machine. The manifests typically include **Keywords** that define the events that a provider captures and can also contain event descriptions that can be useful when assessing ETW Provider functionality. To see an example of a simple manifest, see the [Event Manifest](etw-framework-conceptual-tutorial.md#BKMK_EventManifest) topic in the [ETW Framework Conceptual Tutorial](etw-framework-conceptual-tutorial.md).  
  
-   **Windows Events Provider Explorer (WEPExplorer)** — a graphic utility that enables you to display metadata from the manifest of each system ETW Provider that is installed and registered on your system. The metadata includes event **Keywords**, error **Levels**, **Opcodes**, **Channels**, and so on. For further details, see [Windows Events Provider Explorer](http://lallouslab.net/2016/01/25/windows-events-providers-explorer/) on the web.  
  
-   **Event Trace Sessions** — view **Keyword** configurations for various ETW Providers in live sessions that you can view with Performance Monitor, as described in [Finding System ETW Provider Metadata](system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords). If you select an ETW Provider in the **Providers** list in the **Properties** dialog for a particular session and then click the **Edit** button, you can display the list of **Keywords** that were originally specified in the manifest as the selected provider was developed. This can give you an indication of the type of messages that the selected ETW Provider will capture. In most cases, you can also locate such providers in the previously mentioned **Add System Providers** dialog when you are configuring a Live Trace Session in Message Analyzer.  
  
-   **Community knowledge bases** — you may be able to find information on optimized ETW Provider configurations from sources such as blogs and other social media.  
  
## Optimizing Data Capture Configurations  
 There are several ways that you can optimize your data capture configurations. Most of them involve additional filtering of some sort. Other methods include specifying a **Trace Scenario** or ETW message provider that captures specific types of messages, or messages at different Layers, as previously indicated. The goal is to maintain optimal performance while capturing the least amount of data to solve the problem at hand. For example, by specifying a **Session Filter**, ETW **Keyword** filter, **Fast Filter**, **Parsing Level**, a **Trace Scenario** that focuses on messages at a particular Layer, or by applying other advanced filtering techniques, you can optimize the process of capturing data in a Live Trace Session to achieve the following:  
  
-   Reduced message count in a more manageable data set that focuses on specific data only.  
  
-   Faster performance and reduced use of system resources when capturing message data.  
  
-   A more streamlined data analysis process.  
  
-   A focused set of messages that expedites the analysis process for others with whom you are sharing your results.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using **Session Filters**, see [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md).  
**To learn more** about using **Keyword** filters, see [Adding a System ETW Provider](adding-a-system-etw-provider.md) and [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
**To learn more** about using **Fast Filters**, see [PEF-NDIS Fast Filters](pef-ndis-fast-filters.md) and [PEF-WFP Fast Filters](pef-wfp-fast-filters.md).  
**To learn more** about using **Parsing Levels**, see [Setting the Session Parsing Level](setting-the-session-parsing-level.md).  
**To learn more** about the capabilities of the **Microsoft-Windows-NDIS-PacketCapture** provider, see the [Microsoft-Windows-NDIS-PacketCapture Provider](microsoft-windows-ndis-packetcapture-provider.md) topic.   
___________________\_  
  
## Session Configuration Workflow and Features  
 The linked section immediately below provides a general workflow that you can follow when configuring a Live Trace Session. It also contains subtopics that describe the features and functions that you can use when configuring a Live Trace Session:  
[Configuring a Live Trace Session](configuring-a-live-trace-session.md)  
  
## See Also  
 [Built-In Trace Scenarios](built-in-trace-scenarios.md)   
 [PEF Message Providers](pef-message-providers.md)