---
title: "Trace Scenario Overview | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: f58fbe05-5fc6-451e-b783-c35af1a1819c
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Trace Scenario Overview
You might need to have quick access to common trace configurations that you can use on a regular basis to capture messages. Message Analyzer anticipates this need by enabling you to design and save *trace templates* that contain specific providers and filters that you configure for specific purposes.  To do this, you can use the configuration features of a Live Trace Session to design and then save the template as a **Trace Scenario**. Your trace template can encapsulate specific tracing functionality of your own design, with one or more predefined providers and optional filter configurations that you can either run as-is, or modify to further customize its functionality before running it or resaving it. After you save the trace template, it becomes part of the **Trace Scenarios** Library and you can then access it as you would any other **Trace Scenario**.  
  
 To be clear, a distinction should be made between the concept of a **Trace Scenario** and an actual Live Trace Session. Generally speaking, all **Trace Scenarios** are trace templates. Therefore any custom trace template of your own design, and even the predefined **Trace Scenarios** that are provided with Message Analyzer by default, contain no data, as they are simply *templates* for a Live Trace Session. At the time when you select a **Trace Scenario** and providers appear in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog, you have a predefined provider configuration and you can optionally configure filters to define the scope of messages that you capture, but you do not yet have any trace results. A **Trace Scenario** becomes a Live Trace Session after you start the trace and capture data with it. Thereafter, you can save the Live Trace Session results in one of the Message Analyzer native file formats.  
  
 You can run any **Trace Scenario** that you wish on demand, including any custom trace template that you saved as a **Trace Scenario** in the **Trace Scenarios** Library. In addition, all **Trace Scenario** Library items are part of the Message Analyzer Sharing Infrastructure. As a result, you and other team members have mutual shared access to custom **Trace Scenarios** that you create. To export or import one or more **Trace Scenarios** to or from a designated file share or other location, you can use the **Manage Trace Scenario** dialog, which is accessible by clicking the **Manage Trace Scenarios** button from the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about the Message Analyzer Sharing Infrastructure, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.   
**To learn more** about the common **Manage \<AssetType>** dialog, see [Managing User Libraries](managing-user-libraries.md).   
---