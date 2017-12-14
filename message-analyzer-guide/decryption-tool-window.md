---
title: "Decryption Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc6809ef-f188-4566-a2e1-59b18d6de90a
caps.latest.revision: 16
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Decryption Tool Window
The Message Analyzer **Decryption** feature enables you to view messages that are encrypted with the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols, for example, messages from the HTTP and Remote Desktop (RDP) protocols. To decrypt messages that were captured on a specific server, Message Analyzer requires a valid certificate and password for such a server. Also, you must provide these to Message Analyzer prior to loading data from saved input files through a Data Retrieval Session or before running a Live Trace Session that you expect to contain messages that you want to target for decryption. Thereafter, Message Analyzer can decrypt those messages by using the server certificate and password that you provided. To view the results of a decryption session, you will use the **Decryption** **Tool Window**.  
  
## Displaying Decryption Data  
 To display the **Decryption** window, select the **Decryption** item in the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu. The **Decryption** window is a session-specific, interactive, and dockable window that simplifies the means of locating and analyzing decrypted messages that might typically be hard to find in a large trace. The **Decryption** window is session-specific because the data it displays is driven by session selection; for example, this might mean selecting an **Analysis Grid** viewer session tab, as described in [Data Viewer Concepts](data-viewer-concepts.md). Moreover, if you have decrypted data in an **Analysis Grid** viewer session tab and you select it, the **Decryption** window displays summary data for the selected decryption session. If you have multiple sessions that have decrypted data, selecting a viewer tab for any of them causes the **Decryption** window to snap to the selected session data. This enables you to have quick access to comprehensive decryption information for each decrypted conversation in the selected session.  
  
## Assessing Decryption Session Results  
 In the **Decryption** window, a separate row displays for each message that Message Analyzer attempted to decrypt and status information for each message is also provided to enable you to quickly assess the results of a decryption session. Selection of a message row in the **Decryption** window automatically selects that message in the **Analysis Grid** viewer. This also causes field data in the **Details** **Tool Window**, hexadecimal data in the **Message Data** **Tool Window**, and message layer data in the **Message Stack** **Tool Window** to snap-to the selection, provided that such **Tool Windows** are displayed. This interactive display of associated data immediately provides you with the diagnostic and analysis perspectives by which you can accurately assess your decrypted messages and the supporting origins stack.  
  
---  
  
 **More Information**   
 **To learn more** about the decryption session status information that is provided in the **Decryption** window, see [Analyzing Decryption Session Data](decrypting-tls-and-ssl-encrypted-data.md#BKMK_AnalyzeDecryptData).   
---  
  
## See Also  
 [Decrypting TLS and SSL Encrypted Data](decrypting-tls-and-ssl-encrypted-data.md)