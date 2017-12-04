---
title: "PEF-NDIS Provider Manifest | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d81f1ec-dbfa-4849-8211-6c2d29e4cab1
caps.latest.revision: 24
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# PEF-NDIS Provider Manifest
The manifest for the **Microsoft-PEF-NDIS-PacketCapture** provider defines its contract with an ETW Controller in terms of the events that are issued by the provider, which are in turn consumed by Message Analyzer. The **Microsoft-PEF-NDIS-PacketCapture** provider and its manifest are installed and registered on your machine when you install Message Analyzer. You can find the **Microsoft-PEF-NDIS-PacketCapture** provider manifest file in the following location:  
  
 `C:\Windows\System32\Microsoft-Pef-NDIS-PacketCapture.man`  
  
 In this file you can view the event definitions, tasks, opcodes, keyword bitmask and level specifiers, a channel definition, and template information.  
  
> [!NOTE]
>  You will find the Microsoft-Pef-NDIS-PacketCapture.man file in the specified location only after installing Message Analyzer on computers that are running the Windows 7, Windows 8, or Windows Server 2012 operating system.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the contents of provider manifests, see [Event Manifest](../messageanalyzer_content/etw-framework-conceptual-tutorial.md#BKMK_EventManifest).   
**To learn more** about how Message Analyzer uses provider manifests, see [Understanding Event Parsing with a Provider Manifest](../messageanalyzer_content/understanding-event-parsing-with-a-provider-manifest.md).  
**To learn more** about obtaining a provider manifest if you are missing one, see [Generating a Provider Manifest](../messageanalyzer_content/generating-a-provider-manifest.md).  
___________________\_