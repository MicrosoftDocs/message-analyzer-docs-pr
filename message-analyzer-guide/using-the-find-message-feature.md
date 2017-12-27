---
title: "Using the Find Message Feature | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90491024-b84b-47b1-b340-aca8a8f4b880
caps.latest.revision: 30
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Using the Find Message Feature

When you are analyzing message data that is displayed in an **Analysis Grid** viewer tab, you have access to the **Find** function to search for and locate individual messages that meet the filtering criteria of a Filter Expression that you select or define. To enable the **Find** filtering mode, click the **Find Message** icon on the **Analysis Grid** viewer toolbar. After you select a predefined Filter Expression from the **Library**, or write one in the text box of the **Find Messages** window, click the **Find** binoculars icon to locate the next message that meets the specified filtering criteria. You can also click the **Find Previous** icon to return to a previous message in the trace results that meets the specified filtering criteria.  
  
## Utilizing the Advantages of the Find Message Function  

 One of the advantages of using the **Find** function to locate messages that meet specific filtering criteria is that you can locate single messages in a large data set relatively quickly. An even more important advantage is the context that the feature provides. Often, the messages that precede or trail a target message can provide an indication of what caused the condition that is reflected by the target message — for example, an error — which can be key to the analysis process. This can also include factors such as message types, field values, time stamps, and so on. By contrast, when you apply a view **Filter**, all messages are filtered out except those that meet the filtering criteria, which can obscure the surrounding context.  
  
## Specifying a Filter Expression for the Find Message Function  

 To specify a Filter Expression for the **Find** function, you can manually configure one or select a built-in expression from the centralized Filter Expression **Library** that is accessible in the **Find Messages** window, just as you would do when specifying a **Session Filter**, view **Filter**, or **Color Rule Filter**. The Filter Expressions that are available for the **Find** function are the identical **Library** items that you can access for **Session Filter** or view **Filter** configuration, and include any custom Filter Expressions that you create.  
  
> [!NOTE]
>  You can use the **Find** function to locate messages in the **Grouping** viewer that meet specified filtering criteria, providing that the **Grouping** viewer is in focus when you click the **Find** binoculars icon.  
  
---  
  
 **More Information**   
 **To learn more** about view **Filters**, see [Applying and Managing Filters](applying-and-managing-filters.md).  
**To learn more** about **Session Filters**, see [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md).  
**To learn more** about sharing Filter Expression Library items with others, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.  

---