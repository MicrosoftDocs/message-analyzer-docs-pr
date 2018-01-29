---
title: "Capturing Message Data | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 183be669-3583-4187-b0a5-1929f84d1259
caps.latest.revision: 36
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Capturing Message Data

This section describes how to create and configure a new Live Trace Session with Message Analyzer, so that you can quickly begin capturing data from your system. This section also discusses how to focus your Live Trace Session on capturing messages that contain specific types of data, through the selection or modification of various settings, for example selecting one or more message providers, adding built-in or custom filters, and/or specifying a **Parsing Level** to the capture configuration. Other capabilities enable you to focus on capturing remote traffic on specified hosts and virtual machines (VMs), in addition to decrypting certain types of data.  
  
---
  
 **Go To Session Configuration**   
Go directly to an overview of Live Trace Session configuration workflow, filtering options, and the features that are available for configuring and starting a new Live Trace Session:  
[Configuring a Live Trace Session](configuring-a-live-trace-session.md)  

---
  
 **What You Will Learn**   
In the topics of this section, you will learn how to accomplish the tasks indicated below.  

---  
  
**[Targeting Live Data as an Input Source](targeting-live-data-as-an-input-source.md)**  — learn how to target specific types of message data to capture, with the use of built-in (default) **Trace Scenarios** and the message providers they contain. Also learn about accessing the built-in **Trace Scenarios** that Message Analyzer provides, review options for instantly starting a Live Trace Session with a single click where no further configuration is needed, and read an overview about optimizing capture configurations. In the subtopics of this section, you can also review detailed information about the following:  
  
-   Microsoft Protocol Engineering Framework (PEF) message providers, along with various types of filters you can use to narrow the focus of live captures.  
  
-   The **Microsoft-Windows-NDIS-PacketCapture** provider, with its remote capture capability and unique filtering configurations.  
  
**[Configuring a Live Trace Session](configuring-a-live-trace-session.md)**  — examine an overview of Live Trace Session configuration workflow, read a **Trace Scenario** configuration overview, and review Live Trace Session configuration features that enable you to perform tasks such as:  
  
-   Selecting a built-in **Trace Scenario**.  
  
-   Using custom **Trace Scenario** templates.  
  
-   Adding system ETW Providers to a Live Trace Session and modifying settings for PEF and other ETW Providers.  
  
-   Selecting specific data from a Live Trace Session with the use of a **Session Filter** or by setting a **Parsing Level**.  
  
-   Modifying the settings of the underlying ETW session, to which message providers are enabled.  
  
-   Using the remote tracing capabilities of Message Analyzer.  
  
-   Selecting a data viewer for the trace results.  
  
-   Using the Message Analyzer decryption feature.  
  
**[Creating and Managing Custom Trace Scenarios](creating-and-managing-custom-trace-scenarios.md)**  — learn how to create your own custom **Trace Scenarios**, save and manage your scenarios, run them on demand, and share them with others.  
  
**[Performing a Live Capture](performing-a-live-capture.md)**  — learn about the methods you can use to perform a live capture, which includes automation that enables you to instantly start a live capture with a single click, or manually customizing the capture configuration of a Live Trace Session before you run it.  
  
**[Procedures: Using the Network Tracing Features](procedures-using-the-network-tracing-features.md)**  — perform example procedures that demonstrate various aspects of live capture functionality, as discussed throughout this section.  
  
## Using the Default Trace Scenarios  
 When configuring a Live Trace Session, you are advised that your initial approach should be to use one of the default **Trace Scenarios** that each contain one or more message providers. By learning about the type of data you can capture with the use of default providers, you will understand better how to choose the **Trace Scenario** that you require based on the provider/s that such scenarios contain. To further enhance and optimize a default **Trace Scenario**, you can specify various filtering configurations, as described in this section.  
  
## Considering System ETW Providers  
 Only if using a default **Trace Scenario** fails to isolate the data you wish to capture should you consider customizing a Live Trace Session with one or more system ETW Providers that are installed and registered on your computer. For example, you might end up capturing more data than expected with one of the default **Trace Scenarios** such that packets are being dropped by Message Analyzer. If this is the case, you might consider changing your capture configuration to use one or more selected system ETW Providers instead of a built-in **Trace Scenario** to more finely tune the scope of data capture. You also have the option to *customize* any of the built-in **Trace Scenarios** by either adding selected system ETW Providers to the scenario or by modifying the existing system ETW Provider configuration in the scenario. If you elect to customize using either of these methods, Message Analyzer enables you select specific data to capture by providing facilities to modify the **Keyword** and/or **Level** filtering configuration of any system ETW Provider, as described in [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
  
> [!TIP]
>  Modifying  ETW Provider filtering configurations is applicable to the PEF providers, as described in the [PEF Message Providers](pef-message-providers.md) section, given that PEF providers are also instrumented for ETW **Keywords** and error **Levels**. In addition, these modifications include configuration of **Keyword** and **Level** filters for the **Windows-NDIS-PacketCapture** provider, as described in the [Microsoft-Windows-NDIS-PacketCapture Provider](microsoft-windows-ndis-packetcapture-provider.md) topic. Note that customizing a built-in **Trace Scenario** to optimize your overall capture configuration can also include the application of many types of filters other than **Keyword** and **Level** filtering for the indicated message providers.  
  
 To successfully create a functional tracing configuration with one or more added system ETW Providers, you should be familiar with the workings of system ETW Providers before you employ them; however, you are free to experiment to see what results you obtain. For this reason, adding system ETW Providers to a Live Trace Session is recommended for advanced Message Analyzer users. However, Message Analyzer ships with several built-in **Trace Scenarios** that contain system ETW Providers, and these can serve as usage examples for new users. You can see a list of system ETW Providers in the **Add System Providers** dialog, which is accessible by clicking the **Add System Providers** item in the **Add Providers** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about how to specify one or more system ETW Providers for a Live Trace Session configuration, see [Adding a System ETW Provider](adding-a-system-etw-provider.md).  
**To learn more** about specifying **Keyword** and **Level** filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
**To learn more** about other filtering configurations that you can apply to a built-in **Trace Scenario**, see the following topics:  

- [Selecting Data to Capture](selecting-data-to-capture.md)  
- [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md)  
- [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md)  

---  
  
## See Also  

[Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md)   
[Editing Existing Sessions](editing-existing-sessions.md)