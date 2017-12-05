---
title: "Using a Custom Trace Scenario Template | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cfee9387-dfd7-4846-b77a-e54f612112c7
caps.latest.revision: 32
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Using a Custom Trace Scenario Template
Instead of using a built-in **Trace Scenario** to start a Live Trace Session, you can start one by utilizing any custom **Trace Scenario** template that you created, as described in [Designing a Trace Template](designing-a-trace-template.md). You create custom  **Trace Scenario** templates so that you can store them for quick access to common capture functionality that is tailored to your environment and that you can use on a repetitive basis.  You can display the provider configuration of any **Trace Scenario** template from the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog by selecting the scenario during Live Trace Session configuration. Note that all custom **Trace Scenarios** that you create are stored in the **My Items** category in the specified drop-down list when you click the **Save Scenario** button on the **ETW Providers** toolbar.  
  
 To create a **Trace Scenario** template, you will need to start by first selecting an existing **Trace Scenario** and then modifying it as required, as described in [Configuring a Live Trace Session](configuring-a-live-trace-session.md). Thereafter, you can run your custom **Trace Scenario** template as you would any of the built-in **Trace Scenarios**, for example, the **Local Network Interfaces** scenario.  
  
## Running and Handling Trace Scenario Templates  
 Message Analyzer provides you with some flexibility when running and handling **Trace Scenario** templates. For example, after you select a trace template during Live Trace Session configuration, you can do any of the following:  
  
-   Run the template as-is to capture the specific type of message data that the template is configured to retrieve in your Live Trace Session.  You can then save the results in one of the Message Analyzer native trace file formats, as described in [Saving Session Data](saving-session-data.md).  
  
-   Modify the template and then run it in a Live Trace Session to capture message data.  
  
-   Update the template and then save it without running it.  
  
-   Export the template in a specified asset collection, which can contain built-in **Trace Scenarios** and any scenario templates that you create, so that you can share them with others; either on a user-designated file share or through a user-configured feed in the Message Analyzer Sharing Infrastructure.  
  
    > [!TIP]
    >  You can also import a **Trace Scenario** asset collection that others have shared to a designated location through the Message Analyzer Sharing Infrastructure.  
  
-   Set a custom **Trace Scenario** template to Favorite  status in the **Trace Scenario** user Library, so that you can instantly start a Live Trace Session that uses such a scenario. All **Favorite Scenarios** are available from the Message Analyzer **Start Page**,  the global Message Analyzer **File** menu, and the global Message Analyzer tool bar. Note that if you set a custom **Trace Scenario** template to Favorite status, it will be highly accessible from numerous locations in the Message Analyzer user interface (UI). For information on setting favorites, see [Selecting a Trace Scenario](selecting-a-trace-scenario.md).  
  
 The distinction between a built-in **Trace Scenario** and a **Trace Scenario** template is minor. All **Trace Scenarios** that are accessible from the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog are essentially trace configuration templates, because a template does not yet contain data.  
  
 When you create a particular trace configuration and click the **Save Scenario** button, you create your own *custom* trace configuration template that you can run at any time, just like any built-in **Trace Scenario**. When you save such a **Trace Scenario** template as indicated, the template itself will contain no data. But similar to all **Trace Scenarios**, when you run a **Trace Scenario** template in a Live Trace Session that captures data, you can then save the Live Trace Session *results* in the Message Analyzer native trace file .matp or .cap format. This file will contain your actual message data, whether the initial Live Trace Session provider configuration was a result of selecting a custom **Trace Scenario** template of your own design, or the result of selecting one of the Message Analyzer built-in **Trace Scenarios**.  
  
> [!NOTE]
>  You can run a custom **Trace Scenario** and save session results as many times as you want. If you maintain a common capture configuration in a particular **Trace Scenario**, you can create a baseline for comparing similar trace results from day to day.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about **Trace Scenario** templates, see [Creating and Managing Custom Trace Scenarios](creating-and-managing-custom-trace-scenarios.md).   
**To learn more** about exporting and importing **Trace Scenarios**, including **Trace Scenario** templates, see [Managing Trace Scenarios](managing-trace-scenarios.md).   
___________________\_