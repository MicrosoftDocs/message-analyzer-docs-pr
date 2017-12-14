---
title: "Viewing OPN Source Code | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 421afc43-160b-47da-af77-596b4f5d706f
caps.latest.revision: 38
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Viewing OPN Source Code
Message Analyzer provides a definition viewer that displays Open Protocol Notation (OPN) description code for message modules that display in the **Analysis Grid** viewer and for most fields that display in the **Details** **Tool Window**. After you load data from a native Message Analyzer trace file or after you stop a Live Trace Session, you can view the OPN definition for most message fields, although there are exceptions such as CSV/TSV and some text-based log files for which there might be no OPN definitions. This feature is primarily intended to help developers or other interested users to understand more about OPN descriptions and their use as message parsers.  
  
## Working with OPN Definition Data  
 You can display the OPN definition viewer as a separate tab in an Analysis Session by right-clicking a message in the **Analysis Grid** viewer, a field in the **Details** window, or a field in **Field Chooser** **Tool Window**, and thereafter selecting the **Go To 'fieldName' Definition** command to show the OPN viewer and the OPN definition for the associated field or module. Only when you open the OPN definition viewer from the **Analysis Grid** or the **Details** window is an *entityName* designation included in single quotation marks in the **Go To Definition** command; otherwise it is absent. This designation corresponds to the module or field name that is associated with the message row or field row that you right-click, respectively. The entityName will therefore be identified by a message type in the **Module** column of the **Analysis Grid** viewer or by a field **Name** in the **Details** window. After you perform this action, the OPN definition viewer displays the read-only OPN code that defines the associated module or message field you selected.  
  
 Within the OPN definition viewer, there are several commands that you can access by right-clicking any location inside the viewer window. These commands and the actions they perform are described as follows:  
  
-   **Find** — displays a search control bar that enables you to enter text characters that you want to search for in the OPN code.  
  
     As soon as the OPN viewer is open, a search control bar displays with the selected field information. You can then use the forward and backward arrow keys to search through the OPN code in the direction you specify for occurrences of the search characters. The search control bar also provides check box options for **Match case**, **Match whole words**, and **Use regular expressions** in a drop-down, which establishes the indicated criteria for the search. If you want to search for another entity in the displayed definition, simply  type the entity name while the default search characters are highlighted and then use the search arrow keys in the control to locate any occurrences of the entity.  
  
-   **Search on Web** — enables you to search on the web for a highlighted string of characters that you selected.  
  
-   **Search in Microsoft Protocol Documentation** — enables you to search for protocol-related information in the [Windows Protocols](http://go.microsoft.com/fwlink/?LinkId=233157) documentation in the MSDN Library or other locations on the web.  
  
     For example, you might search for the specification of a particular protocol such as AIPS.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about OPN, see the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx).  
___________________\_