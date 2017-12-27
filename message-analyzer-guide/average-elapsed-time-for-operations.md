---
title: "Average Elapsed Time for Operations | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8abfe23-01d6-47ba-a136-e06d1a4a52fa
caps.latest.revision: 19
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Average Elapsed Time for Operations

The **Average Elapsed Times for Operations** viewer **Layout** for **Charts** provides a horizontal **Bar** element visualizer component to display  the average elapsed time for Operations  that is calculated across all instances of  specific methods or commands  of the same type that are detected in a set of trace results, that is, for protocols that make use of request/response pairs. For example, an HTTP GET or POST method is a request message  that is sent by a client to a web server, where the client awaits a response from the web server. When a response is received, Message Analyzer encapsulates the request and response messages in an Operation node that displays as a top level message row in the **Analysis Grid** viewer. The Average Elapsed Time is calculated as the average time it took for all request messages in a set of trace results to receive the *first* server response, plus the time it took to receive all message fragments associated with the server response messages.  
  
## Understanding the Average Elapsed Time  

 The **Average Elapsed Time** for each method or command detected in a set of trace results measures the difference between the time that a  Request method was sent by the client to a particular server and the time at which the last message fragment associated with the Request was received by the client. Therefore, the elapsed time indicated by a bar element for a specific method or command provides an average value that may indicate when there are network latency issues, providing that server **Average Response Times** are clearly low values (which generally rule out slow server responses). Because the bar graph data is sorted from the longest to the shortest average elapsed times, you can quickly ascertain from this data whether network issues are impacting performance. The Average Elapsed Time for each method or command is specified on the left side of the bar graph, while on the right side there is a percentage value for each method or command that is relative to the total elapsed time for all the methods or commands in the trace. This can provide a quick indication of which methods or commands are taking the longest time to complete transmission of all related data. With this information, you might focus your troubleshooting efforts on network performance.  
  
 Note that the Average Elapsed Time values depicted in the **Average Elapsed Times for Operations** viewer **Layout** are the same as the values in the **TimeElapsed** column of the **Analysis Grid** viewer.  
  
> [!NOTE]
>  You can double-click any bar element in either of the graphs in this viewer and display the associated messages for each method or command in a separate **Analysis Grid** viewer instance for further analysis.  
  
## See Also  

- [Average Response Time for Operations](average-response-time-for-operations.md)