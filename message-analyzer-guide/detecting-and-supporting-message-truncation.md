---
title: "Detecting and Supporting Message Truncation | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dffef49c-50ad-46d6-a752-4cf511d9496f
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Detecting and Supporting Message Truncation

Truncation Support  Message Analyzer provides support for input files in the .cap, .pcap, .pcapng, and .etl format that contain truncated messages. Message Analyzer can automatically detect whether messages in these input file types are truncated, at which time, it switches to a limited OPN parser set that contains parsers for the Ethernet, GRE, IPv4, IPv6, ESP, AH, IKE, AIPS, TCP, UDP, and HTTP protocols. Note that these particular parsers are specifically instrumented in Message Analyzer to support message truncation so that you can avoid unnecessary diagnosis messages in your loaded message results. When message truncation is detected, Message Analyzer also sets an **IsSessionTruncated** annotation that determines how individual messages will be parsed.  
  
 In addition, whenever Message Analyzer detects truncated messages, it automatically selects the **Truncated Parsing** check box on the toolbar of the **Files** tab in the **New Session** dialog, from where you locate and select files containing the data to load into Message Analyzer. Note that Message Analyzer will automatically select this check box whenever you have at least one input file that contains truncated messages. However, you have the option to manually unselect this check box. Moreover, if Message Analyzer does not detect message truncation in a particular input file and you know that it contains truncated messages, you can manually select the **Truncated Parsing** check box to force Message Analyzer to initiate the truncated parsing mode.  
  
> [!NOTE]
>  When resaving your data from such a Data Retrieval Session, you can persist the truncation information when saving the data in the native Message Analyzer .matp file format only.  
  
 After you load files with truncated messages into the **Analysis Grid** viewer from a Data Retrieval Session, you can display the length to which messages in these files are truncated by adding a **TruncationLength** column to the **Analysis Grid** viewer from the **Field Chooser** **Tool Window** under the **Global Annotations** node. Thereafter, the **TruncationLength** column will be populated with truncation length values for the truncated messages.