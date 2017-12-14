---
title: "Specifying a Parsing Level | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33d8362b-c15d-46ce-a42f-6ab3653abedb
caps.latest.revision: 13
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Specifying a Parsing Level
If you are loading large traces into Message Analyzer, you might consider setting a built-in **Parsing Level** to improve performance.  Because **Parsing Level** scenarios typically limit how far up the message stack Message Analyzer will parse, you can reduce the overall number of messages processed and dramatically improve performance. Also, by choosing a **Parsing Level**, you can create a more targeted message set to improve your analytical focus. This is because most **Parsing Level** scenarios contain predefined filters that are beneficial to message analysis at the top stack level on which any particular **Parsing Level** scenario creates focus.  
  
---  
  
 **More Information**   
 **To learn more** about **Parsing Levels** and the built-in scenarios that you can employ, see [Setting the Session Parsing Level](setting-the-session-parsing-level.md).  
---