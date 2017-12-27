---
title: "Understanding Event Parsing with a Provider Manifest | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 470b0640-4a15-409d-aa62-8202465b7f4b
caps.latest.revision: 29
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Understanding Event Parsing with a Provider Manifest

Message Analyzer traces are based on ETW Providers, which operate in an infrastructure that enables you to capture ETW events on your system. For Message Analyzer to be able to parse ETW messages from a particular provider, it must have a manifest for that provider. The manifest is a configuration file that defines the schema or format of the data that is delivered by the provider. When starting a Live Trace Session that is configured to use a specific system ETW provider, Message Analyzer typically obtains the required system manifest from the .exe or .dll of the registered provider component and builds an OPN description (parser) to represent its messages. This OPN description is then compiled and temporarily loaded into the Runtime so it can parse the ETW messages. If a trace file is saved and then transferred to another system, that system may not have the same provider components, component versions, or an appropriate provider manifest that is needed to enable parsing of the ETW messages.  
  
 This issue can be resolved in either of the following ways:  
  
-   The manifest information must be saved with the trace.  
  
-   The manifest file must be manually generated and stored on the new system.  
  
> [!NOTE]
>  On computers that are running the Windows 10 operating system, Message Analyzer can now use dynamic messages generated from raw ETW events to enable the Runtime to parse ETL files with no manifest. This feature accommodates the new ETL file format on Windows 10, where the message format definitions are self-contained. In this scenario, an OPN description is not required.  
  
 However, on computers that are running an operating system that is earlier than Windows 10, you might have an event trace log (ETL) that utilized an ETW provider that is not registered in the particular system on which you are running Message Analyzer. As a result, Message Analyzer will not have access to the provider manifest and will therefore be unable to fully parse messages from that log.  In this case, Message Analyzer will provide a simple level of parsing that produces messages in a general format. However, if the manifest was previously included with the log that contains the data you are loading, Message Analyzer will be able to fully parse the messages in the ETL file.  
  
 You might also save trace data on a source computer that will be further processed on other destination systems where the provider versions are unknown. If this is the case, Message Analyzer accommodates this situation by automatically saving trace data with the manifests of the underlying provider/s that were used in the trace. This ensures that Message Analyzer will be able to parse the ETW message data on the destination computer. Likewise, if you are loading data from an ETL file into Message Analyzer and you suspect that an unknown provider configuration was used to capture/log the data, you might need to generate a manifest for the log to ensure that Message Analyzer can parse its messages.  
  
## Obtaining a Provider Manifest  

 If you need to obtain a provider manifest for parsing ETW messages, see [Generating a Provider Manifest](generating-a-provider-manifest.md).  
  
---  
  
## See Also  
- [Integrating Event Tracing](message-analyzer-tutorial.md#BKMK_EventTraces)   
- [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md)