---
title: "SysLog Levels | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7aa26cf4-da8c-4f81-a224-d50e35e6e9e9
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# SysLog Levels
The **SysLogLevels** view **Layout** for **Charts** enables you to quickly assess the relative distribution of the log entry volumes per information **level** value that exist in a SambaSysLog file. The **Layout** uses a **Bar** element visualizer component that provides a label to the left of the bar elements to display the value of  associated information **levels** in a SambaSysLog. Each horizontal graphic bar element in this **Layout** extends to a certain length that corresponds to the log entry volume for a specific information **level**. Each bar element is also tagged with a number that appears to the right of the element to represent the total number of entries that contain a particular **level**.  To the right of the bar element display, there is set of labels that indicate what percent of the total number of log entry **levels** each bar element represents. Also, in the bottom right sector of the **Layout**, the total number of log entries with level designations is displayed.  
  
> [!NOTE]
>  A SambaSysLog.log file will be parsed only if you select the **SambaSysLog** configuration file in the **Text Log Configuration** drop-down list of the **New Session** dialog for a Data Retrieval Session prior to loading the data into Message Analyzer. Otherwise, no data will display in the **SysLogLevels** view **Layout**.  
>   
>  ___________________\_  
>   
>  **More Information**   
>  **To learn more** about working with text-based .log files, see [Opening Text Log Files](opening-text-log-files.md).  
> ___________________\_  
  
## Using the SysLogLevels Layout  
 With the **SysLogLevels** view **Layout** for **Charts**, you can instantly assess the areas in your log that had the most critical **levels**, which can indicate an initial direction in which further investigation might proceed. SambaSysLog **levels** typically consist of the following. As expected, errors and warnings are usually the most critical to review, as described in "Interactive Analysis" ahead:  
  
-   0 — Error  
  
-   1 — Warning  
  
-   2 — Notice  
  
-   3 — Information  
  
-   4+ — Debug  
  
 **Interactive Analysis**   
The **SysLogLevels** view **Layout** is intended to work with the **SysLog** view **Layout** of the **Analysis Grid** viewer and the **SysLog** view **Layout** of the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **Samba Logs** **Profile** and will display after you  load data from a SambaSysLog.log file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 For example, to interactively analyze SambaSysLog data, you can  drive the display of log  entries that contain **level** designations into the **Analysis Grid** viewer by double-clicking any bar element for a particular **level** in the **SysLogLevels** view **Layout**. Thereafter, you can review status information and other content for any log entry in the **Summary** column of the **Analysis Grid** viewer along with log entry fields and values in the **Details** **Tool Window**. If you want to isolate log entries that contain an error or warning, you might apply a view **Filter** to the **Analysis Grid** viewer such as `*Summary contains "level=0"` or `*Summary contains "level=1"`, respectively. You can also quickly isolate **level** data from high volume SambaSysLog.log files with the **Grouping** viewer, as described immediately below.  
  
 The **SysLog** view **Layout** for the **Grouping** viewer also enables a greater interactive context with additional enhancements to the analysis process. For example, this  **Layout** is organized with **level** values as the top groups with nested **function** groups, and  nested **source_file** groups beneath that. The advantage of this viewing configuration is that you can isolate the log entry data to the top group (the Samba information **level**), then to the first nested group (the Samba **function** that wrote the log entry), and finally to the second nested group (the Samba **source_file** that contains the function that logged an entry). As you select these groups, the log entries associated with them display in the **Analysis Grid** viewer for a focused assessment of details. This grouped configuration enables you to streamline and prioritize your investigation based on the **level** values, which is a good starting point from where you can determine, in a hierarchical manner, the functions and source code that are associated with the most critical **levels**.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about interactively analyzing SambaSysLog data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **SysLog** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **SysLog** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **Samba Logs** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  
___________________\_