---
title: "Working With Special Input Requirements | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef97f4f8-1027-4295-a34d-ff01199a9b97
caps.latest.revision: 34
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Working With Special Input Requirements
This section describes how you can handle input data that has a unique format, in addition to cases where the data you are loading was captured with a provider for which your system has no provider manifest.  
  
## Handling Unique Log File Formats  
 A common log file type that Message Analyzer supports uses the .log extension, which can have a proprietary format. Prior to loading data into a Message Analyzer Data Retrieval Session from such a text-based log file, you will typically need to select a predefined parser from the **Text Log Configuration** drop-down list above the files list in your Data Retrieval Session. If you do not select one of these predefined OPN configuration files, or if an appropriate configuration file is unavailable, it is likely that Message Analyzer will not recognize the format of your log and will therefore be unable to parse it fully. If this occurs, Message Analyzer will display all of the message fields from your log in the **Summary** column of the **Analysis Grid** viewer with each field delimited by a semicolon.  
  
 If you want Message Analyzer to successfully parse and display all the message fields of your log in separate **Analysis Grid** columns, you will need to create a custom OPN configuration file to parse the log. Moreover, if Message Analyzer does not have an OPN description for any particular message that is contained in a particular log file from which you are trying to load data, you will be unable to display any data for *that message*. This is because, in absence of an OPN description, the protocol object model (POM) (see [PEF Architecture Tutorial](../messageanalyzer_content/pef-architecture-tutorial.md)) will not contain a *compiled* OPN description that the PEF Runtime can use to parse the messages. When you create an OPN configuration file, you will define the log messages with OPN declarations and Regex notation, as described in the [OPN Configuration File for Text Log Adapter v2](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) document. When complete, you must drop the new configuration file into the following directory location:   
`%LocalAppData%\Microsoft\MessageAnalyzer\OpnAndConfiguration\TextLogConfiguration\DevicesAndLogs\`  
Thereafter, whenever you add a log file of this particular type to the files list in a Data Retrieval Session, an OPN description will be automatically generated from the content of the existing OPN configuration file after you select the file from the **Text Log Configuration** drop-down list in session configuration and you **Start** the session.  
  
## Missing Provider Manifests  
 Message Analyzer also accommodates for loading messages that were captured with a provider for which your system has no provider manifest, if the proper manifest is included with the loaded trace file. In addition, if you have a destination computer with a manifest that is out-of-date with respect to the source computer manifest that was included in an .etl file, a workaround that you can employ to create the manifest that you require is described in [Generating a Provider Manifest](../messageanalyzer_content/generating-a-provider-manifest.md). Otherwise, Message Analyzer will be unable to parse messages from such message providers.  
  
> [!NOTE]
>  Message Analyzer saves the OPN parser configuration with all files that you save in .matp format, to make the data portable from one Message Analyzer installation to another should any differences exist in the parser packages.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about working with text-based log files, see [Opening Text Log Files](../messageanalyzer_content/opening-text-log-files.md).  
**To learn more** about creating an OPN configuration file for text-based logs, download the [OPN Configuration File for Text Log Adapter v2](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) document.  
___________________\_