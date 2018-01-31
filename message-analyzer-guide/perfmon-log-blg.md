---
title: "Perfmon Log (.blg) | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ffb3c07-b607-4a97-b1cd-382cf65700d1
caps.latest.revision: 14
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Perfmon Log (.blg)

The **Perfmon Log** view **Layout** for **Charts** enables you to display data from a Performance Monitor log and utilize some of Message Analyzer capabilities to manipulate and analyze the data whenever you load data from a \*.blg log file. This **Layout** provides a main display with a graphic representation of performance counter data along with a legend of counters and an adjustable time window for zooming into data points. It displays a related set of messages after you double-click a line of performance counter data for further details.  
  
 **Interactive Analysis**   
This **Layout** for the **Chart** viewer is intended to work with the **Perfmon Log** **Layout** for the **Analysis Grid** viewer and the **Perfmon Log** **Layout** for the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **Perfmon Logs** **Profile**. The **Perfmon Log** **Layouts** for the **Chart** and **Grouping** viewers both display by default after you  load data from a \*.blg file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu). However, you will need to manually display the **Analysis Grid** viewer with the **Perfmon Log** **Layout**.  
  
 Consider the following as an example of interactively driving the display of messages into different viewers from the **Grouping** viewer, which contains the following groups to organize the data:  
  
-   **Machine**  
  
-   **Instance**  
  
-   **Counter**  
  
 Under any **Instance** group, you can click a **Counter** and display that result in the **Perfmon Log** **Layout** of the **Chart** viewer. In addition, you can double-click the resulting counter data line and display the logged data in an associated set of messages in a new instance of the **Analysis Grid** viewer. Otherwise, if the **Analysis Grid** viewer is already open in the session, it will simply be updated with the same set of messages.  
  
## See Also  

[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)