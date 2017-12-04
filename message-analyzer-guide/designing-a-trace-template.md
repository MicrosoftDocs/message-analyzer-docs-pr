---
title: "Designing a Trace Template | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0240983-9e00-4600-9d40-2f9d38252a45
caps.latest.revision: 25
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Designing a Trace Template
Designing a trace template consists of adding providers, filters, and other settings to the trace configuration, just as you would do when configuring any Live Trace Session prior to running it, only you save the trace template as a **Trace Scenario** in the **Trace Scenarios** Library instead of running it. From the **Select Scenario** drop-down in the **New Session** dialog, you can add a default **Trace Scenario** with a predefined provider configuration to your trace template design by selecting one in the **Trace Scenarios** Library. You can then modify the provider configuration to achieve specific results that you require. For example, you might create a filter configuration that retrieves specific data in a Live Trace Session where you run your scenario template. Moreover, you can do the following and more when configuring your own trace template:  
  
-   Specify driver-level **Fast Filter Groups** in the default **Local Network Interfaces (Win 8 and earlier)** **Trace Scenario** provider settings, by using the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog that is accessible by clicking the **Configure** link for the **Microsoft-PEF-NDIS-PacketCapture** provider in the **ETW Providers** list of the **New Session** dialog.  
  
-   Add a custom written **Session Filter** to your trace template or add one that is predefined from the centralized Filter Expression **Library**.  
  
-   Modify certain default **Trace Scenario** provider capture settings, such as specifying **WFP Layer Set** filters, WFP **Fast Filters**, or dropped packet logging for **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**.  
  
-   Specify NDIS stack or Hyper-V-Switch extension **Layer** and packet **Direction** filtering, packet **Truncation**, **EtherTypes**, and **IP protocol numbers**, and filter on **MAC addresses** and **IP addresses** in the **Remote Network Interfaces (Win 8.1 and later)**  **Trace Scenario** that uses the **Microsoft-Windows-NDIS-PacketCapture** provider. These settings are available from the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog.  
  
-   Customize the trace template configuration by adding system ETW providers that enhance the scope of data capture.  
  
-   Modify or add an event **Keyword** bitmask filter and/or error **Level** settings in the system **ETW Provider** configuration, if the provider defines them.  
  
-   Use the **ETW Session – Advanced Configuration** dialog to specify advanced buffer configuration settings that are passed to the ETW Session Controller that will manage your Live Trace Session.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about modifying provider configurations, see [Modifying Default Provider Settings](modifying-default-provider-settings.md).  
**To learn more** about saving a trace template as a **Trace Scenario**, see [Saving Trace Scenarios](saving-trace-scenarios.md).   
**To learn more** about creating **Fast Filters** for the **Local Network Interfaces (Win 8 or earlier)** scenario, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).   
**To learn more** about how to configure advanced filters for **Remote Network Interfaces** scenarios, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
**To learn more** about creating filter expressions, see [Writing Filter Expressions](writing-filter-expressions.md).   
**To learn more** about how to configure advanced settings for ETW sessions, see [Specifying Advanced ETW Session Configuration Settings](specifying-advanced-etw-session-configuration-settings.md).   
___________________\_