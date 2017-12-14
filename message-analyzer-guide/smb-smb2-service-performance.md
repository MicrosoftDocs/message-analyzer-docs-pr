---
title: "SMB-SMB2 Service Performance | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 142e60b0-6900-4543-94ad-25342e57d849
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# SMB-SMB2 Service Performance
The **SMB/SMB2 Service Performance** view **Layout** for **Charts** provides a summary of the top SMB command types in a set of trace results, the number of calls made by each command, along with the minimum, average, and maximum values for the service response time and elapsed time for each command. The summary information is provided as tabular data in the grid visualizer format  and contains the following columns of information:  
  
-   **Type** — specifies the SMB/SMB2 command type by name, for example `SMB2.VirtualOperations.Create`.  
  
-   **Calls** — specifies the number of calls made by each SMB/SMB2 command type.  
  
-   **Avg SRT** — averages the **ResponseTime** across all calls made by each different command type, for example `SMB2.VirtualOperations.Read`, `SMB2.VirtualOperations.Write`, and so on.  
  
     The service response time (SRT) is the time differential between an SMB request sent to a server and the first server response to that request, as measured by the **ResponseTime** global annotation that is found in **Field Chooser**. A long SRT can be an indication of a slowly responding server application.  
  
-   **Min SRT** — indicates the minimum response time detected across all calls made by each different command type.  
  
-   **Max SRT** — indicates the maximum response time detected across all calls made by each different command type  
  
-   **Avg Elapsed Time** — averages the elapsed time across all calls made by each different command type, for example, `SMB2.VirtualOperations.Close`, `SMB2.VirtualOperations.QueryInfo`, and so on.  
  
     The elapsed time is the time differential between an SMB request sent to a server and the last response to that request, which signals that all message fragments associated with the operation have been received by the requesting computer. A relatively long elapsed time value for an operation can be an indication of possible network latency issues.  
  
-   **Min Elapsed** — indicates the minimum elapsed time detected across all calls made by each different command type.  
  
-   **Max Elapsed** — indicates the maximum elapsed time detected across all calls made by each different command type  
  
## Using the SMB/SMB2 Service Performance Layout  
 To maximize the use of the **SMB/SMB2 Service Performance** view **Layout**, the **SMB/SMB2** **Viewpoint** is set by default for this **Layout** in the **Viewpoints** drop-down list on the Filtering toolbar. This enables you to view your data from the perspective of the SMB/SMB2 protocol with no layers above it. This also helps you to further isolate the SMB/SMB2 command data  along with the associated service response time and elapsed time values, which can provide the previously specified troubleshooting indications.