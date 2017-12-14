---
title: "Applying an Input Time Filter to a Data Retrieval Session | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ac8a4e9-bc8f-4db1-aba2-9d80b9f7f316
caps.latest.revision: 51
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Applying an Input Time Filter to a Data Retrieval Session
Prior to loading data into Message Analyzer from a specified message collection that you configure in a Data Retrieval Session, you can also configure a window of time in which to view data by using a **Time Filter**. This is particularly useful if you have one or more very large data files that contain trace or log data that was collected over a significant period of time and you want to narrow the scope of the data to be viewed. The UI configuration of the **Time Filter** feature is shown in the figure of the topic [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md).  
  
 Most logs and file types are supported by the **Time Filter** feature; however, you may need to select the **Use Start Filter** and **Use End Filter** check boxes and specify start and end times in the corresponding text boxes for certain types of logs and traces in which the data format prevented Message Analyzer from retrieving this information. See [Manually Specifying Time Formats](applying-an-input-time-filter-to-a-data-retrieval-session.md#BKMK_ManuallySetTimeFormats) for more information.  
  
 For example, the following table lists the different trace or log file types for which Message Analyzer can determine the start times and end times, along with those that it cannot.  
  
### Table 10.   Estimated Start and End Times vs Trace  File Types  
  
|Trace Type|Estimated Start Time|Estimated End Time|Total Messages/Filtered Messages|  
|----------------|--------------------------|------------------------|---------------------------------------|  
|.aztable*|N/A|N/A|N/A|  
|.blg|No|No|No|  
|.cap**|**Yes**|**Yes**|**Yes**|  
|.csv|No|No|No|  
|.dmp|No|No|No|  
|.etl|**Yes**|No|No|  
|.evtx|No|No|No|  
|.json|No|No|No|  
|.log|**Yes**|**Yes**|**Yes**|  
|.matp|**Yes**|**Yes**|**Yes**|  
|.matu|**Yes**|**Yes**|**Yes**|  
|.oms*|NA|NA|NA|  
|.pcap|No|No|No|  
|.pcapng|No|No|No|  
|.pmlcsv|No|No|No|  
|.pmlxml|No|No|No|  
|.ps1|No|No|No|  
|.saz|No|No|**Yes**|  
|.sqltable*|N/A|N/A|N/A|  
|.trc|No|No|No|  
|.tsv|No|No|No|  
|.xml|No|No|No|  
  
> [!CAUTION]
>  *Message Analyzer supports these input file types with separate user interface (UI) features, as described in [Retrieving Azure Storage Table Data](retrieving-azure-storage-table-data.md), [Loading SQL Data](loading-sql-data.md), and [Loading OMS Log Data](loading-oms-log-data.md). However, the UI for these features does not provide start and end time information, as described in the previous table.  
  
> [!NOTE]
>  \*\*When loading data from a .cap file that was not previously saved by Message Analyzer, the start and end time values for the message data is unknown. In cases where Message Analyzer has *some* information, any displayed values for these files are only estimates. For text logs in .log file format, the start and end time values of messages will be known only after the parsing process, or if you specified the time stamp format in an OPN configuration file for the text log.  
  
 You should also be aware that estimated start and end times for some supported file types, as indicated in the **Start Time** and **End Time** text boxes in the **Time Filter** pane of your Data Retrieval Session configuration, may not match the **Start Time** and **End Time** text box values in the **Time Filter** panel on the Filtering toolbar in an Analysis Session. This is because the start and end times indicated in a Data Retrieval Session for certain file types is only an estimate, while the **Start Time** and **End Time** indicated in the **Time Filter** panel on the Filtering toolbar are known values that are determined in the parsing process. Moreover, this is the case because the start and end time estimations in the **Time Filter** pane are calculated *before* the data is retrieved, whereas the start and end time indications that appear on the Filtering toolbar are calculated *after* the data is retrieved.  
  
## Input File Details  
 After you add a supported input data file to your Data Retrieval Session and select it in the files list on the **Files** tab of the **New Session** dialog, Message Analyzer estimates the start and end times of the events in the trace or log files and displays these values, respectively, on each side of the adjustable time-window slider controls in the **Time Filter** pane of the Data Retrieval Session configuration. The start and end times are also displayed in  the **Start Time** and **End Time** text boxes just above the **Time Filter** pane. In addition, an estimate of the total number of messages in the trace or log time frame is displayed in the **Total Messages** text box and the number of selected files in the files list is indicated in the **Selected Files** text box. Other file attribute information is also included, such as the file **Name**, **Size**, **File Type**, and **Message Count**; which all display in the columns just below the toolbar on the **Files** tab of the **New Session** dialog.  
  
> [!NOTE]
>  If you are loading multiple data sources in a Data Retrieval Session and any of those sources are among the ones listed in the previous table with a “No” in the estimated start time or estimated end time columns, the corresponding start or end times for the entire input file configuration will not display in the **Time Filter** section of the Data Retrieval Session configuration of the **New Session** dialog.  
  
## Configuring a Time Filter  
 To configure a **Time Filter**, you can adjust the time-window slider controls to zoom into a particular time slot in which you want to view data. Before you adjust the time slider controls, you should enable  **Filtered Messages** tracking  by selecting the **Use Start Filter** and **Use End Filter** check boxes. Thereafter, as you adjust the slider controls, a text box below the **Use Start Filter** check box displays the start time and a text box below the **Use End Filter** check box displays the end time in the **Time Filter** pane of the **New Session** dialog. The corresponding new start and end time values define the selected time window in which you are choosing to view data, while the parenthetical **Filtered Messages** label displays the estimated number of messages that are contained in the time slot that you specify. However, the overall start and end times of the trace or log persist in the **Start Time** and **End Time** text boxes above the **Time Filter** pane.  
  
> [!NOTE]
>  Selecting data with a **Time Filter** produces a subset of the total messages contained in the selected input file/s. Once you apply a **Time Filter** that reduces message count in your Data Retrieval Session results, you will need to remove the **Time Filter** and rerun the Data Retrieval Session if you want to display the original message set in its entirety.  
>   
>  To do this or to specify a different window of time, open the **Edit Session** dialog either by clicking the **Edit Session** icon on the global Message Analyzer toolbar or by selecting the **Edit Session** item from the Message Analyzer **Session** menu. After you open the **Edit Session** dialog, you will need to click the **Full Edit** button to enable the **Time Filter** controls. From the **Edit Session** dialog, you can then remove the previous **Time Filter** configuration altogether by moving the time slider controls all the way to the left and right side default positions, or you can reconfigure the original Data Retrieval Session with a new **Time Filter**. To apply the changes that you make to the **Time Filter** configuration, click **Apply** in the **Edit Session** dialog.  
  
<a name="BKMK_ManuallySetTimeFormats"></a>   
## Manually Specifying Time Formats  
 To enable manual entry of time window boundaries in a specific format, select the **Use Start Filter** and **Use End Filter** check boxes. These selections make the corresponding time boundary text boxes writeable, so that you can specify time values in a format that is suitable for the displayed data. Thereafter, as you adjust the time slider controls, the changing time window boundary values match the time stamp format of the displayed data. This feature accommodates for message data that may have time stamps in a format that Message Analyzer cannot adequately determine, as indicated in the previous table.  
  
 The **Time Filter** configuration that you specify is then applied by Message Analyzer when you start the Data Retrieval Session with a click the **Start** button of the **New Session** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about reconfiguring a Data Retrieval Session and re-running it, see [Editing Existing Sessions](editing-existing-sessions.md).   
**To learn more** about creating an OPN configuration file for text logs with a proprietary format, the [OPN Configuration File for Text Log Adapter](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) document is available as a TechNet download.   
---