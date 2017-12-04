---
title: "Filtering Loaded Input Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d010b302-20b6-4ee7-9c35-5f1cf7c56c0b
caps.latest.revision: 29
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Filtering Loaded Input Data
Prior to loading data into Message Analyzer through a Data Retrieval Session, there are several methods you can use to limit the data that you load for analysis. These methods, which enable you to create a focused message set based on criteria that you define, consist of the following:  
  
-   **Configure a Session Filter** — enables you to “select” specific data from your input file configuration through filtering, to narrow the scope of data retrieval to specific data of interest, reduce the volume of messages that you load, and therefore improve performance.  
  
-   **Choose input files** — enables you to select data by combining chosen input  files that contain specific data that you want to load into Message Analyzer.  
  
-   **Apply a Time Filter** — enables you to select data  by reducing the scope of loaded messages to a specified time range, by configuring a window of time in which to view data prior to loading such data from saved files.  
  
-   **Choose a Parsing Level** — enables you to select data by limiting how far up the message stack Message Analyzer will parse, thereby reducing the number of messages processed and displayed, creating a focused analysis level, and increasing performance.  
  
## Selecting Data with a Session Filter  
 You can specify a **Session Filter** for your Data Retrieval Session by either writing your own Filter Expression or choosing a built-in Filter Expression from the centralized filter  **Library**. This **Library** is accessible in the **New Session** dialog on the toolbar just above the **Session Filter** text box.  This **Library** contains the same built-in Filter Expressions that you will find in the **Message Analyzer Filters** asset collection **Library** on the Filtering toolbar that appears just above the main analysis surface in the Message Analyzer user interface (UI).  
  
 If you want to specify a built-in Filter Expression from the centralized filter **Library** when loading data into Message Analyzer, you should first review the filter functions that are described in [Filtering Live Trace Session Results](filtering-live-trace-session-results.md) and then select an appropriate **Session Filter**. If you intend to create your own Filter Expression, see the appropriate topic below in the **See Also** section for more information about how to write one.  
  
> [!TIP]
>  After you write a Filter Expression or modify a built-in expression that you want to use as a **Session Filter**, you have the option to save the new Filter Expression to the centralized filter **Library** from the **New Session** dialog. For example, if you want to save the Filter Expression code that you specified in the **Session Filter** text box, click the **Library** drop-down list and then select the **New Filter** command to display the **Edit Filter** dialog. The text of the target Filter Expression is transferred to the **Edit Filter** dialog, where you can specify **Name**, **Description**, and **Category** information before you save it to the **Library** (by clicking the **Save** button in the dialog).  
  
 Saving a custom Filter Expression to the filter **Library** is optional. Because you are not restricted from applying such a filter to the data loading process, you can observe its performance prior to saving it. To do this, simply click the **Start** button in the **New Session** dialog.  
  
> [!NOTE]
>  Message Analyzer no longer automatically validates that Filter Expressions properly compile, in order to remove the restrictions on Filter Expressions that use elements which are outside the range of the modules that Message Analyzer parses.  
  
 If your Filter Expression performs as expected and proves to be a useful tool for analysis, you can save it to your centralized filter **Library** for future use, as previously described. Note that such a Filter Expression is added to the **My Items** category of your Filter Expression **Library** and is then available to the Sharing Infrastructure, which enables you to share filters with other users.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using a **Session Filter**, see [Applying a Session Filter to a Data Retrieval Session](applying-a-session-filter-to-a-data-retrieval-session.md).  
___________________\_  
  
## Selecting Data by Choosing Files  
 After using the **Add Files** command on the toolbar of the **Files** tab in the **New Session** dialog to create a list of files that contain the data you want to load through your Data Retrieval Session, feasibly from multiple disparate data sources, you can also apply filtering through *file selection* to create unique message collections. To do this, simply select specific files from among the files that are marked for loading data in the files list to create a subset of messages that you want to focus on. For each file that you want to include for data loading, place a check mark in the check box next to the file name in the files list of the **New Session** dialog. You can also specify a data viewer in which to present the loaded data  by selecting one from the **Start With** drop-down list. After you click the **Start** button in the **New Session** dialog, the data loading process is silently invoked in the background.  
  
## Selecting Data Through Time Filtering  
 You might have multiple log files containing data that was collected over a period of time from different sources, for example, from a client and server. For example, you might be interested in isolating the source of a TCP connection issue that involved lost TCP segments but it is unclear which machine was dropping packets. You could load data from sets of log files from the same time period, possibly while drilling down to a specific window of time with the use of an input **Time Filter**, to select data that was collected on both client and server computers in a specified time window. When viewing results in an Analysis Session, the data from each set is presented as a single unified message collection with messages interleaved in chronological order. Note that you might also want to configure a **Time Shift** if the data sets need to be synchronized.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about creating a **Time Filter** window, see [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).  
**To learn more** about creating a **Time Shift**, see [Setting Time Shifts](setting-time-shifts.md).  
___________________\_  
  
## Selecting Data by Choosing a Parsing Level  
 Message Analyzer provides a  built-in Library known as the **Message Analyzer Parsing Levels** asset collection, as indicated in the **Asset Manager** dialog which is accessible from the global Message Analyzer **Tools** menu. This built-in Library is accessible from the **Parsing Level** drop-down list in the **New Session** dialog. In the list, the **Full** value is the default, which means Message Analyzer will parse the full stack for all messages. However, as an example, if you select the **Network Analysis** item in the list, Message Analyzer will parse up to and including the IP/Network Layer, with a few exceptions for certain TCP, UDP, and other traffic that is predetermined to be valuable for network analysis. Other **Parsing Levels** also use  exceptions that are valuable to analysis at the chosen **Parsing Level**.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about **Parsing Levels**, see [Setting the Session Parsing Level](setting-the-session-parsing-level.md).  
___________________\_  
  
## Changing the Applied Filtering by Editing a Session  
 You also have the option to edit your Data Retrieval Session after the data loads into Message Analyzer. You can do this by clicking the **Edit Session** button on the global Message Analyzer toolbar. Thereafter, the **Edit Session** dialog displays, from where you can choose another **Session Filter** or configure a different one, that is, if you exit the **Restricted Edit** mode. This includes reconfiguring any specified input **Time Filter** and/or choosing a different **Parsing Level** as part of your edits. You can then apply the changes you make to the session configuration by clicking the **Apply** button in the **Edit Session** dialog and Message Analyzer will process the changes you specified for your  Data Retrieval Session. Note that you can  add or remove files in the files list on the **Files** tab without exiting the **Restricted Edit** mode, however, for any other type of edit, you must click the **Full Edit** button to enable all editable features.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about editing a Data Retrieval Session, see [Editing Existing Sessions](editing-existing-sessions.md).  
___________________\_  
  
## See Also  
 [Selecting Data to Retrieve](selecting-data-to-retrieve.md)   
 [Selecting Data to Capture](selecting-data-to-capture.md)   
 [Writing Filter Expressions](writing-filter-expressions.md)