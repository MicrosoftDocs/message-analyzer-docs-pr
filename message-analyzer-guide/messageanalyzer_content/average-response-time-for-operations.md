---
title: "Average Response Time for Operations | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bdf94bc3-de5c-4366-8f4d-a1f0757a3872
caps.latest.revision: 17
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Average Response Time for Operations
The **Average Response Times for Operations** viewer **Layout** for **Charts** provides a horizontal **Bar** element visualizer component to display the average response time  that is calculated across all instances of  specific methods or commands  of the same type that are detected in a set of trace results, that is, for protocols that make use of request/response pairs. For example, an HTTP GET or POST method is a request message  that is sent by a client to a web server, where the client awaits a response from the web server. When a response is received, Message Analyzer encapsulates the request and response messages in an Operation node that displays as a top-level message row in the **Analysis Grid** viewer. The **Average Response Time** is calculated as the average time it took for all request  messages in a set of trace results to receive the first server response.  
  
<a name="BKMK_ResponseTime"></a>   
## Understanding the Average Response Time  
 The **ResponseTime** annotation from **Field Chooser** enables you to measure the difference between the time that a Request message was sent by the client to a particular server and the first Response message received by the client from the server. Therefore, the **Average ResponseTime** indicated by a bar element for a specific method or command provides an average value that tells you how long a particular server is taking to reply to requests. Because the bar graph data is sorted from the longest to the shortest average response times, you can quickly ascertain from the upper rows of data which requests are taking the longest time to get a response for a particular method or command, possibly pointing to server performance problems. The **Average Response Time** that is associated with each method or command is also specified on the right side of the bar graph as a percentage value that is relative to the total response time for all Operation messages in a trace. This percentage value can also provide a quick indication of which server/s are taking the longest time to respond. With this information, you can focus your troubleshooting efforts on performance of the server  that is sending response messages  to the client.  
  
 To determine which server may be having performance problems, you might be able to isolate that information through filtering. For example, for  HTTP GET methods that are reporting a long average response time, you might apply a view  **Filter** to the **Analysis Grid** viewer such as `HTTP.Method == "GET"` to isolate the Operations that contain the HTTP requests. You can then add  the **ResponseTime** annotation from the **GlobalAnnotations** node in **Field Chooser**  as a new column in the **Analysis Grid** viewer, from where you can correlate the high response time values with the IP address of the web server in the **Destination** column. You might perform a similar filtering operation for an `SMB2.ComNegotiate` request message to a file server.  
  
## See Also  
 [Average Elapsed Time for Operations](../messageanalyzer_content/average-elapsed-time-for-operations.md)