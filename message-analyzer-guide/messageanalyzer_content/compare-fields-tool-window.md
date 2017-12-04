---
title: "Compare Fields Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 75b9525d-cc83-436a-a9e7-1b8bbc8cbac6
caps.latest.revision: 14
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Compare Fields Tool Window
Message Analyzer enables you to compare the field data of any two messages that you select in the **Analysis Grid** viewer for detailed analysis of field values. This functionality is provided in the **Compare Fields** **Tool Window**, which is a preview feature that you must enable on the **Features** tab of the **Options** dialog in order to use it.  After enabling this preview feature and restarting Message Analyzer, you can access it from the **Windows** submenu of the global Message Analyzer **Tools** menu.  
  
## Comparing Message Field Data  
 To begin, open the **Compare Fields** window from the **Windows** submenu as previously indicated, to display it in the lower right sector of the Message Analyzer user interface. Assuming that you have a set of trace results displaying in the **Analysis Grid** viewer, perform the following steps:  
  
1.  In the **Analysis Grid** viewer, select a message containing the fields that you want to compare with those of another message of the same type.  
  
2.  In the **Compare Fields** window, right-click anywhere in the window space and select the **Set Current as Baseline** command from the context menu that appears, to set the currently selected message fields and values as a reference in the window.  
  
     **Field** and **Baseline** columns with values derived from the selected baseline message appear in the **Compare Fields** window.  
  
3.  In the **Analysis Grid** viewer, select a second message of the same type which contains the fields that you want to compare in value to the baseline message fields.  
  
     A **Current** column with field values derived from the currently selected message appears in the **Compare Fields** window.  
  
4.  Scroll down through the data and note that fields in the **Current** column which contain values that are different from those in the **Baseline** column are highlighted in red, thus providing you with an instant evaluation of differences between message field values that could be critical to analysis.