---
title: "Top Level Protocols Message Count | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2668c9dc-64f0-4554-83e4-ba74c99a8bad
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Top Level Protocols Message Count

The **Top Level Protocols Message Count** viewer **Layout** for **Charts** illustrates message data in a horizontal **Bar** element visualizer component that provides an at-a-glance view of the relative volume of the top-level messages from different source modules or protocols in a set of trace results. If you double-click any data bar element representing a message source in this **Layout**, the details for the top-level messages represented by that particular data bar element are rendered in a new instance of the  **Analysis Grid** viewer for further analysis.  
  
## Using the Top Level Protocols Message Count Layout  

 This **Layout** can provide an immediate indication of which modules or protocols are the highest bandwidth consumers, based on the associated message count and/or the relative percent volume with respect to total volume of messages. As such, this **Layout** provides an at-a-glance view of the distribution of message volume per module in a set of trace results.  
  
> [!NOTE]
>  By double-clicking a bar element in this **Layout**, all messages in which the module is either a top-level message or part of message origins will display in a separate **Analysis Grid** viewer tab. Because all messages are displayed in a separate viewer tab as indicated, the message count in that viewer tab will differ from the **Total** message count specified in the **Top Level Protocols Message Count** viewer **Layout**. To see only the top-level messages in the new **Analysis Grid** viewer tab, you can apply a view **Filter** that isolates top-level messages by using the backslash symbol (“\”) described in [Browsing Message Origins](using-the-filtering-language.md#BKMK_BrowseMessageOrigins), as follows:  “\\<modulename\>” — where \<modulename> is a placeholder for the module or protocol of interest.  
  
 **Interactive Analysis**   
The **Top Level Protocols Message Count Layout** for the **Chart** viewer is intended to work with the **ETW** **Layout** for the **Analysis Grid** viewer and the **ETW Guids and IDs** **Layout** for the **Grouping** viewer, to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **ETW Analysis** **Profile** and will display after you  load data from an event trace log (\*.etl) file, provided that you previously enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 As an example of interactively driving the display of messages, you can double-click any bar element in the **Top Level Protocols Message Count** **Layout** to display the messages in a new instance of the **Analysis Grid** viewer for focused analysis of the messages associated with a particular protocol or module. The **ETW Guids and IDs** **Layout** for the **Grouping** viewer also enables a greater interactive context with additional enhancements to the analysis process.  
  
---  
  
 **More Information**   
 **To learn more** about interactively analyzing Event log data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **ETW** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **ETW Guids and IDs** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **ETW Analysis** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  

---  
  
## See Also  

[Top Level Protocols Message Count Over Time](top-level-protocols-message-count-over-time.md)