---
title: "Opening Text Log Files | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: acda5280-aa54-4a58-98be-69cbfbee82de
caps.latest.revision: 18
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Opening Text Log Files
Message Analyzer enables you to parse data from text-based log files, for example, files with a \*.log extension. You can open these types of log files from the **New Session** dialog in a Data Retrieval Session, or by using **Windows Explorer**, the **Open** feature, or the drag-and-drop method.  
  
> [!NOTE]
>  The drag-and-drop method is unavailable when running Message Analyzer in the Administrator mode due to varying security contexts.  
  
## Using a Configuration File to Parse Text Logs  
 To parse text-based log files, Message Analyzer requires a configuration file. By default, Message Analyzer provides several predefined configuration files that you can select from a drop-down list in the **Text Log Configuration** column just below the toolbar on the **Files** tab of the **New Session** dialog during Data Retrieval Session configuration. You can view the **Text Log Configuration** drop-down list in the figure of the topic [Parsing Input Text Log Files](../messageanalyzer_content/message-analyzer-tutorial.md#BKMK_ParsingLogFiles).  
  
 If there is no predefined configuration file that meets your requirements, you are advised to create an OPN configuration file so that Message Analyzer can fully parse your text log. Thereafter, you will need to either set the new configuration file as the default for all your log files, by selecting it from the drop-down list in the **Text Log Files** section on the **General** tab of the global **Options** dialog — which is accessible from the Message Analyzer **Tools** menu — or you must select a unique configuration file in the **Text Log Configuration** drop-down for each specific log file that contains a varying message format. For more information about configuration tasks that are required for opening and parsing text logs, see the [Addendum 1: Configuration Requirements for Parsing Custom Text Logs](../messageanalyzer_content/addendum-1-configuration-requirements-for-parsing-customtext-logs.md) topic.  
  
 After you create a configuration file for your text log and place it in the appropriate directory location, as indicated in the [Addendum 1: Configuration Requirements for Parsing Custom Text Logs](../messageanalyzer_content/addendum-1-configuration-requirements-for-parsing-customtext-logs.md) topic, you can then target the text log that contains the messages to load into Message Analyzer through the **Add Files** feature, which is located in the toolbar on the **Files** tab of the **New Session** dialog. After you select a log file with the **Add Files** feature and it displays in the files list, the **Text Log Configuration** drop-down menu is populated with the names of all the predefined configuration files that ship with Message Analyzer, in addition to any that you have created. At this point, you can simply select the appropriate configuration file and start the parsing process by clicking the **Start** button in the **New Session** dialog, at which time messages begin loading into the specified data viewer, for example the **Analysis Grid**.  
  
> [!CAUTION]
>  One of the selections available in the drop-down list under the **Text Log Configuration** column for each text log is the **[None]** option. If you select this option and start to load data, Message Analyzer does not fully parse the messages in the log, but instead simply returns the lines of message data in the file. In this case, it is likely you will see data only in the **MessageNumber**, **Module**, and **Summary** columns of the **Analysis Grid** viewer, where the log data displayed in the **Summary** column contains message fields that are delimited by semicolons. Also, if you select an invalid configuration file for your log, Message Analyzer will display a diagnostic **Parsing Error** icon in the **DiagnosisTypes** column of the **Analysis Grid** viewer for each log message.  
  
> [!TIP]
>  If you do not create a configuration file for your text log and you simply select the **[None]** option in the **Text Log Configuration** column drop-down list, you can still use Message Analyzer filtering features to locate specific data from your log file after the data displays in the **Analysis Grid** viewer. For example, you might specify a view **Filter** such as `contains “error”` or `*Summary contains “error”` to filter for lines of data that contain “error” characters, or you could also specify **Color Rule** filters or a **Pattern Expression** to highlight or extract other data of interest.  
  
## Using Alternate Input Methods for Text Log Files  
 You have the option to load data from a .log file by using **Windows Explorer**, the **Open** feature, or the drag-and-drop method. Providing that you have not set a default configuration file, Message Analyzer automatically opens to the **New Session** dialog to enable you to select a configuration file from the **Text Log Configuration** drop-down menu on the **Files** tab. However, if you have already set a default configuration file that your text logs will use (from the **General** tab of the global **Options** dialog that is accessible from the global Message Analyzer **Tools** menu), as described in the [Addendum 1: Configuration Requirements for Parsing Custom Text Logs](../messageanalyzer_content/addendum-1-configuration-requirements-for-parsing-customtext-logs.md), then Message Analyzer automatically parses and displays the data in the default data viewer without displaying any Data Retrieval Session configuration options.  
  
 To open multiple log files simultaneously from outside a Data Retrieval Session, you can double-click supported files in **Windows Explorer**, use the drag-and-drop method, or use the **Open** feature. Note that if you use **Windows Explorer**, you might need to select the right-click **Open With** context menu command to associate Message Analyzer as the application that opens your log files.  
  
> [!NOTE]
>  You can also use **Windows Explorer**, the **Open** feature, or the drag-and-drop method as alternate methods of loading data from other supported file types, as described in [Locating Supported Input Data File Types](../messageanalyzer_content/locating-supported-input-data-file-types.md).