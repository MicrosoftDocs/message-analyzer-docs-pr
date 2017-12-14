---
title: "Decrypting Input Data | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 8bad29df-0ba6-4c94-8386-451522889cc8
caps.latest.revision: 10
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Decrypting Input Data
Message Analyzer enables you to decrypt the messages in saved trace files from protocols that use the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) encryption protocols, which includes HTTP and the Remote Desktop Protocol (RDP). However, to enable the Message Analyzer **Decryption** feature to decrypt messages in any particular saved trace, you will need to import an applicable server certificate into the Message Analyzer certificate store and specify a required password.  
  
 For further information about Message Analyzer decryption capabilities, which includes decrypting live traces, see [Decrypting TLS and SSL Encrypted Data](decrypting-tls-and-ssl-encrypted-data.md).