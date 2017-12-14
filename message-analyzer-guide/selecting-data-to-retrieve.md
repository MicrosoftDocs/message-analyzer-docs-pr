---
title: "Selecting Data to Retrieve | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a559223b-60a4-4a5a-9b0f-59d923df014f
caps.latest.revision: 40
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting Data to Retrieve
As part of the BSV model, Message Analyzer provides a data selection feature that enables you to define the scope of the information that you load through a session. Although the concept of data selection applies equally to loading saved data in a Data Retrieval Session and capturing data in a Live Trace Session, this section focuses on selecting data in a Data Retrieval Session.  
  
## Using Data Selection  
 To use the data selection feature, you must configure your Data Retrieval Session to select specific data based on configurable criteria prior to starting the actual data retrieval process. During the retrieval process, the selection criteria that you configured is applied. This enables you to narrow the focus of the data retrieval process to only the message data that you want to work with. A very effective means of isolating different messages in a Data Retrieval Session, including those that have specific characteristics, consists of using a **Session Filter** to retrieve only the type of message data that you choose, while blocking all data that does not specifically meet your designated filtering criteria. Other aspects of data selection in a Data Retrieval Session consist of the following:  
  
-   Specifying the input file configuration with the use of check marks on the files in the files list of the **New Session** dialog, to select specific data from chosen files only.  
  
-   Adding a **Time Filter** that selects data according to the window of time you specify with the **Time Filter** controls in the **New Session** dialog.  
  
-   Choosing a **Parsing Level** that returns a set of messages that are constrained by the upper stack level to which Message Analyzer parses. This simultaneously creates a unique analysis perspective and focused message set, while improving performance by removing all messages above the specified **Parsing Level**.  
  
-   Enabling the **Truncated Parsing** mode, which enforces a limited parsing set to deal with data files that contain truncated messages, for example, a .cap file. This also improves performance and creates a unique analysis perspective by returning headers only for message types that are limited to a pared-down parser set, as described in [Detecting and Supporting Message Truncation](detecting-and-supporting-message-truncation.md).  
  
 You might consider limiting data that you collect in a Data Retrieval Session by using a combination of a **Session Filter** and a **Time Filter**. For example, you could use a **Session Filter** to retrieve messages that transited a specified TCP port only and a **Time Filter** to limit the returned data to a particular window of time in which you suspect an issue is occurring with traffic on the specified port. The advantage of using a **Time Filter** with large data sets, such as you often have with log files, is that you can focus on specific subsets of data in order to reduce data loading time and to obtain better performance.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about how to select data from a Data Retrieval Session with a **Session Filter**, see [Applying a Session Filter to a Data Retrieval Session](applying-a-session-filter-to-a-data-retrieval-session.md).  
**To learn more** about how to select data from a Data Retrieval Session with a **Time Filter**, see [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).   
**To learn more** about how to choose the point in the stack up to which Message Analyzer will parse, see  [Specifying a Parsing Level](specifying-a-parsing-level.md).  
___________________\_  
  
## See Also  
 [Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md)   
 [Managing Session Filters](managing-session-filters.md)