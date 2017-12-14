---
title: "Applying a Session Filter to a Data Retrieval Session | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 9f398ff4-94ae-47b3-bf60-ec0f5dc58b25
caps.latest.revision: 41
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Applying a Session Filter to a Data Retrieval Session
After specifying one or more data sources in a Data Retrieval Session, you can apply a **Session Filter** expression to those data sources to filter the loaded message data to specific criteria. The same data selection capability is provided for Live Trace Sessions, where you can also apply a **Session Filter** expression to select specific data that is returned in your trace results. A **Session Filter** is shown in the topic [Using a Session Filter](message-analyzer-tutorial.md#BKMK_UsingSessionFilter).  
  
 To apply a **Session Filter**, you can either choose a built-in Filter Expression or you can create your own. When you create your own Filter Expression or modify a built-in filter, you should be careful to create a valid Filter Expression, or you may not return any data. For further information about creating valid Filter Expressions, see the topic [Writing Filter Expressions](writing-filter-expressions.md) to learn about the Filtering Language that is used by Message Analyzer.  
  
 To specify one of the built-in Filter expressions as a **Session Filter** in a Data Retrieval Session (or a Live Trace Session), you can select the filter you want to use from the centralized **Message Analyzer Filters** asset collection **Library** that is accessible on the toolbar above the **Session Filter** text box in the **New Session** dialog. To review further information on selecting a **Session Filter** in various categories that Message Analyzer provides, see the topic [Selecting Built-In Session Filters](working-with-session-filters-in-a-live-trace-session.md#BKMK_SelectingSessionFilters). Note that the centralized Filter Expression **Library** is also accessible from the **Edit Session** dialog; and also from the Filtering toolbar just above the **Analysis Grid** viewer in any Analysis Session, where you can apply the same Filter Expressions to your trace results for data analysis purposes.  
  
> [!NOTE]
>  If you have created and saved a Filter Expression that uses an **Alias** (uses a friendly name that replaces some cryptic field value) or a **Union** (correlates two data fields with similar values but different names in a single new field), that Filter Expression will appear in the centralized **Library** drop-down list wherever this **Library** is exposed in the Message Analyzer user interface (UI). You can use such a Filter Expression that contains an **Alias** or a **Union**, just as you would any other filter.  
  
 By using a **Session Filter** to select specific data from a Data Retrieval Session, you can work with specific data that you want to focus on, so you can get to the heart of the issue at hand without being overloaded with superfluous information.  
  
> [!NOTE]
>  When you apply a **Session Filter** to a Data Retrieval Session, a funnel icon displays to the right of the corresponding top-level session node in the **Session Explorer** **Tool Window**, to indicate that the session has had a **Session Filter** applied to it. This icon provides a quick reminder of the analysis status of the session.  
  
---  
  
 **More Information**   
 **To learn more** about **Session Filters**, see relevant information in the topic [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md).  
**To learn more** about creating Filter Expressions and using the Message Analyzer Filtering Language, see [Writing Filter Expressions](writing-filter-expressions.md).   
**To learn more** about **Aliases**, see [Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md).   
**To learn more** about **Unions**, see [Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md).  
---