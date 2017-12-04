---
title: "Compatibility with Exported CAP Files | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43a7fd36-f3ad-45df-8685-3b31af9f0913
caps.latest.revision: 15
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Compatibility with Exported CAP Files
As previously stated, Message Analyzer enables you to export trace data in the  .cap file format, which is the native file format for  Microsoft Network Monitor. If you export Message Analyzer data to the .cap file format, it enables Network Monitor and other protocol analysis tools that support this format to open such a file. However, Message Analyzer only supports certain media types when exporting data to the .cap file format. Therefore, if you are saving trace data that contains frames that are unsupported, that data will not be exported. In addition, if no frames of the supported type are found in the trace data being exported, Message Analyzer will not export any messages and displays the following **Trace Save Error** message:  
**None of the messages could be written to file, therefore the file was not created**  
  
 The media types that are supported by Message Analyzer when exporting trace data in .cap file format are described in the table that follows:  
  
### Table 26.   Supported Media Types for .Cap File Exports  
  
|Media Type|Value|  
|----------------|-----------|  
|Cap frame|0|  
|Ethernet frame|1|  
|ETW provider message (NetEvent)|0xFFE0|  
  
## See Also  
 [Saving Files in Native Format](saving-files-in-native-format.md)