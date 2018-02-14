---
title: "Introduction to Creating and Applying Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 733db3b4-526d-4666-b11d-5b5f36ade20e
caps.latest.revision: 31
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Introduction to Creating and Applying Filters

If the built-in Filter Expressions in the centralized filter **Library** do not provide the filtering functionality you need to analyze your message traffic, you can create your own custom Filter Expressions. To help you create Filter Expressions, Message Analyzer has a built-in Filter IntelliSense service that provides a statement completion capability that is similar to the Visual Studio Statement Completion Service. The Filter IntelliSense Service provides support for configuring **Session Filters** for a Data Retrieval Session or a Live Trace Session, and for configuring view **Filters** in an Analysis Session. For further details about Filter IntelliSense for Filter Expressions, see the [Filter IntelliSense Service](filter-intellisense-service.md) topic.  
  
## Creating a Custom Filter  

 To create your own custom **Filters**, you will need to understand the Message Analyzer Filtering Language. As indicated earlier in [Assessing the Built-In Filter Expressions](filtering-live-trace-session-results.md#BKMK_AssesBuiltInFilters), you should first familiarize yourself with various Filter Expressions that exist in the **Message Analyzer Filters** asset collection, which is accessible from the **Library** drop-down list on the Filtering toolbar that appears above the main analysis surface for any set of trace results. As you work with these  filters and observe how they impact your trace results, you can derive an understanding that will help you when creating your own Filter Expressions that you can use as a view **Filter**, **Session Filter**, or **Viewpoint Filter**, which all use the same centralized filter **Library**. In the sections listed immediately below, you will learn about the concepts and constructs of the Filtering Language,  so you can use this information to create custom Filter Expressions and optionally add them as new assets to the centralized filter **Library**.  
  
## Generating a View Filter Dynamically  

 The easiest way to create a Filter Expression and apply it to message data displaying in the **Analysis Grid** viewer is to right-click a **Column** value and select the **Add**  ***\<columnName>***  **to Filter** command, to add the **Column** value as a Filter Expression. For example, if you right-click a protocol module in the **Module** column, the protocol name is added to the Filter Expression text box in a  Filter panel on the Filtering toolbar as your Filter Expression. This action creates a simple filter that is also referred to as an “atomic” filter, meaning that the Filter Expression contains no logical combinators such as OR, AND, or NOT, and has no left-hand-side expression. Note that dynamic generation of a Filter Expression only creates the filter code; you must then apply the Filter Expression to see the effects, as described in the section that follows.  
  
## Selecting and Applying a View Filter  

 As described in many topics of this Operating Guide, you can *select* a built-in Filter Expression from the centralized **Library** to apply to a set of trace results, as appropriate to the type of analysis you are performing. When you are ready to *apply* a view **Filter** to your trace results, click the **Apply** button on the Filtering toolbar to see the effect of the **Filter** on your message data. If you added a protocol name as your Filter Expression as previously indicated, the **Analysis Grid** viewer will display messages from the specified protocol only, which includes top-level messages or operations with that protocol name, in addition to any other top-level message that contains that protocol in its origins tree (stack).  
  
 Note that this differs from the way **Column Filters** work in regard to stack messages, where filtering evaluates exposed layers only, as described in [Filtering Column Data](filtering-column-data.md). The application of a view **Filter** is extremely useful for rapidly isolating the message data you want to analyze, especially in very large traces with thousands of messages. Also, in using the right-click method for adding a **Filter**, configuration is fast and return results are guaranteed, given that these Filter Expressions are derived from values that already exist in the set of trace results with which you are working.  
  
> [!NOTE]
>  Whenever you apply a Filter Expression from the Filtering toolbar, the in-focus session viewer tab and the corresponding session viewer node in **Session Explorer** both provide an indication of the Filter Expression that has been applied. You can view these indicators by hovering over the appropriate tab or node with your mouse. You will also see a funnel icon in both of these locations to indicate that a Filter Expression has been applied.  
  
 You can also use a Filter Expression to restrict your filter results to messages containing specific values. For example, you might specify a Filter Expression such as `UDP.Length > 100` to return only those UDP messages that have a message Length (Header + Payload) value that is greater than 100 bytes. Also, if you want to display all messages that are not UDP traffic, you could apply a filter such as `!UDP`. Moreover, if you want to filter out all UDP and TCP messages, you could apply a filter expression such as `!UDP&&!TCP`.  
  
> [!IMPORTANT]
>  The scope of a view **Filter** is NOT global, meaning that it's effects are applied to only the data viewer that is currently in focus. All other data viewers that are out of focus are not impacted. Therefore, you must apply separate **Filters** to each data viewer independently, as appropriate.  
  
## Maintaining History of View Filter Application  

 After you create and apply a custom Filter Expression, it is maintained in a common **History** drop-down list, where the last filter applied appears first. Like the centralized filter **Library**, the **History** drop-down list is accessible from any Data Retrieval Session, Live Trace Session, or Analysis Session, so that you can reapply any custom Filter Expression in the common **History** drop-down list as a **Session Filter** or a view **Filter**.  
  
> [!NOTE]
>  The **History** drop-down list currently maintains the last set of ten filters that you applied. However, for more permanent storage, you can save any custom Filter Expression that you create to the centralized filter **Library**, if you find that it is  useful. In addition, you can share all **Filter** items that exist in the **Library** with others through the Message Analyzer Sharing Infrastructure.  
  
 In the remaining topics of this section, you will learn more about the Filter IntelliSense service in addition to the concepts, semantics, syntax, and other details about the Filtering Language, so you can create robust Filter Expressions that manipulate trace results in unique ways for data analysis purposes. You can also review a set of procedures that provide numerous examples of using Filter Expressions to isolate data for focused analysis, as indicated below in ***See Also***.  
  
## See Also  

[Procedures: Using the Data Filtering Features](procedures-using-the-data-filtering-features.md)   
[Applying and Managing Filters](applying-and-managing-filters.md)