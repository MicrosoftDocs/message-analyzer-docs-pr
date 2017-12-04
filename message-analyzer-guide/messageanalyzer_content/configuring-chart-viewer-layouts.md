---
title: "Configuring Chart Viewer Layouts | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f535d869-3afe-481b-8bf4-783b52bb67da
caps.latest.revision: 52
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Configuring Chart Viewer Layouts
The built-in   **Chart** viewer **Layouts** that are provided with Message Analyzer by default represent various ways to organize the display of data using any of the four data visualizer components that are available for **Layouts**. When configuring a custom **Layout** of your own design, the following constraints apply:  
  
-   You can use only one of the four types of graphic visualizer components in any one **Layout**.  
  
-   You can configure  one or more data  formulas for each **Layout**.  
  
-   You can only display data in your **Layout** based on message  fields that are available from the **Field Chooser** **Tool Window**, in addition to global **Annotations** and **Properties**.  
  
-   Any new **Layout** that you create must be modified from an existing **Layout** and saved with new metadata that you define, such as the **Layout** name, description, and category.  
  
 This section begins with a list of the built-in **Chart** viewer **Layouts** that are included with every Message Analyzer installation. You can edit any one of these **Layouts** and save it as a new custom **Layout** of your own that will appear in the **My Items** category of the **Chart**/**Layout** drop-down list that is accessible from the global Message Analyzer **Session** menu. You might navigate to the   topics in the lists and review some of the built-in **Layout** features to get an idea of the types of data  displays that you can create and how you can use them in analysis.  This section also provides a brief description of the graphic visualizer components that you can use in any custom **Layout** that you create, some background on how to choose a visualizer component for a custom **Chart** viewer **Layout** of your own, and a brief overview of configuring a custom **Layout**.  
  
<a name="BKMK_Charts"></a>   
## Built-In Chart Viewer Layouts  
 Message Analyzer provides numerous **Layouts** for the **Chart** viewer that are accessible from the  locations that follow. Note that each **Layout** in the drop-down lists that are described immediately below has an icon to the left of the **Layout** name that identifies the type of [graphic visualizer component](../messageanalyzer_content/configuring-chart-viewer-layouts.md#BKMK_VisualizerComponents) that it uses to display data.  
  
-   The **New Viewer** drop-down list on the global Message Analyzer toolbar. You can display an uncategorized  list of **Layouts** by clicking the **Chart** item in this drop-down list.  
  
-   The **Session Explorer** context menu, which is accessible by right-clicking anywhere in the **Session Explorer** **Tool Window**. You can then select the **New Viewer** item in the context menu, and in turn select **Charts** to display an uncategorized list of **Layouts**.  
  
-   In the  **Layout** drop-down list that is accessible from the global Message Analyzer **Session** menu. You can display the fully categorized list of **Layouts** by clicking the **Chart** item in the global Message Analyzer **Session** menu and then selecting **Layout**.  
  
> [!NOTE]
>  The  **Start With** drop-down list in the **New Session** dialog enables you to select a default **Chart** item for session startup that utilizes a **Bar** element visualizer component. See [Selecting a Session Data Viewer](../messageanalyzer_content/selecting-a-session-data-viewer.md) for further details.  
  
 **Subcategories for the Built-In Chart Viewer Layouts**   
The **Layout** list that you can access from the **Session** menu, as previously described, is organized into a top-level **Message Analyzer** category with various subcategories in which the **Chart** viewer **Layouts** appear. The subcategories in the following list contain the **Layout** names, which are each linked to the corresponding topic so that you review their functionality and analysis capabilities:  
  
-   **HTTP** subcategory **Layouts**:  
  
    -   [HTTP Content Type Payloads](../messageanalyzer_content/http-content-type-payloads.md)  
  
    -   [HTTP Content Type Volumes](../messageanalyzer_content/http-content-type-volumes.md)  
  
-   **General** subcategory **Layouts**  
  
    -   [Average Elapsed Time for Operations](../messageanalyzer_content/average-elapsed-time-for-operations.md)  
  
    -   [Average Response Time for Operations](../messageanalyzer_content/average-response-time-for-operations.md)  
  
    -   [Cluster Levels](../messageanalyzer_content/cluster-levels.md)  
  
    -   [Event Log IDs](../messageanalyzer_content/event-log-ids.md)  
  
    -   [IP/Ethernet Conversations by Message Count](../messageanalyzer_content/ip-ethernet-conversations-by-message-count.md)  
  
    -   [IP Ethernet Conversations by Message Count Top 20](../messageanalyzer_content/ip-ethernet-conversations-by-message-count-top-20.md)  
  
    -   [TCP/UDP Conversations by Message Count](../messageanalyzer_content/tcp-udp-conversations-by-message-count.md)  
  
    -   [TCP/UDP Conversations by Message Count Top 20](../messageanalyzer_content/tcp-udp-conversations-by-message-count-top-20.md)  
  
    -   [Top Level Protocols Message Count](../messageanalyzer_content/top-level-protocols-message-count.md)  
  
    -   [Top Level Protocols Message Count Over Time](../messageanalyzer_content/top-level-protocols-message-count-over-time.md)  
  
-   **Network** subcategory **Layouts**  
  
    -   [IIS Log HTTP Traffic  Volumes](../messageanalyzer_content/iis-log-http-traffic-volumes.md)  
  
    -   [IIS Log Server Bytes by Host over Time](../messageanalyzer_content/iis-log-server-bytes-by-host-over-time.md)  
  
    -   [IIS Log Top URI Bytes](../messageanalyzer_content/iis-log-top-uri-bytes.md)  
  
    -   [IIS Log Top URIs by Time](../messageanalyzer_content/iis-log-top-uris-by-time.md)  
  
    -   [TCP Rate and Diagnosis](../messageanalyzer_content/tcp-rate-and-diagnosis.md)  
  
    -   [TCP Stevens Graph](../messageanalyzer_content/tcp-stevens-graph.md)  
  
    -   [Top Talkers](../messageanalyzer_content/top-talkers.md)  
  
    -   [Top Talkers Top 20](../messageanalyzer_content/top-talkers-top-20.md)  
  
-   **NetLogon** subcategory **Layouts**  
  
    -   [Netlogon Message Types](../messageanalyzer_content/netlogon-message-types.md)  
  
-   **Networking** subcategory **Layouts**  
  
    -   [NTP Time Offset](../messageanalyzer_content/ntp-time-offset.md)  
  
-   **Common** subcategory **Layouts**  
  
    -   [Perfmon Log (.blg)](../messageanalyzer_content/perfmon-log-blg.md)  
  
-   **File Sharing** subcategory **Layouts**:  
  
    -   [SMB File Stats](../messageanalyzer_content/smb-file-stats.md)  
  
    -   [SMB Reads and Writes Bytes Sent](../messageanalyzer_content/smb-reads-and-writes-bytes-sent.md)  
  
    -   [SMB Reads and Writes Bytes/Second](../messageanalyzer_content/smb-reads-and-writes-bytes-second.md)  
  
    -   [SMB/SMB2 Service Performance](../messageanalyzer_content/smb-smb2-service-performance.md)  
  
    -   [SMB Top Commands](../messageanalyzer_content/smb-top-commands.md)  
  
    -   [SMB Top Talkers](../messageanalyzer_content/smb-top-talkers.md)  
  
    -   [SysLog Levels](../messageanalyzer_content/syslog-levels.md)  
  
<a name="BKMK_VisualizerComponents"></a>   
## Graphic Visualizer Components  
 Each of the built-in **Layouts** in the previous list use only one of the four different types of graphic data visualizer components that are available. You can also make use of any one of  these components when you are configuring a new **Layout** that organizes and presents data in a unique  format, which can include rendering top-level data summaries in **Bar** element, **Pie** slice, event **Timeline** graph, and **Table** format, as described in [Data Viewer Concepts](../messageanalyzer_content/data-viewer-concepts.md). Note that you can see all four of the available  visualizer components in use if you display the [Protocol Dashboard](../messageanalyzer_content/protocol-dashboard.md) viewer from the **Charts (Deprecated)** drop-down list, which is accessible from the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
 Many of  the **Chart** viewer **Layouts** are intended to work together with other data viewers to create an integrated and interactive analysis environment, as described in [Working With Message Analyzer Profiles](../messageanalyzer_content/working-with-message-analyzer-profiles.md). The interactive features of a **Layout** are initiated when you double-click the elements of a visualizer component that represents some message quantity or other value, for example, message volume, payload length, or some  other field value. This action results in interactively driving the display of the element messages into another viewer such as the **Analysis Grid** to create an analysis context that focuses on the element messages only. Note that all of the built-in **Chart** viewer **Layouts** are capable of interactively driving the display of messages in other viewers, whether or not they are configured in a Message Analyzer **Profile** which can be enabled or disabled.  
  
 The list that follows provides a brief description of the four types of visualizer components and the elements they contain that can interact with the **Analysis Grid** viewer and other viewers by double-clicking them, or in some instances by using a single-click.  
  
-   **Bar** element — contains bar elements that each represent a group of captured messages that have a common field, property, message type, or other entity to which a data manipulation formula has been applied. Double-click any single bar element to view the associated messages in a new instance of the **Analysis Grid** viewer.  
  
-   **Pie** slice — divided into slices or section elements that each represent a group of captured messages that have a common field, property, message type, or other entity to which a data manipulation formula has been applied. Double-click any single slice to view the associated messages in a new instance of the  **Analysis Grid** viewer.  
  
-   **Timeline** graph — displays an interconnected timeline element across trace boundaries for common properties, fields, values, or other entities that are contained in captured messages, to expose the points in time on the X-axis where those entities were sent and/or received, versus other values on the Y-axis that might represent the application of a particular formula, such as the **Count** of identical values for a particular field. Double-click a single timeline element or node to view the associated messages in a new instance of the **Analysis Grid** viewer.  
  
    > [!NOTE]
    >  The **Timeline** visualizer is enabled for zooming into chosen windows of time.  
  
-   **Table** grid — contains data row and column elements that you can organize to correlate values with entities such as message fields and properties, or formulas based on field and properties, for example the **Average** of a set of field values. Double-click a data row to view the associated messages in a new instance of the **Analysis Grid** viewer.  
  
## Choosing a Visualizer Component for a Custom Layout  
 When you are creating a custom **Chart** viewer **Layout** of your own design,  you should consider several factors before you select the visualizer component that you want to work with, as follows:  
  
-   **Troubleshooting context** — this refers to  the environment or circumstances in which you typically expect to experience issues, for example,  connectivity, performance, security, diagnostics, Internet, and so on.  
  
     For example, if you are having performance issues, a high-level view of summary data with a **Bar** element or **Pie** slice visualizer component might be the best choice to obtain a quick assessment of specific types of performance data. Alternatively, a **Table** grid visualizer component can also work when you want to display a combination of parsed field data and computed statistical values in tabular format.  
  
-   **Message type** — this is the type of message data that you are working with. Generally, the messages that are issued by the particular protocol or module with which you are working point to the types of information that you can expose for analysis.  
  
     For example, this could be the message packets that are issued by HTTP, TCP, or LDAP, and even ETW layer events.  
  
-   **Information to expose** — consists of the aspects of message data that you want to expose to optimize the analysis perspective that you can obtain from the displayed results in your **Layout**.  
  
     For example, if you are interested in working with IPv4 messages, you might want to expose network conversations with the **IPv4.Datagram.Network** field in your **Layout** along with their associated message volumes across a set of trace results. If you are interested in working with SMB2 messages, you might want to expose the average response time for all messages associated with the SMB2 queries that occurred in a set of trace results. The average response time would be calculated by a **Layout** formula that is based on the **ResponseTime** Global Annotation; see  [SMB/SMB2 Service Performance](../messageanalyzer_content/smb-smb2-service-performance.md) for further information.  
  
    > [!TIP]
    >  You have the option to employ **Unions** in any **Layout** that you modify, which includes **Union** sets.  
  
-   **Data presentation format** — the format in which you present data should align with the level of detail that you want to see, for example, a high-level summary or low-level details that include message field data  and other computed values, or events occurring in the context of time, as follows:  
  
    -   **High-level summary data** — enables you to see top-level information that you can assess at-a-glance. A **Bar** element or **Pie** slice visualizer component would be a good choice for this type of data presentation because they provide a graphic format that displays the relative distribution of specified values that you can set in ascending or descending order, where each **Bar** element length or **Pie** slice size represents a particular volume of such values, for example message count or cumulative byte volume.  
  
    -   **Low-level details data** — enables you to review significant message details and computed values that provide a set of statistics that can expose the cause of various issues and failures. A **Table** grid visualizer component would be a good choice for this type of data presentation to expose many different field values and calculated values that result in  a statistical view of your data.  
  
    -   **Event data** — enables you to assess events that occur in time. A **Timeline** visualizer component would be a good choice for this type of data presentation, given that you can visually identify the points in time where any particular message occurred in a set of trace results. The **Timeline** component also enables you to use presets or configured windows of time to drill down into any chosen time slot for detailed analysis.  
  
     Note that you can link to some of the built-in **Chart** viewer **Layout** descriptions in the above section "Subcategories for the Built-In Chart Viewer Layouts" to understand chosen **Layouts**, and then display them  in an Analysis Session  to see the various types of graphic visualizer components in action. To locate the **Chart** viewer **Layouts** in Message Analyzer, see the previous [Built-In Chart Viewer Layouts](../messageanalyzer_content/configuring-chart-viewer-layouts.md#BKMK_Charts) topic.  
  
<a name="BKMK_ChartConfigOverview"></a>   
## Overview of Configuring a Custom Chart Viewer Layout  
 Message Analyzer enables you to create your own custom **Layouts** containing one of the four types of data visualizer components. The protocol/module types, fields, properties, and the formulas that you can apply to these entities can provide a quick overview of trace activity at-a-glance or a detailed analysis of statistical data, to enhance your data analysis perspectives. You can use formulas to manipulate the values of fields, properties, and other entities in the messages that you capture to create unique data representations. An example of this is the **Bar** element visualizer component that is used in the **SMB Top Commands** **Layout**. This data visualizer depicts the relative distribution of traffic volume, from the highest to the lowest volume, for SMB commands in a set of trace results. This in turn can help you to quickly evaluate the SMB commands that are consuming the most bandwidth, which may point to other issues.  
  
 **Editing a Built-In Chart Viewer Layout**   
If you want to create a custom **Layout**, you will need to edit an existing **Layout** first  and  then save your changes under a specified **Layout** name. To do so, you must first display the **Layout** you want to edit by selecting it in any of the locations specified in the [Built-In Chart Viewer Layouts](../messageanalyzer_content/configuring-chart-viewer-layouts.md#BKMK_Charts) section. Thereafter, to begin editing, you will need to select the **Chart** item in the global Message Analyzer **Session** menu and then select the **Edit** item in the **Chart** drop-down list to display the **Edit Chart Layout** dialog. You can then make use of the controls in the **Edit Chart Layout** and **Formula Editor** dialogs to modify the current **Layout**.  
  
> [!IMPORTANT]
>  Editing an existing **Layout** and saving it under a different name is the only way you can now create your own **Layouts**, as the former **New Chart** command and others are no longer available. This change is advantageous given that it streamlines the UI and results in fewer clicks and selections to create a custom **Layout**.  
  
 In the topic that follows, a link to which is given  immediately below, you will learn how to use  the controls of the **Edit Chart Layout** dialog to edit an existing **Layout**. After you complete your modifications, you will then learn how to save your changes as a custom **Layout** of your own design.  
  
 ___________________________________\_  
  
 [Using the Edit Chart Layout Dialog](../messageanalyzer_content/using-the-edit-chart-layout-dialog.md)   
 ___________________________________\_