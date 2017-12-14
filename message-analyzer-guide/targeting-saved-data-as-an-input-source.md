---
title: "Targeting Saved Data as an Input Source | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88a7d58a-9a82-48f4-9f95-1fe9e207e775
caps.latest.revision: 40
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Targeting Saved Data as an Input Source
From a Data Retrieval Session, you can locate saved data files and build a message collection that contains the data you want to target for input to Message Analyzer. The fastest way to access the configuration for a Data Retrieval Session is to click the **New Session** button on the Message Analyzer **Start** page to display the **New Session** dialog. To begin configuration for a Data Retrieval Session, click the **Files** button under **Add Data Source** in the **New Session** dialog. From the **Files** tab of the **New Session** dialog, you can target the files that contain the saved data you want to load into Message Analyzer. You can then customize your session configuration with the use of various features to optimize Message Analyzer performance in the data retrieval process.  
  
---  
  
 **More Information**   
 **To learn more** about the input file types that Message Analyzer supports, see [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md).   
---  
  
## Optimizing Data Retrieval  
 By selecting specific input files, specifying a **Session Filter**, and/or configuring a **Time Filter**, you can limit the data that is retrieved, so that smaller, more targeted message sets can be extracted from sources containing high volumes of data. This optimizes the data retrieval process because it results in the following:  
  
-   More manageable data sets that focus only on specific data, optionally in a configurable window of time.  
  
-   Better performance when loading message data.  
  
-   More effective data analysis.  
  
-   A focused set of messages that expedites the analysis process for others with whom you are sharing your results.  
  
 You can also optimize performance and target specific data to be retrieved by using the **Truncated Parsing** feature to detect input files that contain truncated messages and cause Message Analyzer to apply a pared-down parser set that reduces data loading time. Another feature that you can use to significantly improve performance is to set a **Parsing Level** to limit how far up the message stack Message Analyzer will parse.  
  
## Creating a Data Retrieval Session  
 For a general workflow that you can follow to create a Data Retrieval Session, see  [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md). This section also contains subtopics that describe the various features and functions that you can use to create and start a Data Retrieval Session.