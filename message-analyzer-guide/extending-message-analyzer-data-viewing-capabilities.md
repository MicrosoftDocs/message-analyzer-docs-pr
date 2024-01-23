---
title: "Extending Message Analyzer Data Viewing Capabilities | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70b2283e-68fd-4fc4-8a26-17669f491609
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Extending Message Analyzer Data Viewing Capabilities

Although Message Analyzer provides many built-in data viewers that attempt to address common analysis scenarios, it can be to your advantage to customize your data analysis environment with additional data viewing capabilities that meet your specific needs. Message Analyzer accommodates for these requirements by allowing you to extend Message Analyzer data viewing capabilities with custom **Layouts** of your own design that you can create for the **Chart** viewer. When you create your own **Layout**, you can configure any one of several types of graphic data visualizer components along with one or more data formulas that you can specifically craft to provide data analysis capabilities that streamline your work.  
  
> [!IMPORTANT]
>  The process of creating   **Chart** viewer **Layouts** has been simplified in Microsoft Message Analyzer v1.4 to make it easier for users to create them. One of the most apparent departures from the former process that simplifies the configuration is the fact that you can now add one visualizer component only to any one **Layout**, as indicated immediately below. The process to create formulas has been simplified as well, as described later in this section.  
  
 When you are creating a new **Chart** viewer **Layout**, you have the option to select one of the following types of graphic visualizer components for your **Layout**. Note that the built-in **Layouts** for the **Chart** viewer each use one of these same data visualizer components, as follows:  
  
-   **Bar** element  
  
-   **Pie** slice  
  
-   **Timeline** graph  
  
-   **Table** grid  
  
---  
  
 **What You Will Learn**   
In the topics of this section, you will learn about the functions of **Chart** **Layout** configuration features, how to use them to create new **Layouts** that you can display whenever you require them for analysis, and how to manage and share your custom **Layout** assets with others, through the Message Analyzer Sharing Infrastructure. A walkthrough of a built-in **Chart** viewer **Layout** that Message Analyzer provides by default is included for the benefit of exposing the behind-the-scenes configuration of a working **Layout** so that you can come up to speed on the process of creating a new **Chart** viewer **Layout**.  

---  
  
## In This Section  

 **[Configuring Chart Viewer Layouts](configuring-chart-viewer-layouts.md)**  — learn about the constraints  with which you must work when creating a **Chart** viewer **Layout** of your own design,  the built-in **Chart** viewer **Layouts** that are provided with Message Analyzer by default, the visualizer components that Message Analyzer uses in the built-in **Chart** viewer **Layouts** and that you can likewise use in your own **Layouts**, along with the criteria for choosing a visualizer component type for a custom **Layout** of your own. You can also read an overview about configuring a custom **Chart** viewer **Layout**.  
  
 **[Using the Edit Chart Layout Dialog](using-the-edit-chart-layout-dialog.md)**  — learn about the controls and features that you can use to create and save your own custom **Layouts** with a visualizer component that you specify. Also describes how to use the **Edit Chart Layout** dialog to set **Chart Properties**, **Series Fields**, and **Values**; and the **Formula Editor** dialog in which you can create data formulas based on a specified operation that manipulates message field data or computed values.  
  
 **[Configuration Walkthrough of a Built-In Chart Viewer Layout](configuration-walkthrough-of-a-built-in-chart-viewer-layout.md)**  — perform a walkthrough of the built-in **TCP/UDP Conversations by Message Count** **Layout** for the **Chart** viewer to familiarize yourself with the configuration features that you can use to create a functioning **Layout**. This particular **Layout** exposes the network conversations in a set of trace results and the transports that carried those conversations, along with a set of statistics for analyzing performance that includes message volume, payload volume in bytes, data transmission rate, and duration for each conversation.  
  
 **[Managing Chart Viewer Layouts](managing-chart-viewer-layouts.md)**  — learn how you can use the Message Analyzer Sharing Infrastructure to manage the **Message Analyzer Chart View Layouts** Library asset collection, which includes managing individual collection items through context menu commands such as **Edit**, **Create a Copy**, and **Delete**; and creating an item collection that you can share with others or retrieving a collection that was shared by others.