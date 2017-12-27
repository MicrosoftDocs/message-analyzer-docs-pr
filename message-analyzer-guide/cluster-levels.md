---
title: "Cluster Levels | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62d8ac04-9a97-4611-b1f4-9f8481420535
caps.latest.revision: 27
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Cluster Levels

The **Cluster Levels** viewer **Layout** for **Charts** provides a horizontal **Bar** element visualizer component that displays the log entry  count for each of the  information levels (**InfoLevel**) that exist in a Cluster.log file that were reported by components of the Cluster Service.  The typical values for **InfoLevel** consist of **DBG**, **INFO**, **WARN**, and **ERR**. These **InfoLevel** values provide  debug information, status information, warnings, and errors that were reported to the Cluster log by various subcomponents of the Cluster Service, such as the Global Update Manager (GUM), Failover Manager (FM), Node Manager (NM), and Database Manager (DM) services.  
  
 With the **Cluster Levels** viewer **Layout**, you can obtain a quick assessment of which information levels have the most log entry activity. The bar element configuration of this **Layout** provides an at-a-glance summary of the relative distribution of log entry volume for each of the information types found in a Cluster log file. The information level values of the most interest are likely to be the warnings (**WARN**) and errors (**ERR**), which can point you to areas in the Cluster Service on which your analysis should focus.  
  
> [!NOTE]
>  A Cluster.log file will be parsed only if you select the **Cluster** configuration file in **Text Log Configuration** drop-down list of the **New Session** dialog for a Data Retrieval Session prior to loading the data into Message Analyzer. Otherwise, no data will display in the **Cluster Levels** view **Layout**.  
>   
>---  
>   
>  **More Information**   
>  **To learn more** about working with text-based .log files, see [Opening Text Log Files](opening-text-log-files.md).  
>---  
  
## Using the Cluster Levels Layout  

 When you review the data presented in the **Cluster Levels** viewer **Layout**, you might notice a significant volume of log entries with **ERR** levels being reported. To assess these entries, you might proceed by double-clicking the **ERR** bar element to isolate all the log entries that contain the **ERR** **InfoLevel** type in a new instance of the **Analysis Grid** viewer. Then you can sort the **SubComponent** column of the **Analysis Grid** viewer in ascending order to consolidate all the subcomponents of the same type together for easier viewing. Thereafter, you can review the **RemainingText** column for descriptions of the errors and failures that occurred for each subcomponent of the Cluster Service. Note that you might also execute the **Group** context menu command on the **Subcomponent** column of the **Analysis Grid** viewer to create a grouped view of the subcomponents and the associated log entry counts for an enhanced perspective of the data. Moreover, you can use the **Cluster Logs** **Layout** for the **Grouping** viewer to create a hierarchical grouped configuration of nested **InfoLevel**, **Subcomponent**, and **ProcessId** groups, so that you can quickly isolate the data according to **InfoLevel** values and view the underlying **Subcomponents** that logged the debugging information.  
  
 **Interactive Analysis**   
This **Layout** for the **Chart** viewer is intended to work with the **Cluster Log** **Layout** for the **Analysis Grid** viewer and the **Cluster Logs** **Layout** for the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **Cluster Logs** **Profile** and will display after you  load data from a Cluster.log file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 As an example of interactively driving the display of messages, if you select an **InfoLevel** group in the **Grouping** viewer, you can display all the messages associated with that particular error level in the **Analysis Grid** viewer for further analysis of details.  
  
---  
  
 **More Information**   
 **To learn more** about interactively analyzing Cluster log data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **Cluster Log** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **Cluster Logs** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **Cluster Logs** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  

---