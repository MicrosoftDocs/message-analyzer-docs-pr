---
title: "Field Data Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52ce6375-3846-4c18-9639-17747b797a47
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Field Data Tool Window

The **Field Data** **Tool Window** is a field-specific and dockable window that is interactively driven by field selection in the **Details** **Tool Window**, which is in turn driven by message selection in the **Analysis Grid** and other data viewers. Interaction between the **Analysis Grid** viewer and the **Details** and **Field Data** windows occurs only within the context of individual sessions, rather than across different sessions.  
  
## Displaying Field Data  

 In most cases, the **Field Data** window reproduces the value of a selected field that is specified in the **Value** column of the **Details** window, which could be a string, numerical, binary, or other value. For example, if you select a field in the **Details** window for a TCP message that is selected in the **Analysis Grid** viewer, the value of that field also displays in the **Field Data** window. In cases where the information is reproduced, the **Field Data** window will indicate that there is “*No alternate presentation available*” for these fields.  
  
 However, there are some cases where more complex field information can display in the **Field Data** window. This can enable you to very quickly assess the type of payload data a message is carrying. For instance, if you select a TCP message in the **Analysis Grid** viewer and the **Payload** field in the **Details** window, the **Field Data** window usually displays information in text/plain format. If the TCP payload is an HTTP message, then the **Field Data** window might display HTML fragments. Moreover, if you select the **Payload** field in the **Details** window for an HTTP message selected in the **Analysis Grid** viewer, the **Field Data** window might display formats that include the following: text/html, text/css, font/eot, application/x-javascript, text/javascript, and application/json; or different media formats such as image/gif, image/jpeg, image/png, image/bmp, and so on. Also, XML is another format that can display in the **Field Data** window.  
  
> [!NOTE]
>  The **Field Data** window indicates the data format or presentation type by displaying a label value in the lower-left corner of the window.  
  
<a name="BKMK_DecodingURLs"></a>   
## Decoding URLs  
 The **Field Data** window now provides decoding of URLs by removing the special encoding characters from any URL string. For example, when you select the **Uri** field in the **Details** window for an HTTP message, the **Field Data** window displays an upper section named **Actual Value** and a lower section named **Decoded Value**. The latter section shows the decoded value of the **Uri** with the encoding characters removed, while the original value of the **Uri** is retained in the **Actual Value** section. A typical result might be that all **Uri** spacing characters such as "%20" are removed.  
  
## Correlating Field Details  

 You can also correlate the hexadecimal details for most fields selected in the **Details** window with the values displayed in the **Field Data** window, by observing them in the **Message Data** **Tool Window**. For example, to view the hexadecimal details for a TCP **Payload** field value that is displaying in the **Field Data** window, click the **Message Data** tab.  
  
## Working With the Field Data Tool Window  

 If the **Field Data** window is no longer displaying, you can redisplay it by selecting the **Field Data** item in the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu. You can also undock and reposition the **Field Data** window by taking advantage of the docking navigation control that displays after you drag the **Field Data** window by its tab away from its default docking location. You might do this to move the **Field Data** window adjacent to another **Tool Window** or data viewer with which you are working, to enhance your data analysis perspectives.  
  
 After the **Field Data** window is displayed, you can use it in the previously specified manner. When data is displaying in this window, you can select the following right-click context menu items to perform the indicated tasks:  
  
-   **Save Text As …** — Message Analyzer interprets the type of field data displaying in the **Field Data** window and causes the **Save As** dialog to open with a file extension specification that correlates with the interpreted data type. For example, if the displaying field data is **text/html**, the **Save As** dialog opens with the **Save as type** drop-down selection set to **HTML Files (\*.html)**.  
  
-   **Open in Default Application** — Message Analyzer interprets the type of field data displaying in the **Field Data** window and causes a default application to open for the associated type of field data. For example, if the displaying field data is indicated as **text/css**, the default HTML editor on your system opens, such as SharePoint Designer or Expression Web, to enable you to save the data in that application.  
  
-   **Copy Text** — enables you to simply copy the text to the Clipboard for further processing.