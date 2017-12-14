---
title: "Generating a Provider Manifest | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6eac0e53-63f1-46ce-82d3-0a195af84f06
caps.latest.revision: 32
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Generating a Provider Manifest
You might need to generate a provider manifest to ensure that Message Analyzer can parse ETW messages on a destination computer if the ETW events were captured on another source computer and the destination computer has no corresponding manifest to understand the data format. You might also have a destination computer with a manifest that is out-of-date with respect to the source computer manifest that was included in an ETL file. To accommodate these requirements, you can generate and save a manifest in the following ways:  
  
-   **Automatically** — requires that Message Analyzer is installed on the source computer. For this method, you configure a Live Trace Session and specify one or more ETW providers and then perform a capture of ETW events. When you save a trace that used one or more ETW providers to capture live data, Message Analyzer automatically attaches the manifest for each ETW provider in use to the trace.  
  
    > [!NOTE]
    >  Manifests for the **Microsoft-PEF-NDIS-PacketCapture**, **Microsoft-PEF-WFP-MessageProvider**, and **PEF-WebProxy** providers are installed on your system by default when you install Message Analyzer. Also, during Message Analyzer installation, all the system ETW providers that are registered on your system are enumerated and their manifests are automatically obtained.  
  
-   **Manually** — Message Analyzer is not installed on the source computer, or the manifest on the destination computer is out of date. In these cases, you must employ standard external tools to perform the trace and generate a manifest for the provider/s in use. For example, to capture the ETW events, you might use a command-line tool such as **netsh** or **logman**. When you are ready to save the manifest for the ETW trace, or if you already have an ETL file without a manifest, you can run the command-line tool *Tracerpt* with the following command string to generate the manifest file with a .man extension:  
  
     `Tracerpt –l [ETWTrace file | *.etl file]  –export [filename.man]`  
  
     This command exports the schema for the ETW events that were captured and saved to the specified event trace file or log (*.etl). For more information about Tracerpt commands, specify the following help switch:  
  
     `Tracerpt /?`  
  
    > [!TIP]
    >  You might be able to obtain a manifest from [InsightWeb](http://go.microsoft.com/fwlink/?LinkId=523819) as well, if you have access to internal Microsoft sites.  
  
> [!IMPORTANT]
>  As an alternative to the previous methods, you may be able to use the following tool to create a manifest:  
>   
>  -   A new Visual Studio extension known as the [Microsoft EventRegister Tool](https://www.nuget.org/packages/Microsoft.Diagnostics.Tracing.EventRegister) is available from a Nuget package.  
>   
>      This extension includes an EventSource class and other related classes in the Microsoft.Diagnostics.Tracing namespace, which enable you to write to the Event Log and generate a manifest at build time. For additional background information, see [Getting Started with Semantic Logging](https://blogs.endjin.com/2014/04/getting-started-with-semantic-logging/)  
  
 At this point, you should have one of the following from the source machine:  
  
-   A .matu or .matp file with the manifest information automatically attached.  
  
-   A trace file or *.etl log with a separate \*.man file.  
  
 If you have a .matu or .matp file with the required manifest attached, you can simply load the file and Message Analyzer should be able to parse the messages.  If you manually generated the manifest for an ETL file, you will need to place the manifest \<filename.man> in the following folder prior to loading the log data into Message Analyzer:  
  
 `%localappdata%\Microsoft\MessageAnalyzer\OPNAndConfiguration\EtwManifests\`  
  
> [!NOTE]
>  In a future release, Message Analyzer may have the capability to import provider manifests directly through an OPN adapter, depending on demand.  
  
## See Also  
 [Understanding Event Parsing with a Provider Manifest](understanding-event-parsing-with-a-provider-manifest.md)