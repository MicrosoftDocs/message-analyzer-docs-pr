---
title: "Performing Message Analyzer Operations with Aliases | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa1965ef-b012-4629-99a2-9af59221ef8f
caps.latest.revision: 25
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Performing Message Analyzer Operations with Aliases

Message Analyzer enables you to use **Aliases** in the following common operations that you can employ when analyzing session results:  
  
[Using an Alias in a Filter Expression](performing-message-analyzer-operations-with-aliases.md#BKMK_AliasFilters)   
[Sorting Operations with Aliases](performing-message-analyzer-operations-with-aliases.md#BKMK_AliasSorting)   
[Grouping Operations with Aliases](performing-message-analyzer-operations-with-aliases.md#BKMK_AliasGrouping)  
  
 This section briefly describes these capabilities, in addition to the dynamic application of **Aliases** as you are acquiring input message data through a Live Trace Session or a Data Retrieval Session.  
  
<a name="BKMK_AliasFilters"></a>   
## Using an Alias in a Filter Expression  
 Message Analyzer enables you to use an **Alias** in Filter Expressions.  Any applied filter that uses an **Alias** should behave in a manner that is similar to any other functionally equivalent filter. However, when creating filters that use **Aliases**, you must consider that the **Alias** name is always a string.  For example, if you want to create a view **Filter** that isolates source traffic based on a hypothetical **Alias** named "MyComputer", you might have a Filter Expression that looks similar to the following examples:  
  
 `*Source=="MyComputer"`   
  `<moduleName>.Source == “MyComputer”`  
  
 Also note that you can still use the original data type that underlies the **Alias** configuration, for example, an IP address. In this case, the equivalent Filter Expression might look similar to the following:  
  
 `*Source==192.168.1.1`  
  
 You should be aware that because an IP address is a different data type, no quotes are used in the latter Filter Expression.  
  
 After you create and save a Filter Expression with the **Edit Filter** dialog — accessible by clicking the **New Filter** item in the **Library** drop-down list on the default Filter panel of the Filtering Toolbar — and that expression uses an **Alias**, as expected the Filter will  appear in the centralized Filter Expression **Library** — accessible from any Filter panel on the Filtering Toolbar and on the toolbar above the **Session Filter** text box of the **New Session** dialog. Because any Filter Expression that contains an **Alias** is saved in the centralized Filter **Library**, you can use such an expression as a **Session Filter** or view **Filter**. However, for an **Alias** to function properly in either of these Filter Expressions, the **Alias** must be enabled in the **Aliases** drop-down list, which you can access on the global Message Analyzer toolbar. Also, if you change a Filter Expression that contains an **Alias** in mid-stream during a capture, the changes will immediately take effect.  
  
> [!NOTE]
>  If you attempt to use the [Filter IntelliSense Service](filter-intellisense-service.md) to compose a Filter Expression with an **Alias**, you will be unable to find any **Aliases** in the IntelliSense tree because this capability is not yet supported.  
  
<a name="BKMK_AliasSorting"></a>   
## Sorting Operations with Aliases  
 After you create or apply an **Alias**, the data fields in an **Analysis Grid** viewer column for a supported data type may contain varying types such as integers, strings, or others such as addresses. If you sort such a column by clicking the column header, or by clicking the ascending or descending column arrow, it will be sorted in lexicographical order. For example, sorting results might look like the following:  
  
 23.34.51.101  
34.56.11.23  
ClientComputer  
FF02:0:0:0:0:0:1:3  
  
<a name="BKMK_AliasGrouping"></a>   
## Grouping Operations with Aliases  
 If you group an **Analysis Grid** viewer column that supports aliasing and an **Alias** is enabled that corresponds with data field value instances that display in that column, Message Analyzer will create a separate group among other group nodes to contain the messages that correspond with the **Alias** name. For example, if you have a **Source** IP address for which you created an **Alias** named “MyComputer” and you perform a grouping operation, by right-clicking the **Source** column in the **Analysis Grid** viewer and selecting the **Group** command, the results will show expandable **Source** nodes (groups) that display the following information:  
  
-   The number of messages in parentheses for each node or group.  
  
-   The data field value, in this case an IP address or the **Alias** name.  
  
For the hypothetical **Alias** named “MyComputer”, the group identifier might look similar to the following:  
  
**>** **Source  (110): MyComputer**  
  
If you expand this group by clicking the arrow, you will see only the messages that have a “MyComputer” **Alias** in the **Source** column of the **Analysis Grid** viewer.  
  
## Dynamically Applying Aliases  

 If you have a Live Trace Session in progress or if you are in the process of loading static data into Message Analyzer through a Data Retrieval Session, you can create a new **Alias** or enable/disable an existing **Alias** and the results will immediately take effect.  
  
---  
  
 **More Information**   
 **To learn more** about view **Filters**, see [Applying and Managing Filters](applying-and-managing-filters.md).   
**To learn more** about grouping, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).  

---