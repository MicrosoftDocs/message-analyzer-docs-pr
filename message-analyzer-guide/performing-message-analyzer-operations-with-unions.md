---
title: "Performing Message Analyzer Operations with Unions | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88677646-6c69-473d-b53f-adf49cdd8267
caps.latest.revision: 28
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Performing Message Analyzer Operations with Unions
After you create a **Union**, as described in [Creating Unions](creating-unions.md), it is a new entity that can function normally in various Message Analyzer operations. However, to facilitate the use of a **Union** in most of the operations described in this section, you will first need to add a column to the **Analysis Grid** viewer based on the **Union** name. To do this, open the **Field Chooser** **Tool Window** by clicking the **Add Columns** button on the **Analysis Grid** viewer toolbar. You can navigate to the **Union** of interest by clicking the root **Unions** node in the **Field Chooser** window to expose the **Unions** that it contains. You can then double-click the **Union** name to add it as an **Analysis Grid** viewer column. Thereafter, you can observe that such a **Union** functions as expected in the following Message Analyzer operations:  
  
-   **Sorting** — to sort a **Union** column in the orders indicated below, click the column header as follows:  
  
    -   **Ascending** — the first click on the **Union** column header sorts the **Union** values in ascending order, as indicated by an up arrow that appears on the column header, providing that the column header did not already display an up or down arrow.  
  
    -   **Descending** — the second click on the **Union** column header sorts the **Union** values in descending order, as indicated by a down arrow that appears on the column header.  
  
    -   **Unsorted** — the third click on the **Union** column header returns the messages to the order in which they were initially captured by Message Analyzer.  
  
        > [!NOTE]
        >  If you continue to click the **Union** column header after the initial three clicks indicated in this list, the column will be sorted in round-robin fashion, with ascending, descending, and unsorted results repeating over and over, in that order.  
  
-   **Grouping** — after you add the **Union** as a column in the **Analysis Grid** viewer as previously indicated, you can perform a Grouping operation, just as you do with any other **Analysis Grid** viewer column that contains a related set of values. In this case, the Grouping operation results in creating groups of data that are organized according to the different values that exist in the  column with the **Union** name. You can continue with additional Grouping operations on other **Analysis Grid** viewer columns that will typically result in nesting additional child data groups within the original parent **Union** group. By pivoting on various combinations of column data, you can create a variety of unique data analysis perspectives.  
  
    > [!NOTE]
    >  Because **Unions** now support sets, that is, multiple values for a particular field correlation, a **Grouping** operation will reflect the set values.  
  
-   **Filtering** — after you create and save a **Union**, it is available for use in a Filter Expression. The simplest way to create a Filter Expression with a **Union** is to right-click any field value in the **Union** column and select the **Add** ***‘\<unionName>'*** **to Filter** item, where '\<unionName>' is  a placeholder for an actual **Union** name. This might be the quickest way to create a valid Filter Expression with a **Union**, because Message Analyzer automatically passes the associated module into the Filter Expression and provides the correct syntax for the filter, as expressed in the following format: `module.unionName==someValue`. The Filter Expression then appears in the text box of the default Filter panel on the Filtering toolbar in the indicated format.  
  
     After you create a filter in this manner, you can add it to your centralized Filter Expression **Library** by selecting the **New Filter** item in the **Library** drop-down list in the default Filter panel on the Filtering toolbar. The text of the Filter Expression containing a **Union** is automatically passed to the **Edit Filter** dialog that displays. After you save the Filter Expression that contains your **Union**, you can use it in any Message Analyzer feature that has access to the centralized **Library**, which includes a **Session Filter** or view **Filter** that you can specify when you run a new session or when you are analyzing session results, respectively.  
  
-   **Pattern matching** — after you create and save a **Union**, it is available for building a Pattern Expression. For example, you can access the **Union** in the **Field Chooser** **Tool Window**, that you typically use to locate fields when creating a Pattern Expression. You can treat the **Union** the same way you do any other field, property, or annotation when using the **Pattern Editor** to build a Pattern Expression, although **Union** behavior in the Pattern Expression might be different than other fields, depending on how you construct the expression.  
  
-   **Color Rules** — after you create and save a **Union**, it is available for use in Filter Expressions that you can add to a **Color Rule** from the centralized Filter Expression **Library**. In the context of **Color Rule** functionality, the Filter Expression that contains a **Union** will behave in a manner that is similar to any Filter Expression that contains a comparable type. This is also true of other features that can use a Filter Expression, for example, a **Chart**.  
  
-   **Layouts** — after you create a **Union**, you can use the **Field Chooser** window to add it to the **Analysis Grid** viewer as a new column. Thereafter, you can save the current **Analysis Grid** column configuration as a new **Layout** that contains the **Union** column, which you can apply any time you want to recover that particular column configuration.  
  
## See Also  
 [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md)   
 [Filtering Live Trace Session Results](filtering-live-trace-session-results.md)   
 [Pattern Match Viewer](pattern-match-viewer.md)   
 [Creating and Modifying Color Rules](creating-and-modifying-color-rules.md)   
 [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)