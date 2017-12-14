---
title: "Configuring Time Format Settings | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 23842612-8a43-4475-b948-cfaa1b3af79b
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Configuring Time Format Settings
For the data viewers that display date-time values, Message Analyzer utilizes the standard ISO format for consistency throughout the user interface (UI). For example, the same date-time format that displays in the **Analysis Grid** viewer will also display in the **Pattern Match** viewer, in addition to the **Time Filter** dialog in Live Trace Session results and in the **Time Filter** pane of a Data Retrieval Session.  However, Message Analyzer enables you to change how time data displays by providing you with the option to show either the date and time, or the time only.  Configuration settings for these formats are available from the following locations:  
  
-   **Options dialog** — this dialog is accessible from the global Message Analyzer **Tools** menu. The dialog exposes the **Time Display** pane on the **Display** tab, from where you can specify date and time configuration settings that include **Show Date And Time** and **Show Time Only** options, along with a **Time Zone** drop-down list that enables you to set your locale. Specifying the date and time configuration settings from this location has global scope that overrides any previously set configuration.  Note that by default, your local time zone is automatically set in the **Time Zone** drop-down list when you start Message Analyzer and will remain that way until you manually change it.  
  
-   **Analysis Grid Timestamp column context menu** — right-click the **Timestamp** column header in the **Analysis Grid** viewer to display a context menu that enables you to toggle the date and time configuration settings between **Show Time Only** and **Show Date and Time**; note that the latter is the default. Only one of these commands will display at any time, depending on the current configuration setting. Setting one of these commands from the **Timestamp** column context menu also has global scope and overrides any previously set configuration.  
  
 You can set the time locale as the reference time zone for all Data Retrieval and Live Trace Sessions, to achieve a time zone perspective that enables you to view time information based on where your data was captured. This makes it convenient to analyze data based on the perspective of a particular time zone. Also, by setting the time configuration to **Show Time Only**, you can condense the time value display and recover some UI display space in the **Timestamp** column and other viewers.  
  
> [!NOTE]
>  Although you might set the time display configuration to **Show Time Only**, you will still need to specify a full date and time value when you configure a `#Timestamp` filter, for example, when specifying a **Session Filter** or view **Filter**.  
  
## See Also  
 [Setting Message Analyzer Global Options](setting-message-analyzer-global-options.md)