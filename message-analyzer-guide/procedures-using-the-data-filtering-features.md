---
title: "Procedures: Using the Data Filtering Features | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6d0f1e0-24a7-47bb-b3d4-a049d81ef84a
caps.latest.revision: 88
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Using the Data Filtering Features

The procedures in this section encapsulate many of the filtering functions described in the [Filtering Message Data](filtering-message-data.md) section. For each procedure, background scenario information is provided to set the context for the problem that each procedure will help to resolve. The background information describes at a high-level some common issues that you might encounter, while the procedures demonstrate how you can use Message Analyzer to isolate relevant data with the use of filters and simplify your data assessment and problem resolving process.  
  
> [!IMPORTANT]
>  Although these procedures demonstrate the use of Message Analyzer capabilities with respect to issues specific to the HTTP, TCP, and SMB protocols, these are only a sampling of what you can accomplish with Message Analyzer, given that you can also apply the same methodologies described here to troubleshoot a wide range of other types of network traffic and events.  
  
> [!NOTE]
>  As the person running the procedures in the examples of this section, it is assumed that you are a Network Administrator, or that you are at least familiar with networking concepts.  
  
---  
  
 **Procedure Overviews**   
A brief description of each procedure is included here for review, as follows.  

---  
  
**[Filtering a Data Retrieval Session](procedures-using-the-data-filtering-features.md#BKMK_FilterImportedData)**  — provides examples of the following:  
  
-   How to apply a **Session Filter** to data that is loaded into Message Analyzer through a Data Retrieval Session that targets a saved trace file as input, so you can isolate and analyze HTTP request messages sent from a specified client IP address to a poorly performing web server along with the response messages that were issued back to the client. Some HTTP analysis techniques are also provided in the procedure to help you discover possible reasons for the poor performance of a hypothetical web server.  
  
-   How to apply a **Time Filter** to data that is loaded into Message Analyzer through a Data Retrieval Session that targets input files that consolidate several message sources, so that you can view data in specific windows of time in which problems are suspected to have occurred.  

  ---

  **More Information**   
  **To learn more** about the types of input files to which you can apply a **Time Filter**, see [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).   

  ---

**[Filtering Live Trace Session Data](procedures-using-the-data-filtering-features.md#BKMK_FilterLiveData)**  — provides examples of the following:  
  
-   How to collect data from a specific network interface in a Live Trace Session that uses the **Local Network Interfaces** **Trace Scenario**, by selecting an **Adapter** from which to capture data. This can be useful to isolate data on a specific adapter when network adapters are on different networks or load balanced on the same subnet where traffic spans multiple adapters.  
  
-   How to specify a **WFP Layer Set** filter in a Live Trace Session that uses the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario** to capture inbound TCP traffic only, in order to limit the number of captured messages while focusing on TCP ACK traffic for troubleshooting purposes.  
  
-   How to specify a **Session Filter** in a Live Trace Session that uses the **Loopback and Unencrypted IPSEC** **Trace Scenario** to isolate TCP messages, in an attempt to correlate slow file transfers or sluggish web page loading performance with TCP retransmit issues.  
  
-   How to specify a **Fast Filter** that filters messages at the provider level based on a port or client IP address. The filtering is applied to a busy server where the responses are slow, in a Live Trace Session that uses the **Loopback and Unencrypted IPSEC** **Trace Scenario**, in order to reduce captured message volume and lower the impact on server performance while still capturing sufficient data for analysis. Demonstrates the efficiency and performance advantages of **Fast Filters** that enable you to capture the least amount of data possible to resolve a problem.  
  
-   How to specify a **Hostname** and/or **Port** filter in a Live Trace Session that uses the **Pre-Encryption for HTTPS** **Trace Scenario** to reduce captured traffic volume and isolate client messages sent to a specified web server that is very busy and is causing users to experience connection issues. Applies the specified filters to gather sufficient data for the assessment of possible connection problems, without imposing a high-volume data capture on a client computer that is overwhelmed with traffic. Assesses possible causes by examining HTTP **StatusCode** indicators for connection issues and errors.  
  
**[Filtering Live Trace Session Results](procedures-using-the-data-filtering-features.md#BKMK_FilterTraceResults)**  — provides examples of the following:  
  
-   How to apply an Address and Port view **Filter** to the results of a Live Trace Session that used the **Local Network Interfaces** **Trace Scenario**, and to thereby remove unwanted lower-layer traffic and streamline the detection of virus signatures.  
  
-   How to apply an HTTP view **Filter** to the results of a Live Trace Session that used the **Loopback and Unencrypted IPSEC** **Trace Scenario**, to isolate all HTTP traffic from a particular client computer, including all the origins messages in the underlying stack where a problem might occur in supporting HTTP operations. Alternatively uses the **HTTP** **Viewpoint** to present data from the perspective of the HTTP protocol. Demonstrates the superior capabilities of Message Analyzer compared to its predecessor Network Monitor, which returns only HTTP headers in a similar scenario.  
  
-   How to apply TCP view **Filters** to the results of a Live Trace Session that used the **Loopback and Unencrypted IPSEC** **Trace Scenario** to help expose the causes of TCP connection and data transmission issues such as lost TCP segments, slow data transmission rates, or broken TCP three-way handshakes.  
  
-   How to apply an HTTP filter to the results of a Live Trace Session that used the **Pre-Encryption for HTTPS** **Trace Scenario**, so you can isolate specific HTTP request/response messages and analyze HTTP **StatusCodes** and **Reason** phrases for evidence of a poorly performing web server.  
  
**[Filtering with Color Rules and Exposing Diagnostics for TCP and SMB](procedures-using-the-data-filtering-features.md#BKMK_FilterWithColorRules)**  — how to apply **Color Rules** to the results of a Live Trace Session that used the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario** with a **Session Filter** to expose TCP and SMB diagnostic messages, in order to prompt further analysis of faulty or erratic file share access.  
  
> [!NOTE]
>  In the procedures of this section, placeholders within angle brackets (<>) refer to values that you enter that are specific to your system/s. However, do not include the angle brackets in your entries when testing these procedures.  
  
> [!IMPORTANT]
>  If you have not logged off Windows after the first installation of Message Analyzer, please log off and then log back on before performing these procedures. This action ensures that in all subsequent logons following installation, your security token will be updated with the required security credentials from the Message Capture Users Group (MCUG). Otherwise, you will be unable to capture network traffic in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapture** provider, **Microsoft-Windows-NDIS-PacketCapture** provider, or the **Microsoft-PEF-WFP-MessageProvider**, unless you start Message Analyzer with the right-click **Run as administrator** option.  
>   
>  Even if you log off your system, log back on, and receive the required security credentials from the MCUG, you will still need to use the **Run as administrator** option if you want to capture message traffic in Message Analyzer **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider or the **Microsoft-PEF-WFP-MessageProvider**, which both have remote capabilities. Because of the inherent remote capabilities of these message providers, additional security restrictions must be applied.  
  
<a name="BKMK_FilterImportedData"></a>   
## Filtering a Data Retrieval Session  
 This section provides examples of possible ways to filter data that is loaded into Message Analyzer from saved trace or log files. The examples include the use of an HTTP **Session Filter** that is applied to a saved trace file and an adjustable **Time Filter** that is applied to one or more log files.  
  
 **Applying a Session Filter to Saved Trace Data**   
The hypothetical high-level issue in this example is that a Network Administrator has client browsers that send requests to a web server that is being constrained, possibly by high message volumes, connection problems, or other issues. The administrator loads data from one or more saved trace files containing messages that were originally captured on one or more client computers by using the **Loopback and Unencrypted IPSEC** **Trace Scenario**, which reduces most network noise at the Data Link Layer. The example assumes that the trace ran over an adequate time period to reproduce the connection issues that clients are experiencing. Messages are loaded into Message Analyzer through a Data Retrieval Session with a **Session Filter** applied that isolates HTTP “GET” requests (displayed under HTTP operation nodes in the **Analysis Grid** viewer) that were sent to a specified web server from a particular client IP address.  
  
 The purpose of the **Session Filter** in this case is to enable the administrator to isolate HTTP operations and facilitate analysis of the HTTP request and response messages that were interchanged between a specified web server and a specified client IP address, which resulted in possible transport errors, request timeouts, or other faulty status indications. In this example, the administrator also discovers possible reasons why the web server performed poorly by examining the HTTP **StatusCode** indicators and **ReasonPhrases** that were sent back to the client computer in HTTP response messages.  
  
> [!NOTE]
>  A **Session Filter** enables you to isolate specific messages and limit the amount of data stored in memory, which provides a performance advantage, but can be more expensive in terms of processing time. A view **Filter** is somewhat more efficient and makes it easier to work with your data after it displays in Message Analyzer.  
  
 For example, a view **Filter** can be applied and then removed because all of your original data is preserved in the Message Store, whereas with a **Session Filter**, all messages that are not targeted to pass the filter are removed before any data is displayed and can only be retrieved by re-running the Data Retrieval Session with the **Session Filter** removed. If you want to re-run a session, click the **Edit Session** button on the global Message Analyzer toolbar to display the **Edit Session** dialog, from where you can reconfigure the session and run it again, as described in [Editing Existing Sessions](editing-existing-sessions.md).  
  
#### To apply a Session Filter to loaded data for HTTP message analysis  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. If you have not logged off and back on after first installing Message Analyzer, then start Message Analyzer with the right-click **Run as Administrator** option.  
  
2.  On the global Message Analyzer toolbar, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Files** button to display the **Files** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  On the toolbar of the **Files** tab in the **New Session** dialog, click **Add Files** to display the **Open** dialog and then navigate to the trace file/s containing the saved trace data you want to work with.  
  
5.  In the **Open** dialog, select the file/s containing the data you want to load into Message Analyzer, and then click **Open**.  
  
     The files list is populated with the file/s you selected.  
  
6.  In the files list, ensure that there is a check mark in the check box next to the file/s containing the data you want to load into Message Analyzer.  
  
7.  In the **Session Filter** text box of the **New Session** dialog, enter the following Filter Expression and substitute appropriate values for the placeholder italic values. In this expression, note that the value for the “Source” phrase is the client IP address:  
  
     `HTTP.Request.Method=="GET" && *HTTPHost == "www.hostname.com"  && *Source == <192.168.1.1>`  
  
8.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
9. Click the **Start** button in the **New Session** dialog to begin loading data into Message Analyzer from the specified file/s.  
  
     The loaded data displays in the **Analysis Grid** viewer.  
  
10. On the **Analysis Grid** viewer toolbar, click the **Add Columns** button to display the **Field Chooser** **Tool Window**.  
  
11. In **Field Chooser**, double-click the **StatusCode** and **ReasonPhrase** fields for **Response** messages in the **HTTP** message hierarchy to add **StatusCode** and **ReasonPhrase** columns to the **Analysis Grid** viewer column layout.  
  
12. Right-click the **StatusCode** column and select the **Group** command to isolate the status data into separate groups with identical status codes for ease of analysis.  
  
  > [!TIP]
  >  You can right-click the **StatusCode** label and select the **Expand All Groups** menu item to expand all the nodes of grouped data.  
  
13. In the **Analysis Grid** viewer, examine the **StatusCode** and **Reason Phrase** values to determine any problem areas that might indicate a poorly performing web server, as described in the status code table in the [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) section of this documentation.  
  
 > [!NOTE]
 >  You can also review the default **TimeElapsed** column in the **Analysis Grid** viewer to verify the elapsed time for HTTP “GET” methods, or for entire HTTP operations to complete. High values for elapsed time in the latter “operations” case may be an indication of network latency or TCP retransmit issues due to dropped packets.  
 >   
 >  You might also add a **ResponseTime** column (from the **Global Annotation** category in **Field Chooser**) to examine the server response times to request messages. This can provide an indication of whether or not a server is performing slowly, as it measures the time difference between the last time-stamped message in the request stack and the **Timestamp** of the first response message that is sent back to the requesting node. Note that you can create a similar configuration for any protocol that makes use of request/response pairs.  
  
14. Expand the top-level HTTP operations nodes and child nodes in the **Analysis Grid** viewer to expose the origins tree for HTTP messages to determine whether any TCP diagnosis errors are present. You can do this by clicking the **Diagnostics** icon in the **DiagnosisTypes** column in the **Analysis Grid** viewer for any message to display diagnosis error details inline. Alternatively, you can view diagnostic information more effectively by doing any of the following:  
  
    -   Open the **Diagnostics** **Tool Window** by selecting it in the **Windows** submenu of the global Message Analyzer **Tools** menu, to display a summary of diagnosis messages for your data set. You can then select diagnosis messages in the **Diagnostics** window to drive the interactive highlighting of corresponding messages in the **Analysis Grid** viewer for further examination of diagnosis errors in those messages.  
  
    -   Perform the **Group** command on the **Diagnosis** column in the **Analysis Grid** viewer to isolate errors by type, by right-clicking the **Diagnosis** column and selecting the **Group** command.  
  
    -   Click the **Diagnosis** column in the **Analysis Grid** viewer until  you sort and bubble up any diagnosis errors that might have occurred.  
  
 > [!TIP]
 >  For ease of analysis, you might also consider displaying only HTTP messages encapsulated in top-level operations with no layers above, by applying an  **HTTP** **Viewpoint** from the **Viewpoints** drop-down list on the Filtering toolbar that appears above the **Analysis Grid** viewer.  
 
 > [!NOTE]
 >  Diagnosis messages that specify lost TCP segments and retransmits might be an indication of packets being dropped by the network, or could indicate TCP performance issues related to TCP **Window** size and/or **WindowsScaleFactor** settings.  
  
**Applying a Time Filter to Loaded Log Data**   
The hypothetical high-level issue in this example is that a Network Administrator has a large volume of data that was collected in one or more log files and he or she wants to view the data in a specific window of time where failures are suspected to have occurred. In this scenario, the administrator will consolidate one or more related log files as input to a Data Retrieval Session and will apply a **Time Filter** that defines a time window in which to view messages. By using the Message Analyzer **Time Filter**, the administrator will limit the amount of data being loaded, reduce the loading time, and as a result, realize better performance. Optionally, the administrator can apply a **Session Filter** to the input data to isolate messages to a specific client IP address, if the log file format supports IP addresses, thereby reducing message count and helping to streamline the message analysis process.  
  
> [!NOTE]
>  Some log files, such as text-based log files in proprietary format, may require you to create an OPN configuration file so that the log messages can be fully parsed by Message Analyzer, as described in [Working With Special Input Requirements](working-with-special-input-requirements.md). However, note that you can select from a number of built-in **Text Log Configuration** files on the toolbar of the **Files** tab in the **New Session** dialog, during Data Retrieval Session configuration. If your log file cannot be parsed by one of the built-in configuration files, you will need to create one, as described in [Opening Text Log Files](opening-text-log-files.md).  
  
#### To apply a Time Filter to input file data and view results in a selected time window  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. If you have not logged off and back on after first installing Message Analyzer, then start Message Analyzer with the right-click **Run as Administrator** option.  
  
2.  Click the **New Session** button on the Message Analyzer **Start Page** to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Files** button to display the **Files** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  On the toolbar of the **Files** tab in the **New Session** dialog, click **Add Files** to display the **Open** dialog and then navigate to the trace file/s containing the saved trace data you want to work with.  
  
5.  In the **Open** dialog, select the file/s containing the data you want to load into Message Analyzer, and then click **Open**.  
  
     The files list is populated with the file/s you selected.  
  
6.  In the files list, ensure that there is a check mark in the check box next to the file/s containing the data you want to load into Message Analyzer.  
  
     After you select the files to include in the Data Retrieval Session, the **Time Filter** pane on the **Files** tab will be populated with **Start Time** and **End Time** values that are derived from the input file/s, in addition to the **Total Messages** count. Note that the time values that initially display create a window that is inclusive of the earliest and latest time values that Message Analyzer detects from the currently selected files in the input files list.  
  
7.  Select the **Use Start Filter** and **Use End Filter** check boxes in the **Time Filter** pane and then adjust the **Time Filter** slider controls to set the time window that contains the data you want to examine.  
  
     The **Start Time** and **End Time** values track the position of the slider controls and the **Filtered Messages** count changes to indicate the number of messages that the Data Retrieval Session will load from the selected log files, for example, one or more \*.etl files, based on the current **Time Filter** settings.  
  
 > [!NOTE]
 >  If the **Start Time** and **End Time** values do not display in the **Time Filter** pane for your log, you can manually specify starting and ending date-times in a format that is appropriate for your log file/s. Thereafter, time window adjustments should track in accordance with the format that you specified. Also be aware that **Start Time** and **End Time** values will appear for \*.log files only after they are parsed, meaning that you can only apply a **Time Filter** to messages in these file types through the **Edit Session** dialog, unless the configuration file specifies the time stamp format.  
  
8.  Optionally, enter the following Filter Expression in the **Session Filter** text box of the Data Retrieval Session configuration, while substituting appropriately for the value in italics, so that you can isolate messages from a particular client IP address — providing that this action is appropriate for the log files you are working with as indicated earlier:  
  
     `*Source==<192.168.1.1>`  
  
9. Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
10. Click the **Start** button to begin loading data from the specified input log file/s.  
  
     The loaded and filtered data displays in the **Analysis Grid** viewer to enable you to examine the messages in the time window that you specified.  
  
11. To optionally load log data in different windows of time, click the **Edit Session** button on the global Message Analyzer toolbar to open the **Edit Session** dialog, from where you can readjust the slider controls to configure a different **Time Filter** window. Note that you will need to enter the **Full Edit** mode in the **Edit Session** dialog to enable the controls.  
  
 > [!NOTE]
 >  If you alter the original Data Retrieval Session configuration after entering the **Full Edit** mode, by making changes other than adding or removing files, Message Analyzer will perform a required reload of all data.  
  
12. When reconfiguration of the time window in your Data Retrieval Session is complete, click the **Apply** button to start loading data based on the new **Time Filter** or other session reconfiguration.  
  
> [!NOTE]
>  After you apply a **Time Filter** to an input data files configuration, all messages that are outside the time window you specified are removed from displayed results. If you want to restore all messages from your log files, you will need to reload all data with the **Time Filter** removed.  
  
 However, as an alternative to applying an input **Time Filter** prior to loading data from saved files, you can simply load all input log data as is and then apply a **Time Filter** to session results from the Filtering toolbar to isolate data to a specified time window. The action of the latter **Time Filter** can be quickly undone by simply  clicking the **Remove** button on the Time Filter panel of the Filtering toolbar, so you can conveniently return to the original data set to review all messages or apply different time window filtering as required, without having to reload any data. However, there are some factors to consider when choosing to use an input **Time Filter** versus a session results **Time Filter**, as described in [Applying a Time Filter to Session Results](applying-a-time-filter-to-session-results.md). For example, when loading data from large log files without an input **Time Filter**, Message Analyzer performance may diminish.  
  
<a name="BKMK_FilterLiveData"></a>   
## Filtering Live Trace Session Data  
 This section provides examples of possible ways to filter data as it is being collected from several Live Trace Sessions that separately utilize one of the following default **Trace Scenarios**:  
  
-   **Local Network Interfaces**  
  
-   **Network Tunnel Traffic and Unencrypted IPSEC**  
  
-   **Loopback and Unencrypted IPSEC**  
  
-   **Pre-Encryption for HTTPS**  
  
The types of filters that are applied in these four  scenarios, in order, consist of an **Adapter** filter, **WFP Layer Set** filter, **Session Filter**, **Fast Filter**, and a **HostnameFilter** and **PortFilter**, as described in the sections that follow.  
  
**Selecting a Network Adapter to Filter a Local Network Interfaces Trace**   
The hypothetical high-level issue in this example is that a Network Administrator has a computer that is acting as a firewall with two adapters on different networks, and he or she wants to look at traffic on one adapter only, possibly for evidence of packets dropped at the NDIS layers. Message Analyzer enables the administrator to specify a particular adapter on which to capture data in a **Local Network Interfaces** **Trace Scenario**, by selecting the adapter in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog that is accessible from the **New Session** dialog during session configuration, while deselecting all other adapters. A trace at the Data Link Layer ensures that the administrator can capture relevant data for the selected adapter.  
  
> [!IMPORTANT]
>  If you are running the **Local Network Interfaces** scenario on a computer with the Windows 7, Windows 8, or Windows Server 2012 operating system, you will be working with the **Microsoft-PEF-NDIS-PacketCapture** provider. However, if you are running this scenario on a computer with the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, you will be working with the **Microsoft-Windows-NDIS-PacketCapture** provider.  
>   
>  Please note that the **Advanced Settings** dialogs for these two providers are very different and contain unique filtering configuration capabilities. The procedure that follows focuses on the **Microsoft-PEF-NDIS-PacketCapture** provider and its configuration capabilities. However, to configure adapter selection in any **Trace Scenario** that uses the **Microsoft-Windows-NDIS-PacketCapture** provider, refer to the [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) topic for further details.  
  
<a name="BKMK_AdapterFilteringLocNetworkIFaces"></a>   
#### To filter data on a specific network interface in a Local Network Interfaces trace  
  
1.  From the **Start** menu, **Start** page, or task bar of the target computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. If you have not logged off and back on after first installing Message Analyzer, then start Message Analyzer with the right-click **Run as Administrator** option.  
  
2.  Click the global Message Analyzer **File** menu, click **New Session**, and then select **Blank Session** in the **New Session** submenu to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Local Network Interfaces** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Name** and **Id** (GUID) of the **Microsoft-PEF-NDIS-PacketCapture** (or **Microsoft-Windows-NDIS-PacketCapture**) provider, along with the **Configure** link, which provides access to the provider **Advanced Settings** dialog.  
  
5.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link next to the **Microsoft-PEF-NDIS-PacketCapture** provider **Id** to display the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, as shown in [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
  
6.  In the **Advanced Settings** dialog, click the **Provider** tab and then deselect the **In** and **Out** check boxes for the **Machine** node in the **System Network** tree grid to deselect the **In** and **Out** check boxes for all adapters.  
  
7.  In the **System Network** tree grid, select the adapter on which to capture data by selecting the **In** and **Out** check boxes for that particular adapter. Ensure that all other adapters are unselected and then click **OK** to exit the dialog.  
  
     The **Microsoft-PEF-NDIS-PacketCapture** provider is now set to capture traffic in both directions on the network interface that you specified.  
  
 > [!NOTE]
 >  You have the option to select only the **In** or **Out** check boxes for any adapter in the **System Network** tree grid, so that you can monitor traffic in a specified direction only. However, in most cases, it is prudent to monitor traffic in both directions. Note that you also have the option to specify a **Fast Filter** for this Live Trace Session in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, to focus on specific results and improve performance.  
  
8.  Verify that the **Analysis Grid** is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
9. Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the Message Analyzer **Analysis Grid** viewer.  
  
10. While Message Analyzer is capturing data, attempt to reproduce any issue that is related to the reason for capturing data on a particular adapter, although this might not be necessary if the issue is  an NDIS layer  that is simply dropping packets.  
  
11. At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
12. Examine the data you captured, as appropriate.  
  
> [!TIP]
>  When using the **Microsoft-Windows-NDIS-PacketCapture** provider in the **Local Network Interfaces** scenario, you can configure filtering that can help determine whether an NDIS layer is dropping packets.  
>   
>  For example, by selecting the **All Layers** check box in the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog, you can specify that packets are intercepted on all layers of the NDIS stack. In addition, by selecting both the **Ingress** and **Egress** check boxes in the dialog, you can specify the traversal path (direction up and down the stack) in which packets are intercepted. By specifying all layers and both traversal paths for an adapter that is dropping packets, you make certain that dropped packet events will be generated for any layer. If packets are being dropped, you should be able to expose them in Message Analyzer as ETW events that have certain characteristics, as described in step 24 of the procedure [Capture Traffic on a Remote Host](procedures-using-the-network-tracing-features.md#BKMK_CaptureRemoteHost).  
  
---  
  
 **More Information**   
 **To learn more** about configuring the **Microsoft-PEF-NDIS-PacketCapture** provider from the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, including how to assign **Fast Filter** **Groups** to selected adapters, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).  
**To learn more** about the unique filtering configurations and other advanced capabilities that are available for the **Microsoft-Windows-NDIS-PacketCapture** provider, including remote tracing, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).   

---  
  
 **Applying a WFP Layer Set Filter to a Network Tunnel Traffic and Unencrypted IPSEC Trace**   
The hypothetical high-level issue in this example is that a Network Administrator wants to run a Live Trace Session that directionally isolates TCP traffic on a client computer to detect connectivity issues while at the same time reduce the amount of TCP traffic that is captured to streamline performance. Message Analyzer enables the administrator to use the **WFP Layer Set** filter configuration of the **Microsoft-PEF-WFP-MessageProvider** in the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario** to isolate inbound V4 traffic at the Transport Layer as a possible starting point for detecting network connectivity issues. Note that the **WFP Layer Set** filter configuration also enables capture of outbound V4 traffic at the Transport Layer in addition to inbound and outbound V6 traffic, in any combination.  
  
#### To apply WFP Layer Set filtering to a Network Tunnel Traffic and Unencrypted IPSEC trace and isolate TCP diagnosis traffic  
  
1.  On the client computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Name** and **Id** (GUID) of the **Microsoft-PEF-WFP-MessageProvider**, along with the **Configure** link, which provides access to the  **Advanced Settings** dialog for this provider.  
  
3.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link next to the **Id** of the **Microsoft-PEF-WFP-MessageProvider** to display the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog.  
  
4.  In the **Advanced Settings** dialog, click the **Provider** tab to display the **WFP Layer Set** inbound and outbound Transport Layer filters.  
  
     By default, the **WFP Layer Set** filter configuration is set to capture messages for all inbound and outbound transports.  
  
5.  In the **WFP Layer Set** pane on the **Provider** tab, deselect the **Outbound Transport V4**, **Inbound Transport V6**, and **Outbound Transport V6** check boxes; then ensure that only the **Inbound Transport V4** check box is selected.  
  
     With this **WFP Layer Set** configuration, the TCP messages that this Live Trace Session captures will be inbound TCP packets only.  
  
6.  Verify that the **Analysis Grid** is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
7.  Click the **Start** button to begin capturing data.  
  
     The captured messages start to accumulate in the Message Analyzer **Analysis Grid** viewer.  
  
8.  While Message Analyzer is capturing data, attempt to reproduce the conditions that result in network connectivity issues being experienced by the client.  
  
9. At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
10. From the **Viewpoints** drop-down list on the Filtering toolbar above the **Analysis Grid** viewer, select the **TCP** item to filter all TCP traffic to top-level so you can more easily examine the TCP inbound traffic that you captured for signs of connection or transmission issues.  
  
     For example, with the **Inbound Transport V4** filter, you could focus on TCP acknowledgement (ACK) traffic only to see whether you have a large number of duplicate ACK messages. You could also add the **TCPDiagnosis** column (see the TCP message hierarchy in **Field Chooser**) to the **Analysis Grid** viewer as a new data column to see diagnosis message summaries that provide useful diagnostic information. You might also execute the right-click **Group** command on the new column to better organize the diagnosis data.  
  
     Other measures you can take to expose connectivity or transmission issues include applying either of the following view **Filters** in the text box of the Filtering toolbar above the **Analysis Grid**:  `*TCPDiagnosis contains "Dup-Ack"` or `*TCPDiagnosis contains "retransmitted"`.  
  
 > [!TIP]
 >  You can also specify these filters in separate Filter panels. The first Filter panel displays by default, where you can enter the first filter in the Filter Expression text box of that panel. To add the second filter to the text box of another Filter panel, select **Add Filter** from the **Add Filter** drop-down list on the Filtering toolbar to display the  second Filter panel with its Filter Expression text box and enter the text of the second filter into it. You can then apply and remove these filters independently by clicking the respective **Apply** and **Remove** buttons on the Filter panels.  
  
 You might also reconfigure the **WFP Layer Set** filtering  by clicking **Edit Session** on the global Message Analyzer toolbar,  clicking the  **Configure** link for the **Microsoft-PEF-WFP-MessageProvider** in the **ETW Providers** list to open the **Advanced Settings** dialog, and then selecting the **Outbound Transport V4** filter only on the **Provider** tab of the dialog. Thereafter in the trace results, apply the following view **Filter** so you can focus on outbound TCP synchronization traffic from the client:  `tcp.syn==true`.  

 In any case, you can also look at diagnosis error messages in the default **DiagnosisTypes** column of the **Analysis Grid** viewer to see what TCP issues you might have. The goal in creating these **WFP Layer Set** filtering configurations is to capture the least amount of traffic to resolve TCP connectivity and/or transmission problems.  
  
---

**More Information**   
**To learn more** about Advanced Settings for the **Microsoft-PEF-WFP-MessageProvider**, see [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  

---  
  
 **Applying a Session Filter to a Loopback and Unencrypted IPSEC Trace**   
The hypothetical high-level issue in this example is that a Network Administrator has a client computer that is experiencing slow file transfer activity or slowly loading web pages. A high number of TCP retransmits could be responsible for the delays. This could be symptomatic of inappropriate TCP **Window** size and **WindowsScaleFactor** settings, or possibly packets are being dropped by the network or client firewall.  
  
> [!NOTE]
>  Retransmits can also be the result of the memory capacity of a router that cannot keep up with the traffic.  
  
 In this example, the administrator runs a trace on the client computer for a significant time period to gather data, while using the **Microsoft-PEF-WFP-MessageProvider** in a **Loopback and Unencrypted IPSEC** **Trace Scenario** to minimize low-level traffic from the Data Link Layer and a **Session Filter** to capture only top-level TCP messages or messages containing TCP in the stack. When the trace is complete, the administrator then adds **Window**, **Options**, and **TCPDiagnosis** columns to the **Analysis Grid** viewer column **Layout** and also applies a diagnostic view **Filter** to isolate and review any **Warning** level diagnosis messages that indicate retransmits occurred. The administrator also uses the **Group** command in the **Analysis Grid** viewer to gather the data into a convenient format that quickly consolidates and exposes related data of interest in groups.  
  
 If there are a significant number of TCP retransmits occurring, the administrator can do the following:  
  
-   Ensure that loopback traffic is being filtered out by applying **IPv4** and **IPv6** **Fast Filters** such as `!=127.0.0.1` and `!=::1`, respectively, or filter out the IP address that a local application is using, if applicable. Otherwise, there can be duplication of TCP retransmit messages. You can configure these **Fast Filters** in the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog. Note that the **Local Loopback Network** **Trace Scenario** sets these filters by default to remove loopback traffic.  
  
-   Review the TCP **Window** sizes of TCP segments in the **Windows** column of the **Analysis Grid** viewer and observe whether the values vary significantly. To examine messages for the client IP address only, the administrator can apply the following filter, while substituting appropriately for the IP address in italics:  
  
     `*SourceAddress==<192.168.1.1>`  
  
-   Review TCP **Options** to ensure that the **WindowsScaleFactor** and **Window** size are set to reasonable values, for example, WindowsScaleFactor=2 and Window size=64k.  
  
-   Verify whether the network is dropping packets, for example, a router with excessive memory utilization might be unable to keep pace with packet traffic.  
  
-   Following the initial trace results, verify whether client computer Firewall rules are causing TCP packets to be dropped, or whether the **PEF-WFP-MessageProvider** is causing it; see *Checking for Dropped Packets* in the next procedure.  
  
<a name="BKMK_ApplySessionFilterToLoopbackIPSECTrace"></a>   
#### To apply a Session Filter to a Loopback and Unencrypted IPSEC trace and evaluate TCP diagnostics  
  
1.  On the client computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Name** and **Id** (GUID) of the **Microsoft-PEF-WFP-MessageProvider**, along with the **Configure** link, which provides access to the provider **Advanced Settings** dialog.  
  
3.  In the **Session Filter** text box of the **New Session** dialog, enter the following **Session Filter** to capture top-level TCP messages only, where TCP messages are not in the message (origins) stack:  
  
     `\TCP`  
  
    > [!NOTE]
    >  By using the **Loopback and Unencrypted IPSEC** **Trace Scenario** with the **Microsoft-PEF-WFP-MessageProvider** and applying the specified **Session Filter**, the collected message count on the client computer will be reduced.  
  
4.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
5.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the Message Analyzer **Analysis Grid** viewer.  
  
6.  While Message Analyzer is capturing data, attempt to reproduce the conditions that cause the client to experience the indicated issues.  
  
7.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
8.  From the **Field Chooser** **Tool Window**, add TCP **Window**, TCP **Options**, and **TCPDiagnosis** columns to the **Analysis Grid** viewer column layout.  
  
9. Filter out all TCP messages that do not have a diagnosis error by entering the following Filter Expression in the text box of the default Filter panel on the Filtering toolbar and then click the **Apply** button on the toolbar:  
  
     `TCP#DiagnosisLevels`  
  
10. Optionally, add the client IP address to the diagnosis filter as follows, to isolate diagnostic messages to the client IP address only. In the Filter Expression, substitute appropriately for the italic address value:  
  
     `TCP#DiagnosisLevels && *Source == <192.168.1.1>`  
  
11. Right-click the **TCPDiagnosis** column in the **Analysis Grid** viewer and select the **Group** command to group the different diagnostic error types.  
  
12. Scroll down through the groups until you find one or more groups labeled **Retransmitted**.  
  
     If there are a high number of **Warning** level “Retransmitted” diagnosis messages, then notwithstanding dropped packets, you should determine whether the TCP **Window** size and the **WindowsScaleFactor** of incoming TCP messages are set to appropriate values on the client, in the steps that follow.  
  
13. Remove the **TCP#DiagnosisLevels** filter and then apply the following view **Filter** in the text box of the default Filter panel to filter out all TCP messages that do not contain TCP **Options**:  
  
     `TCP.Options ~= nothing`  
  
 > [!NOTE]
 >  The above filter will return only TCP messages that contain TCP Options and all other messages will be filtered out of the display. Alternatively, if you want to view all TCP messages in relation to IP conversations, including those that have TCP **Options**, you can use the **Field Chooser** window to add a **Network** column (message hierarchy path is IPv4.Datagram.Network) and a **Transport** column (message hierarchy path is TCP.Segment.Transport) to the **Analysis Grid** viewer. You can then use the **Group** command on each of these columns to pivot the data into differently organized data displays that provide alternate contexts for viewing TCP **Options**, as further described by the procedure in [To apply TCP view Filters to Loopback and Unencrypted IPSEC trace results and expose TCP diagnostics](procedures-using-the-data-filtering-features.md#BKMK_ApplyTCPViewFiltersProc).  

14. Highlight TCP messages containing TCP **Options** as necessary and review the **WindowsScaleFactor** option settings, especially for messages that have a low **Window** size value, to determine that they are set to reasonable values. The TCP messages of interest should be those that comprised the SYN request and SYN/ACK response messages of three-way handshakes, as this is where the Option settings are negotiated. You might also consider executing the **TCP Three-Way Handshake** **Pattern Expression** to see the context in which these messages occur. This will also enable you to obtain further information that assists in TCP troubleshooting. See the [Pattern Match Viewer](pattern-match-viewer.md) section for more details  
  
**Checking for Dropped Packets**   
If you want to perform additional checks to determine whether dropped packets are causing TCP retransmits, perform the following steps:  
  
1.  In the current Analysis Session, click the **Edit Session** button on the global Message Analyzer toolbar to open the **Edit Session** dialog.  
  
2.  In the **ETW Providers** list, click the **Configure** link for the **Microsoft-PEF-WFP-MessageProvider** to open the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog.  
  
3.  On the **ETW Core** tab of the dialog, click the **Keywords(Any)** ellipsis and select the **ut:Dropped** event **Keyword** option in the **ETW Keyword Filter Property** dialog.  
  
4.  On the **Providers** tab of the dialog, select the **Select Discarded Packet Events** option.  
  
5.  Click **OK** to exit the dialog and then click the **Apply** button in the **Edit Session** dialog to apply the changes you specified.  
  
6.  After the results have stabilized, check whether the Firewall is blocking packets:  
  
    -   Click the **Show Column Filter Row** icon in the upper left corner of the **Analysis Grid** viewer to display the **Column Filter** text boxes.  
  
    -   Enter the term “Discard” in the **Column Filter** text box beneath the **Summary** column header in the **Analysis Grid** viewer to expose any messages that might indicate the Firewall was involved in blocking traffic.  
  
7.  Check whether the **Microsoft-PEF-WFP-MessageProvider** is dropping packets:  
  
    -   On the Filtering toolbar, click the **Viewpoints** drop-down list and then select the **ETW Layer** **Viewpoint** to display only ETW messages in the **Analysis Grid** viewer.  
  
    -   Apply the following view **Filter** to the results to verify whether the **ut:Dropped** event is present in one or more ETW messages:   
        `ETW.EtwProviderMsg.EventRecord.Header.Descriptor.Keywords==0x0000010000000000`  
        You can also look for the KW_DROPPED flag value in the **Details** **Tool Window** after selecting any ETW message.  
  
---  
  
 **More Information**   
 **To learn more** about filtering for TCP diagnostic messages, see the procedure [To apply TCP view Filters to Loopback and Unencrypted IPSEC trace results and expose TCP diagnostics](procedures-using-the-data-filtering-features.md#BKMK_ApplyTCPViewFiltersProc).   

---  
  
 **Applying Fast Filters to a Loopback and Unencrypted IPSEC Trace**   
The hypothetical high-level issue in this example is that a Network Administrator has a busy server where the responses are slow, but he or she does not want to impact the server with a high-volume trace when troubleshooting issues. Message Analyzer enables the administrator to accommodate this situation and determine why the server is behaving this way, by using a **Fast Filter** based on a **Port** to narrow down the traffic captured on the server. If the problem seems to be related to a particular user, the administrator can use a **Fast Filter** based on a specified client IP address. The intent of this scenario is to demonstrate the efficiency and performance advantages that can be achieved when applying **Fast Filters**, which enable the administrator to capture the least amount of data possible to resolve a problem.  
  
#### To apply Fast Filters to a Loopback and Unencrypted IPSEC trace and isolate specific messages to reduce data volume  
  
1.  On the server computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Name** and **Id** (GUID) of the **Microsoft-PEF-WFP-MessageProvider**, along with the **Configure** link, which provides access to the provider **Advanced Settings** dialog.  
  
3.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link next to the **Id** of the **Microsoft-PEF-WFP-MessageProvider** to display the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog.  
  
4.  In the **Advanced Settings** dialog, click the **Provider** tab to display the **Fast Filters** configuration.  
  
     By default, there are no **Fast Filters** set.  
  
5.  In the **Fast Filters** pane, click the **Fast Filter 1** drop-down list and select the **TCP port** item.  
  
6.  In the text box to the right of the **Fast Filter 1** drop-down list, specify a port number such as `<80>`.  
  
7.  Alternatively, to isolate the data to a specific client IP address, click the **Fast Filter 2** drop-down list and select the **IPv4** item.  
  
8.  In the text box to the right of the **Fast Filter 2** drop-down list, specify a client IPv4 address in a format similar to the following: `<192.168.1.1>`.  
  
9. Click the **OK** button to exit the **Advanced Settings** dialog.  
  
10. Verify that the **Analysis Grid** is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
11. Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the **Analysis Grid** viewer.  
  
12. While Message Analyzer is capturing data, attempt to reproduce the conditions that cause the server to experience the indicated issues.  
  
13. At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
14. Examine the captured data to confirm that slow server responses is an issue.  
  
     For example, if you are working with message data from a protocol that uses request/response pairs (viewed as Operation nodes in the **Analysis Grid** viewer) such as HTTP, SMB, or DNS; ports 80, 445, and 53, respectively; you can add a **ResponseTime** column to the **Analysis Grid** viewer and then sort that column to view the messages that have the highest server response times. Note that high server response times can typically rule out network issues as the cause of delays, providing that operation **TimeElapsed** values are reasonable.  
  
  ---  
    
  **More Information**   
  **To learn more** about the server **ResponseTime** field, see [Average Elapsed Time for Operations](average-elapsed-time-for-operations.md). 
  
  ---  
  
**Applying Hostname and Port Filters to a Pre-Encryption for HTTPS Trace**   
The hypothetical high-level issue in this example is that a Network Administrator is dealing with a client browser that has difficulty connecting with one or more web sites. The client is already overwhelmed with network traffic, so the administrator wants to determine what might be causing the connection problems without imposing a high-volume data capture on the overwhelmed client computer.  
  
In this example, the administrator uses the **Pre-Encryption for HTTPS** **Trace Scenario** with the **Microsoft-Pef-WebProxy** provider and a **Hostname Filter** to isolate messages sent to and from a particular web site, and a **Port Filter** to isolate messages on a particular port, such as 80. This scenario is useful for achieving better performance than using a comparable **Session Filter** that specifies a particular destination IP address and port number. The **Hostname Filter** and **Port Filter** act similarly to the way **Fast Filters** do in that they cause less data to be collected, allow for minimal parsing, and therefore have less impact on the computer where the trace is run. In this scenario, the administrator analyzes HTTP **StatusCode** and **ReasonPhrase** indicators that can reflect connection issues, request timeouts, elapsed time/delays, or other errors that occur when a client is attempting to connect to a specified HTTP web server that might also be very busy.  
  
> [!NOTE]
>  In this scenario, you will be unable to analyze the message data for possible TCP issues because the **Microsoft-Pef-WebProxy** provider captures messages above the Transport Layer.  
  
#### To apply HTTP filters to a Pre-Encryption for HTTPS trace and expose status indications  
  
1.  On the client computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Pre-Encryption for HTTPS** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Name** and **Id** (GUID) of the **Microsoft-Pef-WebProxy** provider, along with the **Configure** link, which provides access to the provider **Advanced Settings** dialog.  
  
3.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link next to the **Id** of the **Microsoft-Pef-WebProxy** provider to display the **Advanced Settings - Microsoft-Pef-WebProxy** provider dialog.  
  
4.  In the **Advanced Settings** dialog, click the **Provider** tab to display the filter configuration.  
  
5.  In the **Hostname Filter** text box, enter a host name value in a format similar to the following:  
  
     `www.bing.com`  
  
6.  In the **Port Filter** text box, enter an HTTP port number in a format similar to the following:  
  
     `80`  
  
7.  Click **OK** to exit the **Advanced Settings** dialog.  
  
8.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
9. Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
10. While Message Analyzer is running, attempt to reproduce the conditions that cause the connection issues that the client is experiencing.  
  
     Captured HTTP messages start to accumulate in the **Analysis Grid** viewer.  
  
11. At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
12. Ensure that the **Field Chooser** **Tool Window** is displayed. If it is not, then select it from the **Windows** submenu that appears in the global Message Analyzer **Tools** window.  
  
13. In the **Field Chooser**, scroll down to the **HTTP** message hierarchy, click its expansion node, and then expand the **Response** node.  
  
14. Under the **Response** node, double-click the **StatusCode** and **ReasonPhrase** fields to add them as new columns in the **Analysis Grid** viewer column layout.  
  
     The **StatusCode** and **ReasonPhrase** fields are populated with data values from the trace.  
  
15. Examine the **StatusCode** and **ReasonPhrase** values of the captured data to determine possible causes of connection issues.  
  
---  
  
 **More Information**   
 **To learn more** about common HTTP **StatusCode** and **ReasonPhrase** definitions, see the status code table in the [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) section of this documentation.   

---  
  
<a name="BKMK_FilterTraceResults"></a>   
## Filtering Live Trace Session Results  
 This section provides examples of possible ways to filter displayed data that was collected from live traces that utilized the **Local Network Interfaces**, **Loopback and Unencrypted IPSEC**, and **Pre-Encryption for HTTPS** **Trace Scenarios**. The types of filters that are applied consist of Address, Port, HTTP, and TCP view **Filters**.  
  
**Applying a view Filter to Local Network Interfaces Trace Results**   
The hypothetical high-level issue in this example is that a Network Administrator is trying to discover the signature of virus traffic that has been infecting client computers. The administrator takes a **Local Network Interfaces** trace for an adequate time period to ensure enough data is collected on a client computer that is potentially being infected. When viewing trace results, the administrator realizes that it contains significant lower-layer noise that should be filtered out. For example, there is a lot of traffic on the client coming from a busy SQL server that is of no interest to the administrator, so he or she decides to remove it with a view **Filter** based on the SQL server IP address. There is also considerable traffic coming from the Remote Desktop Protocol (RDP) that is servicing the client’s connection to a remote computer, which the administrator decides to remove with a view **Filter** based on a TCP port. In this example, the administrator can rule out SQL server and RDP messages when searching for virus signatures because these services are normally considered cleaned by antivirus software.  
  
#### To apply a view Filter to Local Network Interfaces trace results that removes unwanted traffic  
  
1.  On the client computer, perform steps 1 through 4 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
     Depending on your operating system, either the **Microsoft-PEF-NDIS-PacketCapture** provider or the **Microsoft-Windows-NDIS-PacketCapture** provider and its **Id** are displayed in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog.  
  
2.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
3.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the **Analysis Grid** viewer.  
  
4.  While Message Analyzer is capturing data, attempt to reproduce any conditions that you suspect might be causing client vulnerability to virus infection, if possible.  
  
5.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
6.  In the text box of the default Filter panel on the Filtering toolbar, , enter the following Filter Expression to remove unwanted SQL and RDP traffic, while substituting the actual SQL server IP address for the italic value:  
  
     `*Address != 192.168.1.1 && TCP.Port != 3389`  
  
7.  In the default Filter panel on the Filtering toolbar, click the **Apply** button to remove all bidirectional SQL and RDP traffic.  
  
8.  Examine the remaining data in the **Analysis Grid** viewer by performing established procedures for isolating and detecting the algorithms or behaviors that expose unique virus signatures.  
  
**Applying an HTTP view Filter to Loopback and Unencrypted IPSEC Trace Results**   
The hypothetical high-level issue in this example is that a Network Administrator needs to ensure that he or she can isolate *all* HTTP messages interchanged between a client computer and a web server. In this example, the administrator runs the **Loopback and Unencrypted IPSEC** **Trace Scenario** with the **Microsoft-PEF-WFP-MessageProvider** to ensure that all HTTP data is collected with a minimum of lower level noise, and then applies an HTTP view **Filter** to the trace results. To address this issue, the administrator uses the **Loopback and Unencrypted IPSEC** **Trace Scenario** to ensure capture of all HTTP traffic, rather than the **Pre-Encryption for HTTPS** **Trace Scenario** with the **Microsoft-PEF-WebProxy** provider, which captures browser traffic only. Therefore, the administrator can be confident that he or she has isolated all the HTTP traffic necessary to analyze whatever issues are occurring. In addition, Message Analyzer provides better functionality in these circumstances than Network Monitor, which returns only the HTTP headers rather than all message fragments as Message Analyzer does.  
  
<a name="BKMK_ApplyHttpViewFilter"></a>   
#### To apply an HTTP view Filter to Loopback and Unencrypted IPSEC trace results and examine all HTTP-related messages  
  
1.  On the server computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with **Microsoft-PEF-WFP-MessageProvider** information.  
  
3.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
4.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the **Analysis Grid** View.  
  
5.  While Message Analyzer is capturing data, attempt to reproduce any conditions that cause the client or web server to experience the indicated issues.  
  
6.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
7.  In the text box of the default Filter panel on the Filtering toolbar, , enter the following atomic Filter Expression:  
  
     `HTTP`  
  
8.  Click the **Apply** button on the default Filter panel to isolate all HTTP Operations and other messages that contain HTTP in the message stack.  
  
 > [!NOTE]
 >  Alternatively, select **HTTP** from the **Viewpoints** drop-down list on the Filtering toolbar to isolate all HTTP messages at top-level, so you can see the trace results from the perspective of the HTTP protocol. In addition, you can click the **Flat Message List** button the Filtering toolbar to break out all HTTP Operations (request and response messages) into their original chronological order, similar to the Network Monitor view, for a different analysis perspective.  
  
9. In the **Analysis Grid** viewer, click the message expansion nodes to expose the HTTP message origins tree for HTTP messages of interest.  
  
     Alternatively, add **StatusCode** and **ReasonPhrase** columns to the **Analysis Grid** viewer from the **Field Chooser** **Tool Window** and execute the **Group** command on the **StatusCode** and **ReasonPhrase** columns to create groups of identical HTTP status codes, for ease of analysis.  
  
10. Examine the filtered data to determine possible causes of any issues experienced by the client or web server, as appropriate. See [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) for HTTP status code information.  
  
**Applying TCP view Filters to Loopback and Unencrypted IPSEC Trace Results**   
The hypothetical high-level issue in this example is that a Network Administrator has one or more client computers that are believed to be experiencing TCP connection and/or data transmission problems such as the following:  
  
-   Dropped packets or lost TCP segments.  
  
-   Slow data transmission rates related to TCP window size and scaling.  
  
-   Incomplete connection request handshakes.  
  
In this scenario, the administrator identifies common TCP connection and data transmission issues by writing and applying various Filter Expressions to expose data that can reveal the potential causes of such problems. The procedure that follows provides examples of Filter Expressions that the administrator applies to isolate the values of various TCP fields, to determine whether any problems exist in these areas.  
  
> [!TIP]
>  When troubleshooting TCP connection issues, Message Analyzer users should learn the meaning of all the TCP analysis flags so they can write filters to isolate and analyze the information they provide.  
  
<a name="BKMK_ApplyTCPViewFiltersProc"></a>   
#### To apply TCP view Filters to Loopback and Unencrypted IPSEC trace results and expose TCP diagnostics  
  
1.  On the server computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with **Microsoft-PEF-WFP-MessageProvider** information.  
  
3.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
4.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the **Analysis Grid** View.  
  
5.  While Message Analyzer is capturing data, attempt to reproduce the conditions where TCP connection issues are occurring on target client computers.  
  
6.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
7.  If the **Field Chooser** **Tool Window** is not displayed, click the **Add Columns** button in the **Analysis Grid** viewer toolbar to display it.  
  
8.  In the **Field Chooser** window, scroll to the **TCP** protocol and click its expansion node to expose the TCP message hierarchy.  
  
9. In the **TCP** message hierarchy, expand the **Segment** node and then double-click the **TCPDiagnosis**, **SYN** flag, **ACK** flag, **Window**, and **Options** fields to add them as new data columns in the **Analysis Grid** viewer column layout.  
  
 > [!NOTE]
 >  Adding these fields to the column layout enables you to view the corresponding values of these fields as you apply the filters throughout this procedure.  
  
10. In the text box of the default Filter panel on the Filtering toolbar, enter the following Filter Expression:  
  
     `TCP#DiagnosisLevels`  
  
11. On the default Filter panel , click the **Apply** button to filter the **Loopback and Unencrypted IPSEC** trace results and verify whether you have any TCP-related errors.  
  
12. If the filter in the previous step exposes TCP errors in the **TCPDiagnosis** column of the **Analysis Grid** viewer, you can isolate and view this data in several ways, as described in the steps that follow.  
  
13. To isolate lost or out-of-order TCP segments, enter the following Filter Expression in the text box of the default Filter panel and then click **Apply** to start the filtering process:  
  
     `*TCPDiagnosis contains "Segment-Lost"`  
  
     If you want to look at top-level TCP messages only and use a quicker performing filter, apply the following Filter Expression to the trace:  
  
     `\TCP::TCPDiagnosis contains "Segment-Lost"`  
  
14. To focus on TCP message **Window** size, which can reduce the data transmission rate when too small (see [TCP Category](filtering-live-trace-session-results.md#BKMK_TransportExamples)), apply the following filter to the trace, while adjusting the italic **Window** size value in the filter as appropriate:  
  
     `TCP::WindowScaled < 1000`  
  
15. To verify whether **WindowsScaleFactor** is operative or whether other TCP **Options** are correctly set for optimal performance, apply the following filter to return *only* TCP messages that have **Options** set:  
  
     `TCP::Options ~= nothing`  
  
 > [!NOTE]
 >  If you are interested in examining the IP conversations where the TCP options were negotiated, along with the TCP ports that carried the traffic, add an  IP **Network** column and a TCP **Transport** column to the **Analysis Grid** viewer column **Layout** and then perform the **Group** function on these  columns to quickly reorganize the data into common groups. If you use this method, make sure to right-click the **Network** and **Transport** group labels  and select the **Expand All Groups** menu command to expose all the data.  
   
 When you are viewing the TCP **Option** configuration, you might want to do the following:  

 - Ensure that **Selective Acknowledgement (SACK)** is enabled, to minimize TCP retransmits.  
 - Verify that the **Maximum Segment Size (MSS)** is set to a reasonable value to reduce fragmentation.  
 - Ensure that the **WindowsScaleFactor** function is operative and set to a reasonable value for the **Window** size setting, to enable automatic resize of the receive TCP **Window** as necessary.  
  
16. To display statistics associated with all the TCP three-way handshakes in a set of trace results, execute the **TCP Three-Way Handshake** pattern expression in the **Pattern Match** viewer, which is accessible from the **New Viewer** drop-down list on the global Message Analyzer toolbar. When the **Pattern Match** viewer is open, click the  **TCP Three-Way Handshake** pattern expression in the **AVAILABLE PATTERNS** list. If any matches are found, they appear in the Matched pattern selector in the **MATCHES** pane of the viewer. To review the discovered data, click the Matched pattern selector to display all instances of TCP three-way handshake patterns and the associated TCP data.  
  
  ---  
    
  **More Information**   
  **To learn more** about the **TCP Three-Way Handshake** and other pattern expressions, see [Understanding Message Pattern Matching]  (understanding-message-pattern-matching.md).  
  
  ---  
    
  Otherwise, you can perform manual filtering such as the following in an attempt to  locate  incomplete TCP three-way handshake patterns in a trace along   with surrounding messages potentially related to a failure:  
  
  - Click the **Viewpoint** drop-down list on the Filtering toolbar and then select the **TCP** **Viewpoint** to display all TCP messages at top-level.  
  - Click the **Find Message** button on the **Analysis Grid** viewer toolbar.  
  - Enter any of the following Filter Expressions in the **Find Message** text box and then successively click the **Find** binoculars icon to locate messages that meet the specified filtering criteria:  

    TCP::TCPDiagnosis contains "Segment-Lost"   
    TCP::AcknowledgementNumber==0  
    TCP::Flags.Syn==true && TCP::Flags.Ack==true  

  You can use the method described immediately above to find TCP messages that   participated in incomplete three-way handshake operations. By locating the TCP   messages that contain TCP **Options** and broken or incomplete patterns of   **SYN**, **ACK**, **SequenceNumber**, and **AcknowledgementNumber** field   values, you may be able to determine where failures have occurred.  
  
  For reference, the following table specifies the pattern of **SYN** and **ACK** field values, with the relative **SequenceNumber** and **AcknowledgementNumber** value representations, that exposes the signature of a three-way handshake pattern that successfully opened a TCP connection:  
  
  ### Table 25.  Three-way Handshake Signature  
  
  |Computer Node|Message Sent|SYN Flag Value|ACK Flag Value|SequenceNumber|  AcknowledgementNumber|TCP Options|  
  |-------------------|------------------|--------------------|  --------------------|--------------------|---------------------------|  -----------------|  
  |Sending|Connection request|True|False|x|0|Yes|  
  |Receiving|Request acknowledgement|True|True|y|x+1|Yes|  
  |Sending|Sync acknowledgement|False|True|x+1|y+1|No|  
  
  > [!NOTE]
  >  Keep in mind that incomplete handshakes can appear in a trace if the capture time frame did not synchronize with a TCP transmission or if the network dropped packets.  
  
 **Applying a view Filter to Pre-Encryption for HTTPS Trace Results**   
The hypothetical high-level issue in this example is that a Network Administrator of a site has web clients that complain about slow responses when attempting to connect with and retrieve data from one or more web servers. With the use of the Message Analyzer **Pre-Encryption for HTTPS** **Trace Scenario** running on a client computer that is having the most issues, the administrator can quickly determine which servers are having connection or performance problems. In the procedure that follows, the administrator applies HTTP view **Filters** against data that is displaying in the **Analysis Grid** viewer, to obtain a clear picture of which servers are experiencing performance issues. To this end, the view **Filters** help the administrator accomplish the following:  
  
-   Isolate HTTP operations where server responses are slow, as indicated by high **ResponseTime** values.  
  
-   Isolate HTTP **StatusCode** values that were received, along with accompanying **ReasonPhrases**, to pinpoint any client or server errors that occurred during HTTP message exchanges.  
  
#### To apply an HTTP view Filter to Pre-Encryption for HTTPS trace results and expose HTTP status codes  
  
1.  On the client computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Pre-Encryption for HTTPS** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with the **Microsoft-Pef-WebProxy** provider information.  
  
3.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
4.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
     The captured messages start to accumulate in the **Analysis Grid** View.  
  
5.  While Message Analyzer is running, perform some HTTP requests from client computers that are experiencing slow connection or data retrieval problems with one or more web servers that are suspected of being overburdened and performing poorly.  
  
     The captured HTTP messages start to accumulate in the **Analysis Grid** View.  
  
6.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
7.  Ensure that the **Field Chooser** **Tool Window** is displayed. If it is not, click the **Add Columns** button on the **Analysis Grid** viewer toolbar to display it.  
  
8.  In **Field Chooser**, scroll to the **HTTP** protocol and click its expansion node to expose the **HTTP** message hierarchy.  
  
9. In the **HTTP** message hierarchy, locate the **StatusCode** and **ReasonPhrase** fields under the **Response** node and double-click each one to add it as a new column in the **Analysis Grid** viewer column **Layout**.  
  
10. In the **Field Chooser** window, open the **Global Annotations** node and then double-click the **ResponseTime** annotation to add it as a new column in the **Analysis Grid** viewer.  
  
11. Click the **Viewpoint** drop-down list on the Filtering toolbar and select **HTTP** to apply an HTTP viewpoint that pushes all HTTP messages to top-level with no messages above them, for ease of analysis.  
  
12. In the text box of the default Filter panel on the Filtering toolbar, enter the following Filter Expression:   
    `#ResponseTime >=1`  
  
13. On the default Filter panel, click the **Apply** button to apply the filtering and isolate the HTTP operations where the server response to client requests is greater than or equal to 1 second.  
  
     Operations that meet the **ResponseTime** criteria of the applied filter would likely indicate excessive server response times, providing that the **TimeElapsed** for the entire operation is a reasonable value. Note that if the **TimeElapsed** is also taking a while, this could be an indication of network issues rather than a slowly responding server.  
  
 > [!NOTE]
 >  The **ResponseTime** is the difference between the **Timestamp** value of the first response message from the server minus the last **Timestamped** value in the request message stack.  
  
14. Click the **Show Column Filter Row** icon in the upper-left corner of the **Analysis Grid** viewer to display the amber-colored **Column Filter** text box row.  
  
15. Isolate specific HTTP **StatusCodes** in the trace by typing “10”, “20”, “30”, “40”, or “50” into the **Column Filter** text box beneath the **StatusCode** column header, as appropriate, or enter a specific **StatusCode** for which you are looking, for example “408”.  
  
     The column is filtered according to the value you specified.  
  
16. Examine the different **StatusCodes** and **ReasonPhrases** to determine any problem areas that might provide some additional indications as to why the web server is performing poorly. To review the definitions of key **StatusCodes** and **ReasonPhrases**, refer to the [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) section of this documentation.  
  
17. Analyze the **TimeElapsed** column values in the **Analysis Grid** viewer to verify whether overall HTTP operations are taking a long time.  
  
     For example, you could type “1.”, “2.”, “3.”, and so on, into the **Column Filter** text box beneath the **TimeElapsed** column to filter for messages that have an elapsed time of 1 second or greater.  
  
<a name="BKMK_FilterWithColorRules"></a>   
## Filtering with Color Rules and Exposing Diagnostics for TCP and SMB  
 The hypothetical high-level issue in this example is that a Network Administrator needs to be aware of faulty or erratic client connections or file request failures that occur during file server access, by highlighting errors representing common TCP connection issues and SMB status. In the example that follows, the administrator runs the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario** to take advantage of the **Microsoft-PEF-WFP-MessageProvider** that captures data above the IP/Network Layer, along with a **Session Filter** that isolates traffic on SMB port 445. The administrator then does the following:  
  
-   Creates a new right-gradient **Color Rule** to highlight TCP diagnostic information.  
  
-   Adds a **TCP.TCPDiagnosis** column to enable quick examination of TCP errors that appear in the trace.  
  
-   Creates a new left-gradient **Color Rule** to highlight SMB error status.  
  
-   Adds an **SMB2.ErrorResponse.Header.Status.Value** column to enable quick examination of SMB2 error values that appear in the trace.  
  
-   Uses the **Color Rule** highlighting as a prompt to perform various operations for error analysis.  
  
#### Applying Color Rules to Network Tunnel Traffic and Unencrypted IPSEC Trace Results and Exposing Diagnostics  
  
1.  On the client computer, perform steps 1 through 3 of the previous procedure: [To filter data on a specific network interface in a Local Network Interfaces trace](procedures-using-the-data-filtering-features.md#BKMK_AdapterFilteringLocNetworkIFaces).  
  
2.  From the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog, select the **Network Tunnel Traffic and Unencrypted IPSEC** **Trace Scenario**.  
  
     The **ETW Providers** list is populated with **Microsoft-PEF-WFP-MessageProvider** information.  
  
3.  In the **Session Filter** text box of the **New Session** dialog, enter the following Filter Expression:  
  
     `TCP.Port == IANA.Port.SMB`  
  
4.  Verify that the **Analysis Grid** viewer is selected in the **Start With** drop-down list in the **New Session** dialog. If it is not, then select it.  
  
5.  Click the **Start** button in the **New Session** dialog to begin capturing data.  
  
6.  While Message Analyzer is capturing data, perform some file share access from the client computer to a file server or other location where access problems are known to be occurring.  
  
     The messages captured on the SMB port start to accumulate in the **Analysis Grid** viewer.  
  
7.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
8.  Create and save a new **Color Rule** with a right-gradient pattern and the following Filter Expression, to highlight any TCP messages where Application-type error events might have occurred, such as lost or incomplete segments, missing three-way handshakes, duplicate ACKs, retransmits, and so on, to expose any possible TCP connection issues:  
  
     `TCP#DiagnosisTypes`  
  
     If TCP diagnosis errors occurred in your trace, they are immediately flagged in the **Analysis Grid** viewer by the **Color Rule** configuration that you created. If you leave this **Color Rule** applied, these errors will continue to be flagged in the **Analysis Grid** viewer until you specifically disable the rule.  
  
     For more information about creating and saving **Color Rules**, see [Using and Managing Color Rules](using-and-managing-color-rules.md).  
  
9. In the **Field Chooser** **Tool Window**, navigate the TCP message hierarchy to the **TCP.Segment** level and add the **TCPDiagnosis** field as a new column in the **Analysis Grid** viewer by using the right-click **Add as Column** command in the **Field Chooser** context menu, so the you can easily view TCP error descriptions.  
  
10. Create and save a new **Color Rule** with a left-gradient pattern and the following Filter Expression, to highlight SMB **Status** errors that might have occurred during file share access:  
  
     `SMB2.ErrorResponse.Header.Status.Value > 0`  
  
     This **Color Rule** is also immediately applied to your trace results, in the previously indicated manner.  
  
 > [!NOTE]
 >  You can leave these **Color Rules** in the applied state so that any messages with TCP diagnostics and SMB errors are automatically displayed whenever you run a trace. Unless you specifically disable **Color Rules**, they remain enabled for all Message Analyzer **Trace Scenarios** with which you  capture data.  
  
11. In the **Field Chooser** window, navigate the SMB message hierarchy to the **SMB2.ErrorResponse.Header.Status** level and add the **Value** field as a new column to the **Analysis Grid** viewer, so you can examine the values of any SMB errors that might have occurred.  
  
12. Perform the following operations to expose TCP diagnosis messages for analysis purposes:  
  
    -   Display TCP messages at top-level to improve analysis by applying the **TCP Layer** **Viewpoint** from the **Viewpoints** drop-down list on the Filtering toolbar.  
  
    -   Analyze TCP error messages as appropriate to determine various TCP issues.  
  
         For example, apply a **Column Filter** to the **TCPDiagnosis** column in the **Analysis Grid** viewer with the text “retransmit”, to isolate all error messages that contain the text “Retransmitted” in the description. Then apply an “ack” **Column Filter** to isolate all error messages that contain the text “Dup-Ack” in the description. You can do the same for "Segment-Lost".  
  
13. Perform the following operations to expose SMB error messages and other statistics for analysis purposes:  
  
    -   Break apart the SMB2 request and response messages from their Operation nodes by applying the **SMB/SMB2 Disable Operations** **Viewpoint** from the **Viewpoint** drop-down list on the Filtering toolbar.  
  
    -   Focus on SMB2 error messages by applying the  filter `SMB2.ErrorResponse.Header.Status.Value > 0` as a view **Filter** that you specify in the text box of the default Filter panel.  
  
         To view the filenames where such errors occurred, add an SMB2  **QueryInfoRequest.Filename** column to the **Analysis Grid** viewer with the use of the **Add as Column** context menu command in **Field Chooser**. You can then correlate the errors and filenames.  
  
         At this point, you might also invoke one of the SMB **Layouts** for the **Chart** viewer to obtain further statistics for analysis. For example, you might  select the **SMB File Stats** view **Layout** from the **Chart** drop-down  list in the **New Viewer** menu on the global Message Analyzer toolbar.