---
title: "Netlogon Message Types | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d3bfc501-c144-4c65-a532-9f2be4bf2154
caps.latest.revision: 16
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Netlogon Message Types
The **Netlogon Message Types** view **Layout** for **Charts** enables you to obtain a high-level summary view of specific data from a Netlogon.log file that depicts the relative percentage of message volumes for each message type in the log. The **Layout** uses a **Pie** chart visualizer component where the volume for each message type is represented by a slice of the chart. The legend to the right of the **Pie** chart exposes each message type in a list of nodes for quick correlation with the message volumes represented in the **Pie** chart.  
  
> [!NOTE]
>  A Netlogon.log file will be parsed only if you select the **Netlogon** configuration file in the **Text Log Configuration** drop-down list of the **New Session** dialog for a Data Retrieval Session prior to loading the data into Message Analyzer. Otherwise, no data will display in the **Netlogon Message Types** view **Layout**.  
>   
>  ___________________\_  
>   
>  **More Information**   
>  **To learn more** about working with text-based .log files, see [Opening Text Log Files](opening-text-log-files.md).  
> ___________________\_  
  
## Using the Netlogon Message Types Layout  
 This **Layout** enables you to assess at-a-glance the distribution of message type volumes in a Netlogon.log file so that you can  quickly focus on message types of interest. For example, you will likely want to review any log entries that contain error or diagnostic information first and this would mean looking at the messages of type CRITICAL and DIAGNOSIS. You might also review MAILSLOT messages for records of client and server communications and PERF messages that can include performance counter information related to setting up client-server sessions and the number of authentication timeouts that have occurred.  
  
 When your mouse hovers over any slice in the **Pie** chart, a tool tip  displays a log message type and a value that represents the percent volume for the message type out of the total volume of all message types in the log. At the same time, the message type is highlighted in the chart's message type  legend. Note that this legend is interactive, as is the **Pie** chart itself, and either of these enable you to drive the display of common message types into a new instance of the **Analysis Grid** viewer by double-clicking a legend node or a slice in the **Pie** chart, respectively, for further analysis of a particular log message type.  
  
 With these capabilities, you can quickly expose the data of different message types, which is very convenient when you need to detect errors and other important information that is buried in a large log file.  
  
 **Interactive Analysis**   
This **Layout** for the **Chart** viewer is intended to work with the **Netlogon** **Layout** for the **Analysis Grid** viewer and the **Netlogon Group by Message Type** **Layout** for the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **Netlogon Logs** **Profile** and will display after you  load data from a Netlogon.log file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 As an additional example of interactively driving the display of messages, if you select any **msgtype** group  in the **Grouping** viewer, you can display all the messages associated with a particular message type in the **Analysis Grid** viewer for further analysis, which includes reviewing **Summary** information and message **Details**.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about interactively analyzing Netlogon log data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **Netlogon** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **Netlogon Group by Message Type** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **Netlogon Logs** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  
___________________\_