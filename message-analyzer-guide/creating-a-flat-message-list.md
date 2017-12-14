---
title: "Creating a Flat Message List | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: b314a3d9-4811-4083-a9f6-12c7fd07866d
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Creating a Flat Message List
A new feature is now included in Message Analyzer for Microsoft Network Monitor users who are making the transition to the Message Analyzer tool, to enable them to create a flattened message display  that appears similar to  the way Network Monitor displays a set of trace results. Users can initiate this type of message display by clicking the **Flat Message List** button on the Filtering toolbar.  
  
 When you select this command, messages are displayed at top-level in their original chronological order, where each request/response message pair is no longer encapsulated under a separate Operation node. However, note that there is a slight difference  between Message Analyzer and Network Monitor in this context, in that Message Analyzer's top-level messages also encapsulate the origins (stack) messages, including fragments under expandable nodes, whereas Network Monitor does not. The included message stack data  provides an additional level of detail that is quickly accessible for analysis. Moreover, even while the **Flat Message List** command is active against a set of trace results and Operations are broken apart, you can still see the request and response message pairs side-by-side in the **Message Stack** **Tool Window**, by selecting any request message in the **Analysis Grid** viewer.  
  
 After you apply the **Flat Message List** command to a set of trace results and you want to return to the default message display configuration in the **Analysis Grid** viewer with Operation nodes intact, you can simply click the **Flat Message List** button again. Note that while the **Flat Message List**  command is active against a set of trace results, its associated button on the Filtering toolbar remains highlighted.  
  
> [!NOTE]
>  When you apply this command to a set of trace results, you may notice a significant difference in message count that displays in the **Available** label on the Message Analyzer status bar. This can result from message fragments that were formerly encapsulated under an Operation node,  but are now pushed to top-level in the **Analysis Grid** viewer, thus adding to the **Available** message count.