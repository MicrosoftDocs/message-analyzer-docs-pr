---
title: "IIS Log Top URIs by Time | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0218e8dd-db11-4212-b85f-0f31e8510359
caps.latest.revision: 14
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
description: "Discover IIS Log Top URIs by Time: Analyze server response times, identify potential overload & network latency issues. Improve your IIS server performance."
---

# IIS Log Top URIs by Time

The **IIS Log Top URIs by Time** view **Layout** for **Charts** enables you to obtain a high-level summary view of  specific data from an IIS log file that depicts the relative distribution of the average time in milliseconds (ms), from the highest to the lowest average time, that an IIS server took to service each client query requesting resources from it. The **Layout** uses a **Bar** element visualizer component that provides a Y-axis label next to each bar element to display the uniform resource identifier (URI) query made by an HTTP client to the server. Each horizontal graphic bar element in this **Layout** shows the average service time (ms) of all the server responses associated with a particular query made by a client browser or other query source. The time values in this **Layout** are based on the **time_taken** field for server responses, the values for which you can view in the **Details** **Tool Window** after selecting an IIS log entry in the **Analysis Grid** viewer.  
  
## Using the IIS Log Top URIs by Time Layout  

 This **Layout** provides a quick summary of the average time it took for an IIS server to service each client query that  requested access to its resources and services. It enables you to see at-a-glance which client queries took the longest to be serviced, which may point to areas that need further investigation. For example, very high average service times could be an indication of the potential overload of an IIS server, or possibly network latency issues when servicing client queries.  
  
 Along with the **IIS Log Top URIs by Time** view **Layout** for **Charts**, you might also consider using the **Grouping** viewer with the **IIS** **Layout** and the **Analysis Grid** viewer with the **IIS** **Layout** to achieve an integrated and interactive analysis context that can significantly enhance your analysis process.  
  
## See Also  

[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)   
[Grouping Viewer](grouping-viewer.md)   
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)