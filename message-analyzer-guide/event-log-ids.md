---
title: "Event Log IDs | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f2d46ca-a271-457f-8b47-04709f467fe0
caps.latest.revision: 25
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Event Log IDs
The **Event Log IDs** viewer **Layout** for **Charts** provides a horizontal **Bar** element  visualizer component that displays the message count associated with each **EventID** in an event  (\*.evtx) log. This **Layout** provides an immediate visual assessment of the relative distribution of message volume per **EventID** — ordered from the highest to the lowest volume. As you might expect, this exposes which **EventIDs** had the most significant volumes.  
  
## Using the Event Log IDs Layout  
 From a quick visual assessment of the data in this **Layout** alone, you can determine the events that involved the highest message count, which could be an indication of where  further investigation is needed, for example, very busy processes that are generating a large number of events. High volumes might also point to an overburdened system component or application that is issuing a lot of event traffic or experiencing a high rate of errors. Sparse traffic might be an indication of dropped packets due to misconfigured ETW Session buffer settings, as described in [Specifying Advanced ETW Session Configuration Settings](specifying-advanced-etw-session-configuration-settings.md).  
  
 **Interactive Analysis**   
The **Event Log IDs** **Layout** for the **Chart** viewer is intended to work with the **Event Log** **Layout** for the **Analysis Grid** viewer and the **Event Viewer** **Layout** for the **Grouping** viewer, to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **Event Logs Profile** and will display after you  load data from a \*.evtx file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 As an example of interactively driving the display of messages associated with a particular **EventID**, you can double-click any bar element in the **Event Log IDs** **Layout** to display the messages associated with that element in a new instance of the **Analysis Grid** viewer for focused analysis of the messages associated with a particular **EventID**. The  **Event Viewer** **Layout** for the **Grouping** viewer also enables a greater interactive context with additional enhancements to the analysis process.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about interactively analyzing Event log data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **Event Log** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **Event Viewer** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **Event Logs** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  
___________________\_