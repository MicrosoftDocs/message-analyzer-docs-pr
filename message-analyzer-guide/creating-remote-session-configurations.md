---
title: "Creating Remote Session Configurations | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44af6165-6229-4e8a-86ce-ced3ba04b4d1
caps.latest.revision: 11
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Creating Remote Session Configurations
This section describes how to set up a **Trace Scenario** that will capture data on a target remote computer. It begins with operating system requirements and then provides instructions on how to configure the source and host computers for a remote capture, which includes configuring the WinRM service and Trusted Hosts list.   Next, you are shown how to specify one or more target computers for remote capture, along with how to specify host connection data.  
  
 To provide a data source for your remote capture session, you will need to specify a remote data provider, which in this case is the **Microsoft-Windows-NDIS-PacketCapture** provider that uses Windows Management Instrumentation (WMI) for its remote capabilities. By default, this provider is contained in the built-in **Remote Network Interfaces** **Trace Scenario** that you can select from the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog during Live Trace Session configuration. After you select this **Trace Scenario**, you can specify advanced settings for the **Microsoft-Windows-NDIS-PacketCapture** provider from the associated **Advanced Settings** dialog, as indicated below. This includes enabling and disabling adapters on which to capture, optionally specifying promiscuous mode for supporting adapters, specifying various types of low-level stack or Hyper-V-Switch extension layer filters, packet direction filters, and configuring various types of special filters such as **EtherTypes** and **IP Protocol Numbers**.  
  
 The content is covered in the following topics, which includes detailed descriptions of how to use the **Advanced Settings** dialog for the **Microsoft-Windows-NDIS-PacketCapture** provider:  
  
 [Configuring a Remote Capture](configuring-a-remote-capture.md)   
 [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md)  
  
## See Also  
 [Microsoft-Windows-NDIS-PacketCapture Provider](microsoft-windows-ndis-packetcapture-provider.md)   
 [Configuring a Live Trace Session](configuring-a-live-trace-session.md)