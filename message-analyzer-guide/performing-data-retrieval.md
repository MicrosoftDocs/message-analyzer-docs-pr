---
title: "Performing Data Retrieval | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41922ecc-505e-42be-862a-81f789a0f8d4
caps.latest.revision: 56
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Performing Data Retrieval
This section describes the methods that you can use to retrieve input data to  load into Message Analyzer. This includes the quickest methods for doing so, such as the **Open** feature.  
  
## Retrieving Data Quickly  
 There are several methods that you can use to get data into Message Analyzer quickly. You can use these methods to find, load, and immediately display the contents of traces, logs, and other data file types that are described in [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md). These methods consist of the following:  
  
-   **Open** feature — the fastest way to retrieve saved data with Message Analyzer is to use the **Open** feature that is located on the global Message Analyzer toolbar as a folder icon that contains a drop-down list, or you can use the **Open** command that is accessible from the Message Analyzer **File** menu. From either of these locations, you can select the **From File Explorer** command from the **Open** drop-down list to display the **Open** dialog, from where you can navigate to and select the files that contain the data of interest.  
  
    > [!NOTE]
    >  If you use the **Open** feature, you can load data from multiple files simultaneously.  
  
    > [!TIP]
    >  You can also select the **From Other File Sources** command from the **Open** drop-down list, to display the **File Selector** dialog, from where you can target Azure logs as input to Message Analyzer.  
  
-   **Drag-and-drop** method — you can retrieve saved data quickly by dragging-and-dropping one or more saved trace or log files onto various Message Analyzer locations, for example, the **Files** tab of a Data Retrieval Session, the **Session Explorer** **Tool Window**, or the **Start Page**.  
  
    > [!IMPORTANT]
    >  If you elect to run Message Analyzer in Administrator mode, it can result in varying security contexts between applications. This means that you will be unable to use the drag-and-drop feature to open saved trace and log files in this mode.  
  
-   **Windows Explorer** method — you can use **Windows Explorer** application to navigate to and select the saved files from which you want to retrieve data.  
  
-   **Recent Files** feature — the global Message Analyzer **File** menu contains a **Recent Files** list that enables you to quickly display data and resume your work from earlier sessions that you saved. You can quickly open one of the files in the list by clicking it and Message Analyzer will then display its data in the current default viewer.  
  
-   **Ctrl+O** keyboard shortcut — you can use the keyboard shortcut `Ctrl+O` to display the **Open** dialog.  
  
 When you use these features to load data into Message Analyzer, the data loading process is immediately invoked in the background and the results quickly begin to display in the default data viewer, for example, the **Analysis Grid**. For this to occur, Message Analyzer automatically creates a new Data Retrieval Session that is implicitly named based on a default session name, which you can edit to customize as you wish. However, when using the previously described input methods, you can only edit the session name if you click the **Edit Session** icon on the global Message Analyzer toolbar *after* the data has loaded into Message Analyzer. The only exception to the automatic startup of a Data Retrieval Session using the previously described input methods is if you have selected a .log file for input to Message Analyzer. In this case, you will need to provide some additional configuration, as described in the next section.  
  
## Specifying a Text Log Configuration File  
 If you are loading data from a .log file, Message Analyzer opens the **New Session** dialog so that you can specify a built-in **Text Log Configuration** file to parse the log. However, if you have previously specified a particular configuration file as the default on the **General** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu), this does not occur. Rather, Message Analyzer immediately proceeds to load your log data without opening the **New Session** dialog. In addition, if you cannot find a built-in configuration file that will successfully parse your log file, you may need to create one, as described in [Opening Text Log Files](opening-text-log-files.md).  
  
## Loading Data with a Specified Session Configuration  
 You can also navigate to trace files or logs that contain the data you want to work with in a Data Retrieval Session, by clicking the **Add Files** button on the **Files** tab of the **New Session** dialog to display the **Open** dialog. After you select files and click **Open** to exit this dialog, the files display in the files list on the **Files** tab of the **New Session** dialog. At this point, no data is loaded into Message Analyzer, as the files list is only a set of pointers to the files that contain the data you are targeting.  
  
 To continue with Data Retrieval Session configuration prior to loading data, you have the option to select specific files in the files list to create a unique collection of messages that you want to analyze, as described in [Selecting Input Files for Data Retrieval](performing-data-retrieval.md#BKMK_SpecifyTargetInputFiles). Prior to starting your Data Retrieval Session, you also have the option to select a different data viewer from the **Start With** drop-down list in the **New Session** dialog; otherwise, your data will be displayed in the data viewer that is set as the default in the **Session Viewer** section on the **General** tab of the global **Options** dialog that is accessible from the global Message Analyzer **Tools** menu. In addition, if you want to filter the data you are loading to retrieve specific information to focus on, you can do so by specifying a **Session Filter** or a **Time Filter**, as described in [Selecting Data to Retrieve](selecting-data-to-retrieve.md).  
  
<a name="BKMK_SpecifyTargetInputFiles"></a>   
## Selecting Input Files for Data Retrieval  
 When configuring a Data Retrieval Session, you can specify the files containing the target data that will display in a Message Analyzer viewer, by placing a check mark in the check box next to the file names in the files list on the **Files** tab of the **New Session** dialog. Message Analyzer keeps track of the **Message Count** for each file that you add, the number of files available for data retrieval, the number of files you actually selected, and the total number of aggregated messages from all the files selected in the list. Other file attributes are also displayed for each file, such as the **Name**, **Size**, **File Type**, **Start Time**, and **End Time**. The current exceptions to this are .etl and .pcap files, for which message count and time ranges may not be displayed in the Data Retrieval Session configuration.  
  
> [!CAUTION]
>  Loading data from very large input files can impact the performance of the data loading process, especially on 32-bit computers.  
  
> [!NOTE]
>  If Message Analyzer detects that an input file from which you are loading data was processed with an out-of-date parser, you will be prompted to reparse that data with an updated parser. If you choose not to reparse, Message Analyzer will not open the file. If you do reparse, note that any **Bookmarks** and **Comments** in the file will be preserved, but in some cases they might be relocated to the lowest stack message due to OPN revisions that might have impacted the origins tree (messages underlying top-level).  
  
## Starting a Configured Data Retrieval Session  
 When you are ready to load the data into Message Analyzer from a *configured* Data Retrieval Session and to display it in the default data viewer, click the **Start** button in the **New Session** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about using the **File Selector** and loading data from Azure logs, see [Retrieving Azure Storage Blob Data](retrieving-azure-storage-blob-data.md).  
---