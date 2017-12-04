---
title: "Saving Files in Native Format | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a5def11-dea6-4fba-baa9-a07ad8832de2
caps.latest.revision: 30
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Saving Files in Native Format
In Message Analyzer, you can save your data in the Message Analyzer Trace Parsed (.matp) format only, or you can export your data in the Network Monitor Capture (.cap) file format. The .matp file format is native to Message Analyzer, meaning that only Message Analyzer can open these files. However, .cap files can be opened by Microsoft Message Analyzer, Microsoft Network Monitor, and other protocol analyzers. When you save a trace file with Message Analyzer, the Windows **Save As** dialog opens to the default location, which is the following:  
`C:\Users\<username>\Documents\MessageAnalyzer\Traces`  
However, note that you can change the location for saving traces and logs to any location you choose.  
  
## Saving Settings  
 When you save trace files, certain types of settings are saved with them. For example, in the case of .matp files, the session **Name**, **Bookmarks**, **Comments**, and **Time Shift** settings are preserved in subsequent openings of this file type. However, when you export data as a Network Monitor Capture (.cap) file, **Bookmarks**, **Comments**, and **Time Shift** settings are not persisted in subsequent openings of this file type. Also, the session **Name** is persisted only when .cap files are opened with the **Recent** or **Open** features, which are accessible from the Message Analyzer **File** menu.  
  
> [!IMPORTANT]
>  When you save a Message Analyzer trace file in the .cap format, be aware that there may be some interoperability issues with certain applications when attempting to open a .cap file in such an application. For more information about the media types that Message Analyzer supports when saving to the .cap file format, see [Compatibility with Exported CAP Files](../messageanalyzer_content/compatibility-with-exported-cap-files.md).  
  
## Reloading Data from Supported File Formats  
 When you save data in the parsed format (.matp) format, the files can be large in size and may consume considerable disk space. However, they are very fast to reload into Message Analyzer because the data does not have to be reparsed. Although you cannot save Message Analyzer trace data as an unparsed file, you can still load data from such files in the .matu format as described in [Locating Supported Input Data File Types](../messageanalyzer_content/locating-supported-input-data-file-types.md). The only tradeoff is the parsing time that you incur when data from these files is being loaded into Message Analyzer.  
  
> [!NOTE]
>  If you load data from a log such as an .etl file or any other supported file type in non-native format and you need to save the results following data manipulation and analysis, you can save the data in the .matp or .cap file format only.