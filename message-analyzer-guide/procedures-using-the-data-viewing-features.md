---
title: "Procedures: Using the Data Viewing Features | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb6551ca-8692-4611-a0eb-4eea5d5cf5ef
caps.latest.revision: 62
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Using the Data Viewing Features

The procedures in this section demonstrate the use of numerous Message Analyzer features that are described in the [Viewing Message Data](viewing-message-data.md) section. They are intended to serve as a cross section of the many ways in which you can use Message Analyzer viewer features and other integrated functions. As viewing message data and analyzing it are closely related, these procedures demonstrate the use of various viewers and tools that manipulate trace results data for analysis purposes. For additional information on the analysis tools that Message Analyzer provides, see [Analyzing Message Data](analyzing-message-data.md).  
  
> [!IMPORTANT]
>  Although these procedures demonstrate the use of Message Analyzer capabilities in some basic analysis scenarios, they are only a sampling of what you can accomplish with Message Analyzer, given that you can also apply the methodologies described here to many other scenarios.  
  
---  
  
 **Procedure Overviews**   
A brief description of each procedure is included here for review, as follows.  

---  
  
 **[Apply Gradient Style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_ApplyGradientColorRules)**  — provides an example of how to utilize gradient style **Color Rules** to quickly flag messages that meet the filtering criteria of multiple **Color Rules**.  
  
 **[Apply a Built-In View Layout](procedures-using-the-data-viewing-features.md#BKMK_ApplyViewLayout)**  — provides an example of a built-in view **Layout** that presents a data column configuration that is useful for diagnosing TCP messages when applied, while also automatically grouping messages by IP conversations and ports (**Group** operations on the **Network** and **Transport** columns, respectively) to enhance diagnostic capabilities and perspectives.  
  
 **[Perform Data Grouping Operations](procedures-using-the-data-viewing-features.md#BKMK_PerformGroupingOps)**  — provides several examples of data grouping operations that demonstrate how you can filter and consolidate data from designated **Analysis Grid** viewer columns and reorganize them into separate groups of common properties that greatly enhance your ability to analyze data and resolve issues.  
  
 **[Perform Top-Level Summary Analysis](procedures-using-the-data-viewing-features.md#BKMK_toplevelsummaryAnalysis)**  — provides an example of how to use the **Protocol Dashboard** viewer to obtain top-level summaries at a glance for a set of trace results.  
  
 **[Perform Interactive Analysis with Data Viewers](procedures-using-the-data-viewing-features.md#BKMK_performInteractiveAnalysis)**  — illustrates a simple method for using the **Protocol Dashboard** and **Analysis Grid** viewers together in an interactive manner to enhance data analysis perspectives.  
  
 **[Apply Viewpoints to Trace Data](procedures-using-the-data-viewing-features.md#BKMK_applyViewpoints)**  — provides an example that shows you how to use the Message Analyzer **Viewpoints** feature, which enables you to examine data from the viewpoint of a protocol, where the messages of a specific viewpoint protocol are displayed at top-level in the **Analysis Grid** viewer with no message layers above them.  
  
 **[Apply a Time Filter to Trace Results](procedures-using-the-data-viewing-features.md#BKMK_ApplyQuickFilter)**  — provides an example that shows you how to apply a **Time Filter** to a set of trace results, so that you can view data in a selected window of time.  
  
 **[Drive Analysis Grid Viewer and Tool Window Interactions](procedures-using-the-data-viewing-features.md#BKMK_DriveInteractions)**  — provides an example that demonstrates interaction between the **Analysis Grid** viewer and various tool windows, such as the **Message Data**, **Field Data**, **Message Stack**, **Details**, and **Diagnostics** **Tool Windows**.  
  
 **[Create an Alias for a Data Field Value](procedures-using-the-data-viewing-features.md#BKMK_CreateAlias)**  — provides an example that demonstrates how to simplify data analysis by creating an **Alias** that  substitutes for a cryptic field value.  
  
 **[Create a Union of Two Data Fields](procedures-using-the-data-viewing-features.md#BKMK_CreateUnion)**  — provides an example that demonstrates how to create a **Union** that correlates/combines two data fields with similar values but different names into a single new field that is specified by the **Union** configuration.  
  
 **[Procedures: Using the Data Filtering Features](procedures-using-the-data-filtering-features.md)**  — see this procedural topic for extensive coverage of different ways to apply a view **Filter**.  
  
> [!IMPORTANT]
>  If you have not logged off Windows after the first installation of Message Analyzer, please log off and then log back on before performing these procedures. This action ensures that in all subsequent logons following installation, your security token will be updated with the required security credentials from the Message Capture Users Group (MCUG). Otherwise, you will be unable to capture network traffic in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapture** provider, **Microsoft-Windows-NDIS-PacketCapture** provider, or the **Microsoft-PEF-WFP-MessageProvider**, unless you start Message Analyzer with the right-click **Run as administrator** option.  
  
<a name="BKMK_ApplyGradientColorRules"></a>   
## Apply Gradient Style Color Rules  
 In the procedure that follows, you will apply the built-in **IPv4 Right Gradient** and **TCP** left gradient **Color Rules** to a Link Layer trace that captured data with the **Local Network Interfaces** **Trace Scenario** that uses the **Microsoft-PEF-NDIS-PacketCapture** provider (available on Windows 7, Windows 8, and Windows Server 2012 operating systems).  
  
> [!NOTE]
>  If your machine is running the Windows 8.1 or later operating system, you can capture data in this example with the **Local Network Interfaces** **Trace Scenario** that uses the **Microsoft-Windows NDIS-PacketCapture** provider.  
  
 This procedure demonstrates a simple way to expose TCP messages that have an IPv4 Network Layer in the message stack. The **Color Rule** that is used in the procedure also serves as an example of how you might design multiple gradient-style **Color Rules** with visually-coordinated opposite facing gradients, which you can then use as a troubleshooting mechanism to quickly identify message stack components at a glance.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Using and Managing Color Rules](using-and-managing-color-rules.md).  

---  
  
<a name="BKMK_Transport-Network-ColorRulesProcedure"></a>   
#### To identify Transport and Network Layer messages with gradient-style Color Rules  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
     To ensure that you have access to all features, run Message Analyzer as an Administrator.  
  
2.  Click **New Session** on the **Start Page** to open the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **Live Trace** tab, click the **Local Network Interfaces** **Trace Scenario**.  
  
     If your operating system is Windows 7, Windows 8, or Windows Server 2012, the **ETW Providers** list on the **Live Trace** tab is populated with the **Microsoft-PEF-NDIS-PacketCapture** provider **Name** and **Id** (GUID). Otherwise, for the Windows 8.1, Windows Server 2012 R2, Windows 10 operating system, or later, the **Microsoft-Windows-NDIS-PacketCapture** provider information displays.  
  
5.  Click the **Start** button in the **New Session** dialog to automatically select the default data viewer and start capturing data. Assuming that you have not changed the default data viewer in the **Default Profile** pane on the **Profiles** tab of the global **Options** dialog, the default viewer will be the **Analysis Grid**.  
  
     Message Analyzer should immediately begin capturing data and accumulating it in the **Analysis Grid** viewer.  
  
6.  While Message Analyzer is capturing data, attempt to reproduce any conditions that are related to a particular TCP or IPv4 issue you are trying to isolate, for example, network connection or packet loss problems.  
  
7.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer  toolbar.  
  
  > [!TIP]
  >  You can temporarily suspend tracing operations by clicking the **Pause/Resume** button and you can resume tracing by clicking the **Pause/Resume** button again.  
  
8.  Click the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar, and then under the **Network** category of the drop-down that displays, select the **TCP** left gradient and **IPv4 Gradient Right** **Color Rules**.  
  
     All top-level TCP messages or other top-level messages that have TCP in the origins tree are highlighted with the light blue left-to-right gradient **Color Rule** style. Also, all TCP messages that have an IPv4 network layer are highlighted in the olive green right-to-left gradient **Color Rule** style, thus enabling you to easily view messages that meet the filtering criteria of both the applied **Color Rules**.  
  
  > [!NOTE]
  >  To isolate either TCP or IPv4 messages at top-level to further enhance analysis, you can apply a TCP or IPv4 viewpoint as appropriate from the Filtering toolbar.  
  
<a name="BKMK_ApplyViewLayout"></a>   
## Apply a Built-In View Layout  
 In the procedure that follows, you will apply the built-in **TCP Deep Packet Analysis with Absolute Sequence Number Grouping** view **Layout** to trace data that is displayed in the **Analysis Grid** viewer. This view **Layout** has a column layout configuration that contains various TCP fields, the values of which can be important when diagnosing TCP issues. The columns that hold TCP field data include **DestinationPort**, **SourcePort**, **PayloadLength**, **SequenceNumber**, **AcknowledgementNumber**, and **WindowScaled** columns. In addition, a **TimeDelta** field is also included to display the running time for captured messages. The predefined **Layout** also includes groupings of **Network** and **Transport** columns that present the details of the IP conversations that took place on corresponding TCP ports within a trace. Note that the **Network** and **Transport** columns were removed after the **Grouping** operation, but before this **Layout** was saved in the default **Layout** Library item collection.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md).  

---  
  
#### To apply a built-in View Layout for TCP diagnosis  
  
1.  Perform steps 1 through 7 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure) to start and stop a Message Analyzer Live Trace Session that uses the **Local Network Interfaces** **Trace Scenario**.  
  
2.  Click the **Layout** drop-down list on the **Analysis Grid** toolbar and then click the **TCP Deep Packet Analysis with Absolute Sequence Number Grouping** item in the drop-down list that appears.  
  
     The new column configuration displays and the data is grouped into **Network**, **Transport**, and **Sourceport** groups, as indicated by corresponding labels  above the tree grid. The data groups are also organized such that the **Transport** nodes are nested within the **Network** nodes, and the **Sourceport** nodes are nested within those. Note that the **Network** conversations can use either IP or Ethernet addresses.  
  
3.  Expand a particular **Network** node to expose the **Transport** node it contains.  
  
     The exposed **Transport** node provides an indication of the number of messages that it contains, along with the source and destination TCP ports over which IP or Ethernet conversations took place.  
  
4.  Expand the **Transport** node to display the TCP messages, so that you can examine the TCP field data. If you are dealing with loss of packets, you might check the **WindowScale** field for low values.  
  
    > [!NOTE]
    >  For convenience of viewing the TCP column data, you can alter the data columns that will horizontally scroll by right-clicking the column that you want as the first scrollable column   and then select the **Freeze Columns to Left** command in the context menu that appears.  
  
5.  Expand the **Sourceport** nodes, so that you can view the messages that transited each TCP port.  
  
6.  Repeat steps 3, 4, 5  for other **Network**, **Transport**, and **Sourceport** nodes as appropriate.  
  
7.  To obtain a different perspective on the data, you can drag the **Transport** group label and drop it to the left of the **Network** group label.  
  
     The data is now grouped and organized with **Network** nodes nested within the **Transport** nodes.  
  
     **Note**: You can drag and drop any of the Group labels into any position that you want, to change the way messages are hierarchically organized.  
  
> [!NOTE]
>  To restore the default **Layout**, click the **Layout** drop-down list on the **Analysis Grid** viewer toolbar, click the **Manage Layouts** item, and then click the **Restore Application Default Layout** command that displays in the submenu that appears.  
  
<a name="BKMK_PerformGroupingOps"></a>   
## Perform Data Grouping Operations  
 In the procedure that follows, you will execute the **Group** command on various **Analysis Grid** viewer data columns, including the **ContentType**, **Transport**, **Source** or **Destination**, and **Diagnosis** data columns. The grouping operations will enable you to quickly determine the object types being requested by your web browser, assess the heaviest port traffic, determine the IP addresses carrying the most traffic, and examine grouped diagnosis messages types, respectively. In this procedure, the **Analysis Grid** viewer will be populated with message data that you capture with the **Microsoft-PEF-WFP-MessageProvider** in the **Loopback and Unencrypted IPSEC**  **Trace Scenario** and the focus will be on Application Layer (HTTP) and Transport Layer messages.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).  

---  
  
#### To perform multiple data grouping operations for analysis  
  
1.  Perform steps 1 through 3 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure), to start Message Analyzer and open the **New Session** dialog for Live Trace Session configuration.  
  
2.  In the **Network** category of the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, click the **Loopback and Unencrypted IPSEC** **Trace Scenario**. Alternatively, click the **Loopback and Unencrypted IPSEC** **Trace Scenario** in the **Favorite Scenarios** list that is accessible from the Message Analyzer **File** menu.  
  
     The **Microsoft-PEF-WFP-MessageProvider** information displays in the **ETW Providers** list on the **Live Trace** tab, which includes the provider **Name**, **GUID**, and a **Configure** link that opens the **Advanced Settings** dialog for this provider.  
  
    > [!NOTE]
    >  In addition to capturing loopback traffic and unencrypted IPSEC messages, the **Microsoft-PEF-WFP-MessageProvider** minimizes other lower-level noise such as broadcast traffic, so that you can focus your analysis above the IP/Network Layer. Also note that messages below the Transport Layer are typically represented in the message stack as a **WFPCapture** and below that are events at the **ETW** level.  
  
3.  If the **Start With** drop-down list in the **New Session** dialog does not indicate the **Analysis Grid** viewer, then click the drop-down list and select it.  
  
4.  Click the **Start** button in the **New Session** dialog to start capturing data.  
  
     Message Analyzer may immediately begin capturing and accumulating message data in the **Analysis Grid** viewer.  
  
5.  While Message Analyzer is capturing data, launch a web browser and attempt to reproduce any conditions that are related to a particular HTTP issue you might be experiencing. For example, you might attempt to navigate to a poorly performing web server with your browser.  
  
6.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
7.  Click the **Add Columns** button on the **Analysis Grid** viewer toolbar to display the **Field Chooser** **Tool Window** in focus in its default location, if it is not already displayed.  
  
8.  Open the **HTTP** node in **Field Chooser** and navigate to the **ContentType** field in the HTTP **Operation** message hierarchy, right-click the field, and then select the **Add As Column** context menu item to add the **ContentType** column to the **Analysis Grid** viewer.  
  
9. Open the **TCP** node in **Field Chooser** and navigate to the **Transport** field in the **Segment** message hierarchy, right-click the field, and then select the **Add As Column** context menu item to add the **Transport** column to the **Analysis Grid** viewer.  
  
10. In a similar manner, add the **ResponseTime** field from the **Global Annotations** node in **Field Chooser** as a new column in the **Analysis Grid** viewer, so that you can determine how quickly the web server is responding to HTTP requests.  
  
11. Right-click the **ContentType** column in the **Analysis Grid** viewer and select the **Group** command from the context menu.  
  
     The trace data is grouped according to the different content types associated with HTTP messages, so that you can examine the types of objects being passed to your web browser by the server.  
  
 > [!TIP]
 >  To create a more focused analysis, you can limit the display to HTTP messages only by specifying an HTTP **Viewpoint**; you can do this by clicking the **Viewpoint** drop-down list on the Filtering toolbar and then selecting the **HTTP** item.  
  
 When you are done with assessing the data, click the **x** in the **ContentType** Group label above the **Analysis Grid** to remove the Group and return to the default view **Layout**.  
  
12. Sort the **ResponseTime** column in descending order and then **Group** this column to quickly expose the slowest server responses and associated messages in separate Groups for analysis.  
  
13. Remove the **ResponseTime** Group by clicking the **x** in the **ResponseTime** Group label above the **Analysis Grid**.  
  
14. Right-click the **Transport** column in the **Analysis Grid** viewer and select the **Group** command from the context menu.  
  
     The trace data is grouped according to the different Transport types, such as TCP or UDP, so that you can examine the ports across which the most substantial traffic is transiting.  
  
15. Remove the **Transport** grouping in the previously indicated manner and then execute the **Group** command on the default **Source** or **Destination** column of the **Analysis Grid** viewer.  
  
     The trace data is grouped according to **Source** or **Destination**, as appropriate, so that you can determine which IP addresses are carrying the most traffic. Note that you can obtain similar statistics by executing a **Group** command on the **Network** column, which you can add from the IP message hierarchy in the **Field Chooser**.  
  
 > [!TIP]
 >  You can also nest groups by performing successive **Group** operations on multiple columns. For example, you might also add the **Response.PayloadLength** field from the **HTTP** message hierarchy in **Field Chooser** and then perform multiple groupings in succession on the **ResponseTime**,  **ContentType**, **PayloadLength**, and **Transport** data columns so you can view the slowest server response times correlated with the content types that are associated with the highest payload values, along with the TCP ports that carried that information. Another grouped configuration you can try would be to **Group** the **Source** and **Destination** columns, in that order, to organize all the **Destination** traffic that is associated with each **Source** address, or vice versa.  
  
16. Remove all **Group** configurations to return to the original **Analysis Grid** viewer display and then execute the **Group** command on the **DiagnosisTypes** column in the **Analysis Grid** viewer.  
  
     The trace data is grouped according to the different types of diagnosis messages, which includes **Application**, **InsufficientData**, **Parsing**, and **Validation** message types, so that you can immediately assess the types of errors that occurred in your trace. For more information about the meaning of these diagnosis message types, see the “Enum Values for DiagnosisType filters” table in the [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.  
  
<a name="BKMK_toplevelsummaryAnalysis"></a>   
## Perform Top-Level Summary Analysis  
 In the procedure that follows, you will use several viewing infrastructure components to accomplish simple data analysis tasks. For example, you will use the graphic chart visualizer components of the **Protocol Dashboard**  viewer, which includes the **Top Level Protocol Summary** **Bar** element, **Pie** chart, **Table** grid, and the **Timeline** (**Top Level Protocols Over Time**) visualizer components, to view top-level protocol summary data that can reflect traffic volume levels for the message types in a trace, along with message activity across selected windows of time into which you can zoom. In the first part of the procedure, you will use the **Microsoft-PEF-NDIS-PacketCapture** provider in the **Local Network Interfaces** **Trace Scenario** to capture message data in a Live Trace Session. However, if you are running the Windows 8.1 or Windows Server 2012 R2 operating system, you will be using the **Microsoft-Windows-NDIS-PacketCapture** provider in this **Trace Scenario**.  
  
 This example also shows how to use the **SMB Reads and Writes Bytes/Second**, **SMB File Stats**, and **SMB/SMB2 Service Performance** view **Layouts** for **Charts** to expose file access activities and statistics. In this part of the procedure, you will start a new session with the **Loopback and Unencrypted IPSEC** **Trace Scenario**, in which you will use the **Microsoft-PEF-WFP-MessageProvider** to focus on statistical summaries of SMB/SMB2 file access operations messages above the IP/Network Layer.  
  
---  
  
 **More Information**   
 **To learn more** about the **Protocol Dashboard** viewer, see the [Protocol Dashboard](protocol-dashboard.md) topic.  
**To learn more** about the SMB **Layouts** for the **Chart** viewer, see the subtopics in the [File Sharing Category](file-sharing-category.md) section.   

---  
  
#### To analyze top level summary data  
  
1.  Perform steps 1 through 5 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure) to start a Message Analyzer Live Trace Session with the **Local Network Interfaces** **Trace Scenario**.  
  
2.  While Message Analyzer is capturing data, attempt to reproduce conditions that are related to any particular issue you might be trying to resolve, for example, a high volume of TCP traffic to a target computer.  
  
3.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
4.  From  the **New Viewer** drop-down list on the global Message Analyzer toolbar, click   **Charts (Deprecated)** and then select the **Protocol Dashboard** item in the drop-down list.  
  
5.  In the **Protocol Dashboard** viewer, observe the numerical and graphical presentation of top protocol activity in the trace by examining the **Top Level Protocol Summary** and **Top Level Protocols Over Time** visualizer components, which expose the relevant statistics.  
  
     In the **Top Level Protocol Summary** Table and Bar element sections of the dashboard, you can observe message traffic volume that is sorted in a descending scale from highest to lowest. Note that an extraordinarily high traffic volume for a particular module can immediately expose the top bandwidth consumer, or exceptionally heavy TCP traffic might indicate that you have a large quantity of TCP retransmits or duplicate ACK messages in your trace.  
  
     If you suspect there is an issue with a protocol or module that has particularly high traffic volume, you can double-click the Bar element or Pie chart segment representing the module in the **Top Level Protocol Summary** to display only those specific messages in a separate instance of the **Analysis Grid** viewer for further investigation. You can also adjust the time window slider controls of the Timeline visualizer component (**Top Level Protocols Over Time**) to zoom into specific messages in a particular time slot and then double-click a message node to display that traffic only in a separate instance of the **Analysis Grid** viewer for further investigation.  
  
6.  Start another Live Trace Session with the **Loopback and Unencrypted IPSEC** **Trace Scenario** and capture data live with Message Analyzer while performing file access operations that have previously been problematic.  
  
7.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar and then launch the **SMB Reads and Writes Bytes/Second** view **Layout** from the **Chart** drop-down in the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
     From this view **Layout**, you can obtain statistics that reflect the network bandwidth being consumed by the file access/sharing activities of the Server Message Block (SMB) protocols. See [SMB Reads and Writes Bytes/Second](smb-reads-and-writes-bytes-second.md) for further details.  
  
8.  Adjust the time window slider controls in the **SMB Reads and Writes Bytes/Second** viewer to zoom into specific messages in a particular time slot.  
  
9. Double-click a message node or time line in the **SMB Reads and Writes Bytes/Second** data viewer to display specific traffic in a new instance of the **Analysis Grid** viewer tab for further investigation.  
  
 > [!TIP]
 >  You can also use the **Field Chooser** **Tool Window** to add an SMB **FileName** or SMB2 **FileName** column to the **Analysis Grid** viewer and then execute a **Group** command on the new column so that you can examine the SMB traffic that is associated with access to specific files.  
  
10. Optionally, select the **SMB File Stats** view **Layout** from the **Chart** drop-down in the **New Viewer** drop-down list. With this **Layout**, you can examine a summary of SMB file statistics in a **Table** visualizer component that includes the file name, access duration, total number of bytes for each file or folder access operation, and the data transmission rates, as described in [SMB File Stats](smb-file-stats.md).  
  
     You might also consider selecting the **SMB/SMB2 Service Performance** viewer **Layout**, also in the **Chart** drop-down, to examine statistics that expose how long first responses to SMB operations are taking (**ResponseTime**), possibly to expose slow server response issues; and how long it is taking for operations to complete (**ElapsedTime**), as a possible indication of network issues; as described in [SMB/SMB2 Service Performance](smb-smb2-service-performance.md).  
  
<a name="BKMK_performInteractiveAnalysis"></a>   
## Perform Interactive Analysis with Data Viewers  
 The procedure that follows provides a simple example of how you might utilize the **Analysis Grid** and **Protocol Dashboard** viewers interactively to analyze captured message data. The example also indicates how you might user other data viewers interactively with the **Analysis Grid** viewer:  
  
---  
  
 **More Information**   
 **To learn more** about data viewers and how they interact, see [Data Viewer Concepts](data-viewer-concepts.md).   

---  
  
#### To analyze data through data viewer interaction  
  
1.  Perform steps 1 through 4 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure), to start Message Analyzer, open the **New Session** dialog for Live Trace Session configuration, and select the **Local Network Interfaces** **Trace Scenario**.  
  
2.  Click the **Start** button in the **New Session** dialog to begin capturing data in a Live Trace Session.  
  
     The captured data begins to accumulate in the **Analysis Grid** viewer, assuming that you have not changed the default data viewer in the **Default Profile** pane on the **Profiles** tab of the global **Options** dialog that is accessible from the global Message Analyzer **Tools** menu.  
  
3.  While Message Analyzer is capturing data, attempt to reproduce conditions that are related to any particular issue you are trying to isolate.  
  
4.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
5.  From  the **New Viewer** drop-down list on the global Message Analyzer toolbar, click   **Charts (Deprecated)** and then select the **Protocol Dashboard** item in the drop-down list.  
  
6.  In the **Protocol Dashboard** viewer, observe the relative distribution of captured message volumes in the **Top Level Protocol Summary** Bar element visualizer of the **Protocol Dashboard**, in an attempt to isolate message traffic that might be related to failures in a particular component, system, or service. Note that high message volumes can be a flag for underlying issues that may need further investigation, such as network issues and TCP retransmits.  
  
7.  In the Bar element visualizer, double-click the graphic bar representing the message traffic you want to target, for example, a protocol that has a high volume of messages.  
  
     A new instance of the **Analysis Grid** viewer opens and contains only the traffic that you targeted, for further analysis.  
  
8.  Sort the **DiagnosisTypes** column in the **Analysis Grid** viewer to bubble up any errors that might have occurred in the target traffic.  
  
9. Perform a **Group** operation by right-clicking the **DiagnosisTypes** column in the **Analysis Grid** viewer and then selecting the **Group** command from the context menu that displays. The data is then organized into expandable group nodes that each contain different diagnosis message types. By expanding each node, you can view the messages that contain the diagnosis errors.  
  
10. Click the diagnosis error icons in the **DiagnosisTypes** column under the expanded group nodes to review the error message text. You might also examine the **Summary** column descriptions for these messages in the **Analysis Grid** viewer to discover any evidence of the underlying failures that are associated with the diagnosis errors that occurred. You can also review the values of the fields for selected messages in the **Details** **Tool Window**.  
  
---  
  
 **More Information**   
 **To learn more** about the meaning of diagnosis message types, see the “Enum Values for DiagnosisType filters” table in the [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.   

---  
  
<a name="BKMK_applyViewpoints"></a>   
## Apply Viewpoints to Trace Data  
 In the procedure that follows, you will apply HTTP and TCP **Viewpoints** so that you can view HTTP- or TCP-related traffic at top-level, without having to drill down into each message stack to expose these messages. In addition, you will alternately disable or enable Operations so that you can expose HTTP request and response messages — either in their original chronological order (by executing the **Disable Operations** **Viewpoint**), or encapsulated by Message Analyzer in top-level Operation rows (by executing the **No Viewpoint** command) respectively, in the **Analysis Grid** viewer.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Applying and Managing Viewpoints](applying-and-managing-viewpoints.md).  

---  
  
#### To analyze data with applied Viewpoints  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
     To ensure that you have access to all features, run Message Analyzer as Administrator.  
  
2.  Click the Message Analyzer global **File** menu  and then click **New Session** to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **Live Trace** tab, click the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **Microsoft-PEF-WFP-MessageProvider** information displays in the **ETW Providers** list on the **Live Trace** tab, which includes the provider **Name**, **GUID**, and a **Configure** link that opens the **Advanced Settings** dialog for this provider.  
  
 > [!NOTE]
 >  In addition to capturing loopback traffic and unencrypted IPSEC messages, the **Microsoft-PEF-WFP-MessageProvider** minimizes other lower-level noise such as broadcast traffic, so that you can focus your analysis above the IP/Network Layer.  
  
5.  If the **Start With** drop-down list in the **New Session** dialog does not indicate the **Analysis Grid** viewer, then click the drop-down list and select it.  
  
6.  Click the **Start** button in the **New Session** dialog to start the trace and begin capturing data.  
  
     The captured data begins to accumulate in the **Analysis Grid** viewer.  
  
 > [!NOTE]
 >  You can start this type of trace immediately with default provider configuration settings, by selecting the **Loopback and Unencrypted IPSEC** **Trace Scenario** in the **Favorite Scenarios** list on the Message Analyzer **Start Page**. By starting a trace in this manner, you will not have access to provider configuration settings prior to capturing data.  
  
7.  While Message Analyzer is capturing data, launch a web browser and attempt to reproduce any conditions that are related to a particular HTTP issue you are trying to isolate, for example, a slowly responding or non-responsive web server.  
  
8.  Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
9. In the **Analysis Grid** viewer, note that you have HTTP messages displaying as top-level operation message rows, as signified by messages with a blue-cubed icon to the left of the message number, along with some TCP messages at top-level and others hidden within the message stack. You may also have HTTP fragments hidden within **Analysis Grid** viewer expansion nodes. This configuration of displayed messages is typical of the results returned by the **Microsoft-PEF-WFP-MessageProvider**, which focuses on Transport Layer messages and above.  
  
10. Click the **Viewpoints** drop-down list on the Filtering toolbar and select the **HTTP** item from the list.  
  
     All HTTP messages are driven to top-level message rows in the **Analysis Grid** viewer, which can also include any fragments that existed in the origins tree (message stack). In this view configuration, you can focus on HTTP messages without the encumbrance of other message types in display. However, because associated HTTP request and response messages are still grouped as Operations to provide context, there is a chronological displacement of response messages in this configuration that you can resolve by disabling the Operations. See the **Important** note below.  
  
11. Click the **Disable Operations** item in the **Viewpoints** drop-down list on the Filtering toolbar just below the **Analysis Grid** viewer tab.  
  
     Note that the HTTP request and response message pairs that were formerly grouped under Operation nodes are now displayed in chronological order in the **Analysis Grid** viewer. This view should be familiar to Network Monitor users and should enable them to work with the messages in the manner with which they are accustomed.  However, for quick analysis of HTTP request and response pairs, it is more expedient to view the data encapsulated in the default Operation node format to see the information at top-level. At this level, you can still use typical data analysis tools such as sorting, grouping, filtering, and so on.  
  
     Also note that data values that are important to HTTP analysis include **ResponseTime** and **ElapsedTime**, as described in the **Important** note below.  
  
12. To return to the default display, click the **No  Viewpoint** item in the **Viewpoints** drop-down list on the Filtering toolbar to return to the default viewpoint. This is the presentation format in which the **Analysis Grid** viewer normally displays.  
  
13. Next, isolate TCP messages at top-level in the trace by selecting the **TCP** item in the **Viewpoint** drop-down list.  
  
     All TCP messages display in top-level message rows in the **Analysis Grid** viewer. Note that you will not see any Operation message nodes in this view because the **TCP** **Viewpoint** filters out everything above it.  
  
14. From the **TCP** **Viewpoint**, use your typical data analysis tools such as sorting, grouping, filtering, pattern matching, and annotating, in addition to viewing message **Details**, **Message Stack**, and **Diagnostics** **Tool Window** data, to analyze the information. You might also apply the built-in **TCP Deep Packet Analysis with Absolute Sequence Number and Grouping** **Layout** from the **Layout** drop-down list on the **Analysis Grid** toolbar, so you can focus on important TCP field data.  
  
> [!IMPORTANT]
>  Pairing up request and response messages in Operation nodes for protocols that typically use request/response pairs such as HTTP, DNS, and SMB2, provides immediate access to response messages rather than having to search through potentially hundreds or even thousands of messages to find them. Another advantage of this configuration is that you can readily measure and correlate important values such as **ResponseTime** and **ElapsedTime**, which specify how long it took for the first server response and how long it took to receive all message fragments and complete the Operation, respectively. High values for these times can provide an indication of a poorly responding server in the first case and network latency issues in the second. The **ElapsedTime** is displayed by default in the **Analysis Grid** viewer column layout; however, you must add the **ResponseTime** column by right-clicking it under **Global Annotations** in the **Field Chooser** **Tool Window** and then selecting the **Add as Column** command.  
>   
  
>   
>  **More Information**   
>  **To learn more** about average response time for Operations, see [Average Response Time for Operations](average-response-time-for-operations.md).  
> **To learn more** about average elapsed time for Operations, see [Average Elapsed Time for Operations](average-elapsed-time-for-operations.md). 

  
  
<a name="BKMK_ApplyQuickFilter"></a>   
## Apply a Time Filter to Trace Results  
 In the procedure that follows, you will start a Data Retrieval Session and load data from a saved trace or log file. You will then apply a **Time Filter** to the loaded message collection so that you can temporarily focus on analyzing messages in a specified window of time. You will also verify that you can toggle back and forth between the time-filtered data and your original data, as your analysis might require.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, including the benefits of using a **Time Filter**, see [Applying a Time Filter to Session Results](applying-a-time-filter-to-session-results.md).   

---  
  
#### To apply a Time Filter to a set of trace results  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
     To ensure that you have access to all features, run Message Analyzer as an Administrator.  
  
2.  Click the global Message Analyzer **File** menu and then click **New Session** to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Files** button to display the **Files** tab along with the associated session configuration features that it contains in the **New Session** dialog for a Data Retrieval Session.  
  
4.  On the **Files** tab of the **New Session** dialog, click the **Add Files** button on the **Files** tab toolbar to launch the **Open** dialog, select a large trace or log file containing data that you want to view in a specific time window, and then click **Open**.  
  
 The name of the trace or log file appears in the files list.  
  
5.  If you loaded a \*.log file, you should choose an applicable configuration file from the **Text Log Configuration** drop-down list just below the toolbar of the **Files** tab for your log, to enable full parsing of messages.  
  
 > [!IMPORTANT]
 >  A built-in OPN configuration file is required to parse a text log. Message Analyzer provides several configuration files by default, including Cluster, IIS, SambaSys, and Netlogon .log files, among many others. If the type of text log you want to parse is not included in the previously specified list, you will need to create your own custom OPN configuration file to parse your log, as described in [Addendum 1: Configuration Requirements for Parsing Custom Text Logs](addendum-1-configuration-requirements-for-parsing-customtext-logs.md).  
  
6.  Confirm that the **Analysis Grid** viewer is selected in the **Start With** drop-down list and then click the **Start** button in the **New Session** dialog to start loading the message data.  
  
 > [!IMPORTANT]
 >  Do *not* configure a **Time Filter** in the Data Retrieval Session configuration, given that you will be doing this only *after* the data is loaded into Message Analyzer.   You might do this in a different scenario where you want to improve performance by limiting the amount of input messages from a high volume data file, as described in [Considering Performance vs. Usability Factors for Time Filter Application](applying-a-time-filter-to-session-results.md#BKMK_PerfVsUsability), but not in this particular example.  
  
7.  After the message data is loaded and displayed in the **Analysis Grid** viewer, click the **Add Time Filter** item from the **Add Filter** drop-down list on the Filtering toolbar to open the **Time Filter** panel.  
  
8.  In the **Time Filter** panel, use the **Start Time** and **End Time** slider controls to configure a window of time in which you want to view data. As you do this, you will see the **Start Time** and **End Time** values change.  
  
9. When you are done with **Time Filter** configuration, click the **Apply** button in the **Time Filter** panel to filter the message data according to the time window that you specified.  
  
     The number of messages displaying in the default data viewer is reduced in accordance with the specified **Time Filter** configuration, thus enabling you to perform analysis on a focused data set.  
  
     Note that the number of messages that display are indicated next to the **Available** label on the Message Analyzer status bar at the bottom of the UI.  
  
10. To remove the time filtering configuration that you applied, click the **Remove** button in the **Time Filter** panel to return to your original data.  
  
11. To reapply the same time filtering configuration, click the **Apply** button again.  
  
     Note that you can toggle the application and removal of a **Time Filter** as many times as your analysis requires. You can also apply view **Filters**, **Viewpoints**, and **Viewpoint Filters** to the time filtered results to further focus the results you want to analyze.  
  
 > [!NOTE]
 >  **Time Filters** do not persist across sessions or even across viewers of the same session, which means that you will need to create a new **Time Filter** configuration for every session or viewer where you want to apply time window filtering. Also note that you can save any data set to which you have applied a **Time Filter** by clicking **Save As** on the global Message Analyzer **File** menu and specifying the **Filtered Messages for Analysis Grid view** option to perform the save with the **Save/Export Session** dialog.  
  
<a name="BKMK_DriveInteractions"></a>   
## Drive Analysis Grid Viewer and Tool Window Interactions  
 In the procedure that follows, you will run a trace and display data in the **Analysis Grid** viewer. Thereafter, through message selection in the **Analysis Grid** viewer, or message and field selection in various **Tool Windows**, the procedure will demonstrate how to interactively drive the display of data in these viewing components to facilitate rapid assessment of message details, which include field values and types, hexadecimal or binary data, diagnosis message types and details, message stack configurations, and so on. This procedure assumes that certain tool windows you will be working with are not currently displayed in the Message Analyzer analysis surface. If they are already displayed, please ignore the steps that specifically require you to display them.  
  
---  
  
 **More Information**   
 **To learn more** about how to position Message Analyzer data viewers and **Tool Windows** for enhanced data analysis, see [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md).   

---  
  
#### To drive interaction between the Analysis Grid viewer and tool windows  
  
1.  Perform steps 1 through 7 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure) to start and stop a new Message Analyzer Live Trace Session that uses the **Local Network Interfaces** **Trace Scenario**.  
  
2.  Click the global Message Analyzer **Tools** menu, click the **Windows** item, and then select **Diagnostics** in the submenu that appears, to display the **Diagnostics** **Tool Window** in its default docking location.  
  
 > [!NOTE]
 >  The **Diagnostics** window is a preview feature that will not be included in the **Windows** submenu unless you have first selected it on the **Features** tab of the **Options** dialog. This dialog is also accessible from the global Message Analyzer **Tools** menu. Note that a Message Analyzer restart is required after this selection.  
  
3.  Click the global **Tools** menu again, click the **Windows** item, click the **Message Stack** item, and then select **Message Stack 1** in the submenu to display the **Message Stack 1** **Tool Window** in its default docking location.  
  
4.  Ensure that the **Message Stack 1** window is in focus (click its tab) and then select any message in the **Analysis Grid** viewer.  
  
     Observe that message selection in the **Analysis Grid** viewer drives message selection in the **Message Stack 1** window and message details in the **Details** **Tool Window**.  
  
5.  Click the **Diagnostics** window tab in its default docking location to bring it into focus and then select one or more diagnosis message types in the **Diagnostics** grid.  
  
     Observe that message selection in the **Diagnostics** window drives selection of one or more top-level messages in the **Analysis Grid** viewer and corresponding message details in the **Details** window.  
  
 > [!NOTE]
 >  You should be aware that even though top-level messages are highlighted, the actual message that contains a diagnosis error might be at a lower layer in the origins tree (message stack). You can determine this by expanding message nodes in the **Analysis Grid** viewer under the highlighted top-level message/s. In addition, note that the **Diagnostics** window data columns provide descriptions of all diagnosis messages in the current trace results, so you do not have to drill down into the origins tree through node expansion to see them.  
  
6.  Click the **Message Data 1** **Tool Window** tab in its default docking location to bring it into focus and then select any message in the **Analysis Grid** viewer.  
  
     Observe that message selection in the **Analysis Grid** viewer drives the display of hexadecimal, binary, or ASCII data selection in the **Message Data 1** window and message details in the **Details** window.  
  
 > [!NOTE]
 >  If you select the top-level message in any Operation row, it does not display any data in any **Message Data** window. Rather, you must expand the Operation node in the **Analysis Grid** viewer and select one of the nested request or response messages that it contains to display highlighted hexadecimal data.  
  
7.  Select any message in the **Analysis Grid** viewer and then select a field **Name** in the **Details** window.  
  
     Observe that field selection in the **Details** window drives the display of a hexadecimal, binary, or ASCII  field value in any **Message Data** window and a field value in the **Field Data** **Tool Window** as well, provided that the field you selected in **Details** had a field *value*.  
  
<a name="BKMK_CreateAlias"></a>   
## Create an Alias for a Data Field Value  
 In the procedure that follows, you will perform a live trace and display the results data in the **Analysis Grid** viewer. You will then create an **Alias** for an IPv6 address and name it with a string value of “MyComputer”. You will then use the new **Alias** in a Filter Expression that you apply to the trace.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md).  

---  
  
#### To create a field value Alias  
  
1.  Perform steps 1 through 7 of the procedure [To identify Transport and Network Layer messages with gradient-style Color Rules](procedures-using-the-data-viewing-features.md#BKMK_Transport-Network-ColorRulesProcedure) to start and stop a new Message Analyzer Live Trace Session that uses the **Local Network Interfaces** **Trace Scenario**.  
  
2.  In the **Destination** column of the **Analysis Grid** viewer, right-click an IPv6 address for the local computer and select the **Create Alias for ‘Destination’…** item in the context menu that displays. The **Alias Editor** dialog displays, in which you can specify an **Alias** name, **Description**, and **Category**.  
  
     If you do not know the IPv6 address of the local computer, run `IPConfig /All` at the command line to determine it.  
  
3.  In the **Alias** text box of the **Alias Editor** dialog, specify a friendly name such as “MyComputer”, or specify another name that is appropriate for your environment.  
  
4.  In the **Description** text box of the **Alias Editor** dialog, enter a description that identifies the purpose of the **Alias**, for future reference and for identification if you intend to share the **Alias** with other users.  
  
     The **Description** text will display in a tool tip when you hover over the **Alias** name in the **Aliases** drop-down list with your mouse, or when you hover over the **Alias** name in the **Manage Alias** dialog.  
  
5.  In the **Category** combo box of the **Alias Editor** dialog, either select an existing **Category** or specify a new one, for example “IPv6 Addresses”.  
  
     Any new **Category** that you specify appears as a subcategory under the top-level **My Items** category and will contain the new **Alias** after you **Save** it.  
  
6.  In the **Alias Editor** dialog, ensure that the **Auto Refresh Views** check box is selected if you want Message Analyzer to immediately perform a refresh of all data viewers that will be impacted by application of the new **Alias**.  
  
7.  In the **Alias Editor** dialog, click the **Save** button to save your new **Alias**.  
  
     All data viewers, including the **Analysis Grid** viewer and any **Chart** viewer **Layout** that is displayed, are updated to reflect application of the new **Alias**, providing that the **Auto Refresh Views** check box was selected when you saved the **Alias**. If this is the case, observe that the IPv6 address of the local computer is now identified in the **Source** and **Destination** address columns of the **Analysis Grid** viewer as “MyComputer”.  
  
     Also verify that the new **Alias** appears in the **Aliases** drop-down list, which is accessible from the global Message Analyzer **Tools** menu. In a similar manner, the **Alias** should also appear in the **Manage Alias** dialog.  
  
8.  In the text box on the default **Filter** panel of the Filtering toolbar,  enter the following text to create a Filter Expression that uses your new **Alias**:  
  
     `*Source == “MyComputer”`  
  
 > [!NOTE]
 >  If a **Filter** panel on the Filtering toolbar is not currently displayed, click the **Add Filter** drop-down list just below the **Analysis Grid** viewer tab and select the **Add Filter** item in the list.  
  
9. Click the **Apply** button on the **Filter** panel of the Filtering toolbar and observe that the specified filter removes all traffic except the messages in which “MyComputer” represents either the **Source** or **Destination** computer IPv6 address.  
  
> [!NOTE]
>  If you want to save the filter you created in this procedure, select the **New Filter** item in the **Library** drop-down on the **Filter** panel of the Filtering toolbar and provide a **Name**, **Description**, and **Category** for the filter in the **Edit Filter** dialog that appears before you **Save** it. Note that the **Edit Filter** dialog automatically captures the Filter Expression text that you specified in the **Filter** panel text box.  
  
<a name="BKMK_CreateUnion"></a>   
## Create a Union of Two Data Fields  
 In the procedure that follows, you will load data into Message Analyzer from two saved files that contain related data that was captured in a common environment and within the same time frame; one from a log file and the other from a former live trace. The procedure specifies files that contain messages from SMB operations that have identical value data for certain fields, but which are named differently. After you load your data files into Message Analyzer, the data should display in the **Analysis Grid** viewer and in an interlaced fashion. Thereafter, you will create a **Union** that combines two fields of equal value but with different names into a single field with a new name, to simplify your data analysis processes with Message Analyzer.  
  
> [!IMPORTANT]
>  Because creating a working **Union** in your Message Analyzer installation depends on combining fields that are specific to your environment, the procedure that follows uses hypothetical field names, such as `Command.smb_cmd` and `Command`. Therefore, when using this procedure to create a *working* **Union**, you should substitute actual field names that are contained in actual data files that are specific to your environment. In addition, you have the option to specify any **Union** name that is appropriate for your needs.  
  
---  
  
 **More Information**   
 **To learn more** about the concepts upon which this example procedure is based, see [Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md).   

---  
  
#### To create a Union of two related data fields  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
     To obtain access to all features, be sure to run Message Analyzer as an Administrator.  
  
2.  From the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Files** button to display the **Files** tab along with the associated session configuration features that it contains in the **New Session** dialog for a Data Retrieval Session.  
  
4.  On the **Files** tab of the **New Session** dialog, click the **Add Files** button on the **Files** tab toolbar to launch the **Open** dialog, select the trace and log files that contain the data fields for which you will create a **Union**, and then click **Open**.  
  
 > [!TIP]
 >  You will need to know in advance the field names from the messages in your input files for which you will be creating a new **Union**. As an example, the  built-in **SMBTID** union that you can access from the global Message Analyzer **Tools** menu creates a **Union** of the following three fields that are  accessible in **Field Chooser** **Tool Window**  under the **SMB**, **SMB2**, and **SambaSysLog** nodes, respectively:  
 >
 > **SMB.SmbHeader.Tid**  
 > **SMB2.SMB2Request.Header.TreeId**  
 > **SambaSysLog.smb_command.command.smb_tid** - note that the **SambaSysLog** node and this field will only exist in **Field Chooser** if a Samba \*.log  file is loaded into  Message Analyzer with a  **SambaSysLog** configuration file specified in the **New Session** dialog for a Data Retrieval Session. This  could apply if you are loading a *.log file into Message Analyzer.  
 >
 >  Whenever you create a new **Union**, you will need to use the **Field Chooser** to locate and add the fields that are to comprise the **Union**, as  indicated ahead in this procedure.  
   
 The name of the trace and log files appear in the files list.  
  
5.  Observe the current **Start With** drop-down list selection in the **New Session** dialog; if it is not the **Analysis Grid** viewer, click the drop-down list and select the **Analysis Grid** item.  
  
6.  Click the **Start** button in the **New Session** dialog and observe that the messages loaded into Message Analyzer from the log and trace files display in a chronological interlaced fashion in the **Analysis Grid** viewer, with a column for each differently named field of interest that displays similar values in each corresponding column.  
  
7.  Click the **Unions** button on the global Message Analyzer toolbar to display the **Edit Union** dialog.  
  
8.  In the **Edit Union** dialog, perform the following actions:  
  
    -   In the **Name** text box, specify a name for the **Union**. Be sure to enter a name that is meaningful in your environment. In this example, the hypothetical **Union** name is `SMBCommand2`.  
  
    -   In the **Category** combo-box, either select an existing **Category** or type a new one.  
  
    -   To add the fields you want to combine in the **Union**, click the **Add** button to display the **Field Chooser** **Tool Window**, in which you can locate the field names. Note that you can add only one field at a time with the **Field Chooser**. In this example, the hypothetical field names are `Command.smb_cmd` and `Command`.  
  
         As you add fields, you should notice the **Type** label displaying the most appropriate data type for the combined fields, as calculated by Message Analyzer; see [Creating Unions](creating-unions.md) for more information.  
  
    -   When you are finished configuring the **Union**, click the **Save** button in the **Edit Union** dialog.  
  
         The new **Union** is added to the root **Unions** node in the **Field Chooser** window.  
  
9. Open the **Field Chooser** window by clicking the **Add Columns** button on the **Analysis Grid** viewer toolbar.  
  
10. Expand the root **Unions** node in the **Field Chooser** and then double-click the name of the new **Union** to add it as a new data column in the **Analysis Grid** viewer column layout.  
  
     Observe that the new \<*unionName*> column in the **Analysis Grid** viewer correlates the data field values for the disparate field names that you specified in the **Union** you created. Note that you can remove the disparate field columns from the **Analysis Grid** viewer by selecting the **Remove** command that displays as a context menu item when you right-click the corresponding column header for each field. When the original field columns are removed from the **Analysis Grid** viewer, the **Union** name column will continue to correlate the values for the underlying data fields contained in the **Union**.  
  
## See Also  

[Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md)