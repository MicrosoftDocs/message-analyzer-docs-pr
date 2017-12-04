---
title: "Filtering Message Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2eb99839-d102-47ca-9c90-54c8b440c58a
caps.latest.revision: 34
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Filtering Message Data
This section describes various ways to filter message data in Message Analyzer so that you can focus on traffic that is isolated by specific message type, field value, address, port communication, string value, diagnosis type, and so on. You can use Filter Expressions to select specific data from saved files or live captures when a Data Retrieval Session or Live Trace Session is running, respectively. You can also apply Filter Expressions when you are working with trace *results* to narrow down your view to specific data of interest while filtering out all the rest. In addition, you can either specify built-in Filter Expressions, or you can manually create your own.  
  
 You can even create a Filter Expression that uses an **Alias** (typically a friendly name that replaces some cryptic field value; see [Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md)), and you can save such a filter in the centralized Filter Expression **Library**. This enables you to use the Filter Expression that incorporates an **Alias** as a **Session Filter** or a view **Filter**. Note that you can also create Filter Expressions that include **Unions**.  
  
 ______________________\_  
  
 **What You Will Learn**   
In the topics of this section, you will specifically learn about Message Analyzer filtering capabilities, which includes filtering imported data in a Data Retrieval Session, filtering data while it is captured in a Live Trace Session, filtering trace results, and learning how to create your own Filter Expressions, as described below.  
______________________\_  
  
## In This Section  
 **[Filtering Loaded Input Data](filtering-loaded-input-data.md)**  — apply a built-in or user-developed **Session Filter** or a **Time Filter** to a Data Retrieval Session to constrain input message volume; also use input file selection as a method of limiting input data.  
  
 **[Filtering Captured Input Data](filtering-captured-input-data.md)**  — apply numerous types of driver-level filters to focus on specific types of messages in a trace, so you can limit the amount of data you will capture in a Live Trace Session for problem solving. Provider-level filters include **Fast Filters**, **Keyword** bitmask filters, **Level** filters, **WFP Layer Set** filters, **HTTP** filters, host adapter NDIS layer filters, and Hyper-V-Switch extension layer filters.  
  
 **[Filtering Live Trace Session Results](filtering-live-trace-session-results.md)**  — assess the functions of built-in view **Filters**, so you can better utilize them to apply filtering to a set of trace results.  
  
 **[Filtering Column Data](filtering-column-data.md)**  — make use of the **Analysis Grid** viewer **Column Filter** feature to quickly display only messages with fields that contain search text that you specify in a **Column Filter Row** text box.  
  
 **[Writing Filter Expressions](writing-filter-expressions.md)**  — write your own Filter Expressions with the Message Analyzer Filtering Language, which is based upon the Open Protocol Notation (OPN) language.  
  
 ___________________\_  
  
 **Go To Procedures**   
To proceed directly to procedures that demonstrate the filtering features described in this task area, see **[Procedures: Using the Data Filtering Features](procedures-using-the-data-filtering-features.md)**.  
___________________\_  
  
## See Also  
 [Applying and Managing Filters](applying-and-managing-filters.md)