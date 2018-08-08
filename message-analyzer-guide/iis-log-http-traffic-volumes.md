---
title: "IIS Log HTTP Traffic  Volumes | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1518790e-4a0c-4965-bd94-45c92c4b8978
caps.latest.revision: 22
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# IIS Log HTTP Traffic  Volumes

The **IIS Log HTTP Traffic Volumes** view **Layout** for **Charts** enables you to obtain a high-level summary view of  specific data from an IIS log file that depicts the relative distribution of HTTP traffic volume in bytes, from the highest to the lowest volume, for the cumulative IIS server responses to each client query that the server received. The **Layout** uses a **Bar** element visualizer component that provides a Y-axis label next to each bar element to display the IP address of an IIS server and the uniform resource identifier (URI) query made to the server from an HTTP  client. Each horizontal graphic bar element in this **Layout** shows the cumulative HTTP traffic volume in bytes for all server responses associated with a particular query made by a client browser or other query source. The volume values in this **Layout** are based on the **sc_bytes** field for server responses, the values for which you can view in the **Details** **Tool Window** after selecting a log entry in the **Analysis Grid** viewer.  
  
> [!NOTE]
>  An IIS.log file will be parsed only if you select the **IIS** configuration file in the **Text Log Configuration** drop-down list of the **New Session** dialog for a Data Retrieval Session prior to loading the data into Message Analyzer. Otherwise, no data will display in the **IIS Log HTTP Traffic Volumes** view **Layout**.  
> 
> 
> 
>  **More Information**   
>  **To learn more** about working with text-based .log files, see [Opening Text Log Files](opening-text-log-files.md).  

## Using the IIS Log HTTP Traffic Volumes Layout  

 This **Layout** provides a quick summary of the total server response volumes in bytes that are associated with client queries requesting access to IIS server resources and services. It enables you to see at-a-glance which client queries are driving high byte volume responses from an IIS server, which may point to areas that need further investigation. For example, very high byte volume server responses could be an indication of the potential overload of an IIS server, especially if a higher than expected number of server responses are needed to service client queries.  
  
 **Interactive Analysis**   
This **Layout** for the **Chart** viewer is intended to work with the **IIS** **Layout** for the **Analysis Grid** viewer and the **IIS** **Layout** for the **Grouping** viewer to create an integrated and interactive analysis environment. You will be able to correlate the data most effectively if you have these viewers and **Layouts** displayed. Note that these viewers and **Layouts** are configured in the **IIS Logs** **Profile** and will display after you  load data from an IIS.log file, provided that you enabled this **Profile** on the **Profiles** tab of the **Options** dialog (accessible from the global Message Analyzer **Tools** menu).  
  
 As an example of interactively driving the display of messages, if you select any **c_ip** group  in the **Grouping** viewer, you can display all the messages associated with a particular client IP address in the **Analysis Grid** viewer for further analysis and message **Details**. In addition, each Group selection that you make in the **Grouping** viewer filters the display of messages in the **IIS Log HTTP Traffic Volumes** view **Layout** for **Charts** to create a focused context for analysis.  
  
---  
  
 **More Information**   
 **To learn more** about interactively analyzing IIS log data with the indicated viewing and **Layout** configurations, see the following topics:  
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md) — see the **IIS** **Layout** in this topic.  
[Grouping Viewer](grouping-viewer.md) — see the **IIS** **Layout** in this topic.  
[Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) — see the **IIS Logs** **Profile** in the table of this topic to review a related usage scenario and analysis example and to learn how to manually display the **Grouping** and **Chart** viewers with the **Layouts** defined in this **Profile**.  

---