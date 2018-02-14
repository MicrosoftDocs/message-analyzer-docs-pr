---
title: "IIS Log Top URI Bytes | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e4607ef-659d-45f7-962e-5ecc8ee0c4f6
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# IIS Log Top URI Bytes

The **IIS Log Top URI Bytes** view **Layout** for **Charts** enables you to obtain a high-level summary view of  specific data from an IIS log file that depicts the relative distribution of cumulative IIS server response volume in bytes, from the highest to the lowest volume, for each client query requesting resources or services from an IIS server. The **Layout** uses a **Bar** element visualizer component that provides a Y-axis label next to each bar element to display the uniform resource identifier (URI) query made by an HTTP client to the server. Each horizontal graphic bar element in this **Layout** shows the cumulative volume in bytes for all the server responses associated with a particular query made by a client browser or other query source. The volume values in this **Layout** are based on the **sc_bytes** field for server responses, the values for which you can view in the **Details** **Tool Window** after selecting an IIS log entry in the **Analysis Grid** viewer.  
  
## Using the IIS Log Top URI Bytes Layout  

 This **Layout** provides a quick summary of the total server response volumes in bytes for each client query that  requests access to IIS server resources and services. It enables you to see at-a-glance which client queries are driving high byte volume responses from an IIS server, which may point to areas that need further investigation. For example, very high byte volume server responses could be an indication of the potential overload of an IIS server, especially if a higher than expected number of server responses are needed to service client queries.  
  
 Along with the **IIS Log Top URI Bytes** view **Layout** for **Charts**, you might also consider using the **Grouping** viewer with the **IIS** **Layout** and the **Analysis Grid** viewer with the **IIS** **Layout** to achieve an integrated and interactive analysis context that can significantly enhance your analysis process.  
  
## See Also  

[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)   
[Grouping Viewer](grouping-viewer.md)   
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)