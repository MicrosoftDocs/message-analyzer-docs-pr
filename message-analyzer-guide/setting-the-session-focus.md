---
title: "Setting the Session Focus | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf93334e-ded1-4b9b-86ac-c4ac37c87e09
caps.latest.revision: 12
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Setting the Session Focus

This section describes  various high-level settings that you can specify for a Live Trace Session that alter the overall focus of the  session. Although low-level provider filter settings can create the focus on capturing specific messages, you have the option to specify several high-level settings that can further refine the focus of data capture, improve the efficiency of data capture mechanisms, and specify how you will view results. For example, by selecting  a high-level **Session Filter** or a **Parsing Level**, you can refine the session focus by specifying the type of data you want to capture, or inversely, the traffic you want Message Analyzer to ignore by filtering it out.  
  
 However, before you specify either of these filtering elements, you might want to ensure that you do not have any low-level provider filter settings that conflict with the high-level filter settings that you specify. Another thing to consider is that low-level provider filters  such as **Fast Filters**, **WFP Layer Set** filters, and event **Keyword** bitmask filters are all typically highly performant filters that consume less system resources, while a **Session Filter** requires additional parsing time. On the other hand, by setting a **Parsing Level** that limits the upper layer to which Message Analyzer will parse messages, you  can also realize performance improvements. Moreover, when specifying a **Session Filter**, you can take advantage of numerous built-in Filter Expressions that provide a wide variety of functionality and you can easily change or remove the effects of a **Session Filter** to facilitate different analysis perspectives.  
  
 You can also specify several advanced settings to optimize the underlying ETW Session in which Message Analyzer captures events. Other session-level configuration that you can perform is the setup for decrypting TLS- and SSL-encrypted messages. Lastly, you have the option to set the focus in which you will view the session results data, by choosing one of the  default data viewers  prior to starting a Live Trace Session.  
  
 These discussions are covered in the following subtopics:  
  
[Selecting Data to Capture](selecting-data-to-capture.md)   
[Specifying Advanced ETW Session Configuration Settings]pecifying-advanced-etw-session-configuration-settings.md)   
[Decrypting TLS and SSL Encrypted Data](decrypting-tls-and-ssl-encrypted-data.md)   
[Selecting a Session Data Viewer](selecting-a-session-data-viewer.md)  
  
## See Also  

[Modifying Default Provider Settings](modifying-default-provider-settings.md)