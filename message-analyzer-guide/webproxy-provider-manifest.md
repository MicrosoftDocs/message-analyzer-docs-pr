---
title: "WebProxy Provider Manifest | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3edfd760-e4a5-432a-884c-c39509827c9b
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# WebProxy Provider Manifest
The manifest for the **Microsoft-Pef-WebProxy** provider defines its contract with an ETW Controller in terms of the events that are issued by the provider, which are in turn consumed by Message Analyzer. The **Microsoft-Pef-WebProxy** provider and its manifest are installed and registered on your machine when you install Message Analyzer. You can find the **Microsoft-Pef-WebProxy** provider manifest file in the following location:  
  
 `C:\Windows\System32\Microsoft-Pef-WebProxy.man`  
  
 In this file you can view the event definitions, tasks, opcodes, keyword bitmask and level specifiers, a channel definition, and template information.  
  
---  
  
 **More Information**   
 **To learn more** about the contents of provider manifests, see [Event Manifest](etw-framework-conceptual-tutorial.md#BKMK_EventManifest).  
**To learn more** about how Message Analyzer uses provider manifests, see [Understanding Event Parsing with a Provider Manifest](understanding-event-parsing-with-a-provider-manifest.md).  
**To learn more** about obtaining a provider manifest if you are missing one, see [Generating a Provider Manifest](generating-a-provider-manifest.md).   
---