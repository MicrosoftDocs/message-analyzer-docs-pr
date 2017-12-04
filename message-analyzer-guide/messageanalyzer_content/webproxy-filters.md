---
title: "WebProxy Filters | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08f306cf-082c-4451-ba55-33fe73a1147b
caps.latest.revision: 26
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# WebProxy Filters
The **Microsoft-Pef-WebProxy** provider has two filters for which you can set values. The purpose of these filters is to isolate specific traffic and optimize Message Analyzer capture performance. An option is also provided that enables you to specify a client certificate file that Fiddler will provide in a given session to a site server that requires certification validation. After you open the **New Session** dialog from the Message Analyzer **File** menu and select the **Pre-Encryption for HTTPS** **Trace Scenario** from the **Select a trace scenario** drop-down in the dialog, you can configure the following settings on the **Provider** tab of the **Advanced Settings – Microsoft-Pef-WebProxy** dialog (access by clicking the **Microsoft-Pef-WebProxy** provider **Configure** link to the right of the provider **Id** in the **New Session** dialog):  
  
-   **Hostname Filter** — enables you to filter HTTP messages to and from a specific host, by specifying the host name in a format similar to the following:  
  
     *www.xxxxx.com*  
  
     This filter restricts the capture of HTTP operations initiated by the client browser to requests and responses to and from a single web host. You might set such a filter when troubleshooting communications from a poorly performing web server in cases where you need to isolate messages sent to and received from that server only.  
  
-   **Port Filter** — enables you to filter traffic to a specific port, such as 80, 443, 8080, and so on, by specifying a port value in integer format, similar to the following:  
  
     *443*  
  
     You might use such a filter to limit the traffic you capture to HTTPS operations only, so you can isolate and troubleshoot both requests from the client browser and responses from the server that were intended to be encrypted.  
  
    > [!NOTE]
    >  For maximum positive impact on HTTP capture performance, you should set both of the specified filters to appropriate values.  
  
-   **HTTPS Client Certificate** — enables you to specify a certificate file (\*.cer) that Fiddler will provide in a given session to a server that requires certification validation. This is because in some scenarios, Fiddler must act as the proxy that provides the security certificate. You will need to specify  the path to the certificate file in the **HTTPS Client Certificate** text box.  
  
 Other settings that you can specify  on the **Provider** tab of the **Advanced Settings – Microsoft-Pef-WebProxy** dialog consist of the following:  
  
-   **Reuse Client Connections** — given that Fiddler is a proxy, when it creates HTTP client connections on behalf of Internet Explorer or another browser,  it will keep these connections alive for reuse to more speedily expedite client HTTP requests, rather than keep creating new ones and incurring the accompanying degradation to performance.  
  
-   **Reuse Server Connections** — the same as the above, only as applied to HTTP server connections.