---
title: "Naming Saved Files | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee403bf6-98f6-4feb-ad7a-1f6ce78fe006
caps.latest.revision: 19
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Naming Saved Files

When saving trace data in one of the Message Analyzer native file formats, you are advised to consider file naming conventions. The following elements can be represented in saved message data and can therefore impact how you name the file:  
  
-   The stack level at which you ran a trace or the **Trace Scenario** you used.  
  
-   The provider/s and/or provider settings you specified in the session configuration.  
  
-   The session filter or other filters you applied when capturing or loading data.  
  
-   The name you specified for the session.  
  
-   The type of data being displayed or aggregated, such as trace data or logs, respectively.  
  
-   The way in which you processed or analyzed the data, for example, the filtering you applied to your trace results, or the resulting data set configuration.  
  
-   The data viewers you employed.  
  
-   The problem you solved.  
  
## File Naming and Searchability  

 Considering the variability of these factors, the content of each saved message file is almost certain to be unique. Therefore, the name of any message file that you save should be representative of its unique content, to facilitate ease of recognition when you revisit the data at a future time, or when reviewers, decision makers, and other colleagues view it for the first time. You can also apply the same principles when naming new sessions.  
  
 If you have a well thought-out file naming strategy, it can simplify your work and save time. For example, if you are importing a large number of files that display in the files list of a Data Retrieval Session, you can quickly locate and select specific files containing data that you want to load by specifying characters, in the search box on the toolbar of the **Files** tab in the **New Session** dialog, that are unique to the file names or the directory in which the files are located. For instance, you could search for all files or directories containing the characters “SMB2 Query Info”. The search then highlights all files and directories containing those characters and you can then select only those files from which to load data. This feature enables you to select any single file or group of files, in any combination, that contain the data you want to analyze following the data loading process.  
  
 Note that a Data Retrieval Session might contain data from multiple input files, so the file name under which you save the data should not necessarily reflect the name of any one file. Also, the file name under which you save data and the default session name of a Data Retrieval Session or Live Trace Session can be different.