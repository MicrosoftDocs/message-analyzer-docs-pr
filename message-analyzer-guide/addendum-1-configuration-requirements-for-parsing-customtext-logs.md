---
title: "Addendum 1: Configuration Requirements for Parsing CustomText Logs | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: ec1e4efd-4eaf-41ad-9fff-f4c17c602153
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Addendum 1: Configuration Requirements for Parsing CustomText Logs
Message Analyzer automatically determines the Open Protocol Notation (OPN) configuration that is needed to parse supported input file types, which are described in [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md). However, in the case of textual log file types that contain proprietary message formats, it is often the case that you will need to generate an OPN configuration file that defines how your text log is to be parsed, so that you can properly display your text log data in a Message Analyzer viewer. This addendum provides a high-level overview about creating an OPN configuration file for a text log, the directory location where you must place it so that Message Analyzer can load it at startup, and how to set a configuration file to be the default for parsing all your text logs. For the low-level details required to create a configuration file, a guide is available for download, as described in the section that follows.  
  
## Creating an OPN Configuration File  
 An OPN configuration file consists of message definitions that describe how text log data entries are to be parsed for display in Message Analyzer. You can create the message definitions for a text log by using OPN and Regular Expression (Regex) notation to identify each unique type of log entry and map it to a message structure, as indicated in [Parsing Input Text Log Files](message-analyzer-tutorial.md#BKMK_ParsingLogFiles). The message definitions contained in a configuration file are also subject to OPN compilation to ensure the integrity of the OPN description that Message Analyzer will use to parse the text log. If an OPN configuration file does not properly compile, you will receive a compilation error during Message Analyzer startup when OPN definitions are loaded into the system.  
  
 You can review the details and requirements for creating an OPN configuration file by downloading the [OPN Configuration Guide for Text Log Adapter](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) document.  
  
## Saving the Configuration File  
 After you create a configuration file for a text log and save it with a .config extension, you must place it in the following directory location so that Message Analyzer can locate and load it during startup:   
`%LocalAppData%\Microsoft\MessageAnalyzer\OpnAndConfiguration\TextLogConfiguration\DevicesAndLogs\`  
Thereafter, whenever you use the **Add Files** feature in a Data Retrieval Session to load data from a target text log into Message Analyzer, the drop-down list in the **Text Log Configuration** column on the **Files** tab of the **New Session** dialog will contain your new configuration file as a list item. This enables you to select this configuration file whenever it is required to parse the unique text log messages for which it is designed.  
  
## Specifying a Default Configuration File for All Text Logs  
 You have the option to specify a particular OPN configuration file that will be used by default for all text log data files from which you load data into Message Analyzer. You can do this from the global **Options** dialog that is accessible from the Message Analyzer **Files** tab. On the **General** tab of the **Options** dialog, click the **Default text log configuration** drop-down list and select one of the predefined text log configuration files as your default, or you can select a custom configuration file that you created as your default. However, you will need to have placed your custom configuration file in the previously specified location in `%LocalAppData%` before it will appear in the drop-down list.  
  
 Your selection in the **Text Log Files** pane of the **Options** dialog for the default text log configuration file updates the `<DefaultLogFileReaderModule>` section of the app.ApplicationConfiguration.cfg file in the following directory location:   
`%LocalAppData%\Microsoft\MessageAnalyzer\`  
 Thereafter, whenever you use the **Add Files** feature on the **Files** tab of the **New Session** dialog to target a text log from which to load data in a Data Retrieval Session, the default OPN configuration file that you selected in the **Options** dialog is automatically selected in the drop-down list of the **Text Log Configuration** column, at the time when the actual text log data file appears in the files list. Moreover, if you launch a text log data file from **Windows Explorer**, **Quick Open**, or you use the drag-and-drop method when a default OPN configuration file has been specified, Message Analyzer will automatically begin loading data, at which point your text log messages begin to accumulate in the default **Analysis Grid** viewer.  
  
> [!NOTE]
>  If you want to override the default configuration file specification, you can simply select the **(None)** item from the drop-down list in the **Text Log Files** pane of the **Options** dialog.