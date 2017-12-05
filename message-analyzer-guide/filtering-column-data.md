---
title: "Filtering Column Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82d73678-8a33-4c1c-9262-38291d2c01b4
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Filtering Column Data
To enable you to rapidly isolate messages containing specific field values, names, or other text in a set of trace results displaying in the default **Analysis Grid** viewer, Message Analyzer provides a **Column Filter** feature. This feature enables you to filter a set of trace results based on search text that you enter in a **Column Filter** text box above most **Analysis Grid** viewer data columns. As soon as you enter a text value in a **Column Filter** text box, only the messages that meet the criteria of the search text that you specify in a particular column are displayed, while all other messages are temporarily hidden. To remove the effects of an applied **Column Filter** value and return to the original message set, you can manually clear the specified text value or you can click the **Clear Search** “x” in the **Column Filter** text box.  
  
## Enabling Column Filter Text Entry  
 To display **Column Filter** text boxes for the data columns displayed in the **Analysis Grid** viewer, click the **Show Column Filter Row** icon in the upper-left sector of the **Analysis Grid** viewer tab, immediately to the left of the **MessageNumber** column. When you click the **Column Filter** icon, a row of light amber-colored **Column Filter** text boxes displays immediately below the name of each column, with the exception of the **Diagnosis** column. To hide the **Column Filter** text boxes, click the **Show Column Filter Row** icon again.  
  
> [!NOTE]
>  The **Column Filter** feature is also available in the message **Details** **Tool Window**. You can display these **Column Filter** text boxes in **Details** in a manner that is similar to the previously described method.  
  
## Locating Messages with Matching Search Text  
 As you type search text into a **Column Filter** box, the filter results display immediately so you can quickly locate messages, field values, or other text of interest. For example, if you ran a Live Trace Session with the **Local Network Interfaces** **Trace Scenario** and you wanted to look at all the UDP messages that you captured, you could type “UDP” in the **Column Filter** text box at the top of the **Module** column of the **Analysis Grid** viewer. This action would display only the top-level UDP messages in a trace. Note that **Column Filters** do not recognize text matches in the origins tree (stack), unless a stack message node containing the search text is already open and the matching text is exposed. In this case, such a message would also be returned as a match.  
  
> [!TIP]
>  **Column Filter** input values are case-insensitive.