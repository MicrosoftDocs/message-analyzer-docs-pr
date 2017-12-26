---
title: "Procedures: Quick Start | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2a7e42c0-592f-4ebd-95eb-557111d168db
caps.latest.revision: 88
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Quick Start

This section contains simple procedures that you can run to start coming up to speed on Message Analyzer features.

---

 **Go To Procedures**  
 Proceed to the procedures listed immediately below to learn how to use Message Analyzer features and functions to accomplish basic tasks such as the following:

---

 [Displaying Data Quickly From a Saved Trace File](procedures-quick-start.md#BKMK_quickdisplaytracedata)
 [Starting a Live Trace Session with a Built-In Trace Scenario](procedures-quick-start.md#BKMK_startlivecapture)
 [Starting a Data Retrieval Session](procedures-quick-start.md#BKMK_browseSessionLoadData)
 [Modifying an Existing Data Retrieval Session](procedures-quick-start.md#BKMK_ModifyDRSession)
 [Displaying Different Data Viewers to Change Analysis Perspectives](procedures-quick-start.md#BKMK_displaySummaryViews)
 [Creating and Saving a Customized Trace Scenario](procedures-quick-start.md#BKMK_createSaveScenarioTemplate)

> [!NOTE]
>  Although these procedures demonstrate the use of Message Analyzer capabilities in some basic scenarios, they are only a sampling of what you can accomplish with Message Analyzer, given that you can also apply the methodologies described here to many other scenarios. This is also true of other procedural content in this Operating Guide.

> [!IMPORTANT]
>  If you have not logged off from Windows after the first installation of Message Analyzer, please log off and then log back on before performing these procedures. This action ensures that in all subsequent logons following installation, your security token will be updated with the required security credentials from the Message Capture Users Group. Otherwise, you will be unable to capture network traffic in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapture** provider, **Microsoft-Windows-NDIS-PacketCapture** provider, or the **Microsoft-PEF-WFP-MessageProvider**, unless you start Message Analyzer with the right-click **Run as administrator** option.

<a name="BKMK_quickdisplaytracedata"></a>
## Displaying Data Quickly From a Saved Trace File
 The procedure that follows shows you how to use the Message Analyzer **Open** feature to rapidly access and display data from a saved trace or log file.

#### To quickly open a saved trace file and display its data

1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. Start Message Analyzer with the right-click **Run as Administrator** option if necessary, as described in the previous **Important** note.

2.  Click the global Message Analyzer **File** menu and then click **Open** to display the Windows **Open** dialog.

    > [!TIP]
    >  If you have already opened files with the **Open** command, a **Recent Files** item is available just below the **Open** command on the **File** menu that displays a submenu to the right, from where you can select a file and immediately open it in the default data viewer.

3.  In the **Open** dialog that displays, navigate to a saved trace or log file containing the data you want to display and then click the **Open** button to exit the dialog.

     The saved data displays in the default data viewer.

> [!TIP]
>  You can quickly retrieve data from one or more saved trace files by dragging and dropping them almost anywhere on the Message Analyzer user interface. In drag-and-drop mode, the data retrieved from each file in a selected set is aggregated into a single default session viewer tab. Note that the drag-and-drop function does not work if you are running Message Analyzer as an Administrator, due to varying security contexts that can occur between applications.

 You can also drag and drop \*.log files to display their data. However, instead of the data immediately displaying in the default data viewer, the **New Session** dialog opens to the Data Retrieval Session input configuration, with the log file/s that you selected as the data source/s for the session. This gives you the opportunity to specify a **Text Log Configuration** file, which is required for parsing \*.log files (unless you have already specified a default configuration file on the **General** tab of the **Options** dialog to use for all *.log files, in which case Message Analyzer immediately begins loading the data).

 Note that you  can specify other session input configurations that include a **Time Filter**, **Session Filter**, or **Parsing Level**, to define the scope of messages to be retrieved.  You  can also set the **Truncated Parsing** mode, add more files to the session as data sources, and specify the data viewer you want to use.

---

 **More Information**
 **To learn more** about additional configuration capabilities for a Data Retrieval Session, see [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md).

---

<a name="BKMK_startlivecapture"></a>
## Starting a Live Trace Session with a Built-In Trace Scenario
 The procedure that follows shows you how to select the built-in **Loopback and Unencrypted IPSEC** **Trace Scenario** that uses the **Microsoft-PEF-WFP-MessageProvider** to focus your live data capture above the Network Layer, while minimizing lower-level network traffic. Although this scenario enables you to capture loopback and unencrypted IPSec traffic, this is not the focus of this example.

> [!TIP]
>  To start a Live Trace Session immediately with no further configuration, you can simply click the **Loopback and Unencrypted IPSEC** **Trace Scenario** in the **Favorite Scenarios** list on the **Start Page**, where this scenario is accessible by default. You can also locate it in the submenu of the **Favorite Scenarios** item in the Message Analyzer **File** menu to quickly start a Live Trace Session with this scenario. Note that you can set any **Trace Scenario** to Favorite status at your discretion and it will appear in these locations to enable quick session startup.

#### To start a Live Trace Session with the Loopback and Unencrypted IPSEC trace scenario

1.  Launch Message Analyzer as specified in the previous procedure.

2.  Click the global Message Analyzer **File** menu and then click the **New Session** item to display the **New Session** dialog.

3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features contained in the **New Session** dialog.

4.  Select the **Loopback and Unencrypted IPSEC** item in the **Select Scenario** drop-down menu on the **ETW Providers** toolbar of the **Live Trace** tab in the **New Session** dialog.

     The **Microsoft-PEF-WFP-MessageProvider** is added to the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog.

5.  Optionally, select a built-in **Session Filter** from the centralized Filter Expression **Library**, such as `IPv4Address==<192.168.1.1>` to capture messages that are sent to and received from a specific computer only. The IP address in this example filter is a placeholder for an actual IP address that you must provide.

    > [!NOTE]
    >  A **Session Filter** enables you to define the scope of the data capture while at the same time improve performance by limiting how much data you collect.

6.  Click the **Start With** drop-down arrow and select the data viewer in which to display your trace results, or use the default **Analysis Grid** data viewer setting.

7.  Click the **Start** button in the **New Session** dialog to start capturing data in your Live Trace Session.

8.  While the Live Trace Session is running, launch a web browser and click some links to navigate to several web locations. Alternatively, you can start some network application.

     Message Analyzer starts to accumulate messages in the data viewer that you specified.

9. Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.

     Inspect your trace results in the data viewer that you chose and observe that Message Analyzer has captured a set of messages, including HTTP, as a result of the browser links that you clicked.

---

     **More Information**
     **To learn more** about how you might analyze HTTP and TCP message data, see the following topics for some examples of how to apply HTTP and TCP view **Filters** in an Analysis Session:
    [To apply an HTTP view Filter to Loopback and Unencrypted IPSEC trace results and examine all HTTP-related messages](procedures-using-the-data-filtering-features.md#BKMK_ApplyHttpViewFilter)
    [To apply TCP view Filters to Loopback and Unencrypted IPSEC trace results and expose TCP diagnostics](procedures-using-the-data-filtering-features.md#BKMK_ApplyTCPViewFiltersProc)
    **To learn more** about the configuration capabilities that are available for a Live Trace Session, see [Configuring a Live Trace Session](configuring-a-live-trace-session.md).

---

> [!CAUTION]
>  Be aware that if you let a trace session run for an extended period, it can consume a large amount of memory.

<a name="BKMK_browseSessionLoadData"></a>
## Starting a Data Retrieval Session
 The procedure in this section shows you how to open the input configuration for a  Message Analyzer Data Retrieval Session, from where you can specify one or more saved files that contain the message data you want to load and display in the **Analysis Grid** viewer. The option to create a filtered view of the loaded data with the use of a **Session Filter** is also described.

#### To use a Data Retrieval Session to load saved trace data into Message Analyzer

1.  Launch Message Analyzer as indicated in earlier procedures.

2.  On the **Start Page**, click the **New Session** button to display the **New Session** dialog.

3.  Under **Add Data Source** in the **New Session** dialog, click the **Files** button to display the **Files** tab along with the associated session configuration features that the dialog contains.

4.  On the **Files** tab, click the **Add Files** button to display the **Open** dialog, from where you can navigate to the trace files that contain the data you want to load into Message Analyzer.

5.  In the **Open** dialog, select the file/s that contain the data you want to retrieve, then click the **Open** button to exit the dialog.

     Message Analyzer displays the files you selected in a list on the **Files** tab that includes columns of data such as **Name**, file **Size**, **File Type**, **Message Count**, **Start Time**, **End Time**, and **Text Log Configuration**.

    > [!NOTE]
    >  The data from the files that display in this list is not yet loaded into Message Analyzer. At this point, the files are simply the target data sources from which data will be loaded after you click the **Start** button in the **New Session** dialog.

6.  In the files list, ensure that there is a check mark in the check box next to the file/s containing the data you want to load into Message Analyzer. Note that you can select or unselect files in the list to create specific combinations of data sources from which to load data.

7.  In the **Start With** drop-down menu of the **New Session** dialog, select a data viewer in which to display the results of your Data Retrieval Session; otherwise, the default data viewer setting will be used.

    > [!TIP]
    >  You have the option to change the default data viewer from the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. Note that Message Analyzer ships with the **Analysis Grid** viewer as the default setting, as specified in the **Default Profile** pane of the **Profiles** tab.

8.  Optionally, select a **Session Filter** from the Filter Expression **Library** in the **New Session** dialog, or configure a **Time Filter** from the **Files** tab in the dialog to define the scope of data retrieval or to narrow the window of time in which to view data, respectively.

---

     **More Information**
     **To learn more** about applying a **Session Filter** and/or a **Time Filter**, see [Selecting Data to Retrieve](selecting-data-to-retrieve.md).

---

9. Click the **Start** button in the **New Session** dialog to begin loading the data into Message Analyzer.

     After the data is loaded, it displays in the default or selected data viewer.

---

     **More Information**
     **To learn more** about how to manipulate and analyze saved trace data that you have loaded into the Message Analyzer **Analysis Grid** viewer, see the following sections:
    [Analysis Grid Viewer](analysis-grid-viewer.md)
    [Common Data Viewer Features](common-data-viewer-features.md)
    [Tool Windows](tool-windows.md)
    [Filtering Live Trace Session Results](filtering-live-trace-session-results.md)

---

<a name="BKMK_ModifyDRSession"></a>
## Modifying an Existing Data Retrieval Session
 If you want to modify an existing Data Retrieval Session so that you can load additional data from one or more files, for example saved traces and logs, or if you want to specify other configurations that include a **Session Filter**, perform the steps of the following procedure.

#### To modify an existing Data Retrieval Session

1.  Load data into Message Analyzer through a Data Retrieval Session, as described in the previous procedure.

2.  On the global Message Analyzer toolbar, click the **Edit Session** button to return to the original configuration of the currently in-focus Data Retrieval Session. If you have data for more than one session displaying, ensure that you select a viewer tab for the Data Retrieval Session that you want to modify before you click **Edit Session**.

3.  On the **Files** tab of the **New Session** dialog, click **Add Files** to add one or more saved trace files to the files list and then select the check box next to each file containing the data you want to load into Message Analyzer.

    > [!IMPORTANT]
    >  When you click the **Edit Session** button on the global Message Analyzer toolbar, by default your Data Retrieval Session opens in **Restricted Edit** mode. This mode enables you to add saved files as new data sources, but it disables other configuration capabilities, such as setting a **Time Filter**, choosing a **Session Filter**, or setting the **Parsing Level**.
    >
    >  The advantage of the **Restricted Edit** mode is that you can add the new data files without triggering a reload of all data and incurring a performance hit. However, if you want to enable the indicated configuration features to specify changes, you can select the **Full Edit** mode, although you should be aware that a reload of all data will be required if you **Apply** the changes.

4.  When you are done with reconfiguring the session, click the **Apply** button to load and display the new data in the **Analysis Grid** viewer.

    > [!NOTE]
    >  When you load data from additional files in an edited Data Retrieval Session, the messages from these files are interlaced with the existing messages in the **Analysis Grid** viewer in chronological order.

 **Configuring a Session Filter**
When loading data from saved files into Message Analyzer, you can select a built-in Filter Expression from the **Library** drop-down list above the **Session Filter** text box, or you can manually configure one in the  same text box. This results in filtering the input messages to specific criteria.

 For example, you might add a simple expression such as `*Port != IANA.Port.LDAP` from the **Library** drop-down list to remove LDAP traffic on TCP and UDP transports, if you don't want to  view this data. Note that if you manually configure a Filter Expression and it is invalid, you may receive a **Compile query error** message after you click the **Apply** button in the **New Session** dialog.

> [!TIP]
>  After loading a collection of messages from specified files and displaying the data in a selected viewer, you have the option to add a built-in or manually-configured view **Filter** to further isolate specific data of interest. The centralized Filter Expression **Library** for selecting built-in **Filters** is available on the Filtering toolbar that appears above every session viewer.

---

 **More Information**
 **To learn more** about how to manually configure your own Filter Expressions, see [Writing Filter Expressions](writing-filter-expressions.md).

---

<a name="BKMK_displaySummaryViews"></a>
## Displaying Different Data Viewers to Change Analysis Perspectives
 The procedure that follows runs a the **Loopback and Unencrypted IPSEC** **Trace Scenario** in a Live Trace Session and then loads a message collection to create initial data views in separate **Analysis Grid** viewer tabs. You will then select several different data viewers that provide high-level data summaries and statistics, some in graphic formats.

#### To display different data viewers

1.  Follow the guidelines of the second procedure in this section to start a Live Trace Session with the **Loopback and Unencrypted IPSEC** **Trace Scenario**.

2.  Capture SMB traffic by performing file access activities while your Live Trace Session is running.

     Note that the **Microsoft-PEF-WFP-MessageProvider** in the **Loopback and Unencrypted IPSEC** **Trace Scenario** captures data above the IP/Network Layer, which makes it a good choice for capturing SMB traffic at the Application Layer while minimizing lower layer noise.

    > [!TIP]
    >  You might consider using the **SMB2 Client Full Payloads** **Trace Scenario** to capture SMB traffic unencrypted.

3.  Stop the Live Trace Session at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.

4.  Load messages from one or more saved trace files (preferably related SMB data, if you have it) into Message Analyzer through a Data Retrieval Session by following the guidelines of the third procedure in this section.

     The trace results and loaded data display in separate **Analysis Grid** viewer tabs, assuming that you specified the **Analysis Grid** as your data viewer in the **New Session** dialog for your Live Trace Session and Data Retrieval Session configurations.

5.  If the **Session Explorer** **Tool Window** is hidden, click the global Message Analyzer **Tools** menu, select the **Windows** submenu, and then click the **Session Explorer** item to restore it to the default location.

6.  To create different views of the live trace results data (in addition to the existing **Analysis Grid** viewer instance), right-click the live trace session node in **Session Explorer**, highlight **New Viewer**, select **Chart** in the drop-down list, and then select the **SMB File Stats** view **Layout** so that you can analyze file access duration times, bytes transferred, and data transmission rate for each file name in a set of trace results.

     You might also display the **SMB Top Commands** view **Layout** to obtain a high-level overview of message volume per file access operation, as an indication of the SMB operations consuming the most bandwidth.

     Note that each viewer in the same session is identified by a unique color code. Therefore, the color code for each viewer in the Live Trace Session will be the same, while at the same time different from that of the viewer for the Data Retrieval Session in which you loaded data from saved files into Message Analyzer.

---

     **More Information**
     **To learn more** about the **Layouts** that are available for the **Chart** viewer, see the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.

---

7.  Double-click any bar element in the **SMB Top Commands** **Bar** graph visualizer component **Layout** to display the corresponding SMB messages in a separate **Analysis Grid** session viewer tab for further analysis.

8.  Repeat step 6  and select the **SMB Reads and Writes** **Layout** for the **Chart** viewer to display SMB statistics in the **Timeline** visualizer component.

    > [!IMPORTANT]
    >  These viewers will display data only if SMB, SMB2, or SMB3 protocol packets were captured in the Live Trace Session that you ran.

9. Right-click the node for the Data Retrieval Session in **Session Explorer**, highlight **New Viewer**, select the **Grouping** viewer, and then select the **Process Name and Conversations** view **Layout** in the drop-down list that appears.

     Note that the hierarchy of message groups that display for this **Layout** isolate trace data into nested groups consisting of **ProcessName**, **ProcessId**, **Network** (IP conversations), and **Transport** (ports that carried the IP conversations), to enable a focused analytical perspective. By clicking any Group in the hierarchy, you can drive the display of Group messages into the **Analysis Grid** viewer for inspection of associated message data. If you are a Microsoft Network Monitor user, you might notice that this particular **Layout** is similar to the **Network Conversation Tree**.

10. While the **Grouping** viewer has focus, click the **Layout** drop-down list on the **Grouping** viewer toolbar and select the **File Sharing SMB/SMB2** view **Layout** from the **File Sharing** category, to isolate the data by SMB **SessionIdName**, **TreeIdName**, and **FileName**.

     This will enable you to drill down into the hierarchically organized Group display to analyze the messages associated with each file, as nested under the SMB session and tree IDs. for example to search for diagnostic errors. Note that when you select any Group node under the **Group Values** column of the **Grouping** viewer, you will display the messages associated with the selected Group node in the **Analysis Grid** viewer for further analysis, provided that the **Filtering Mode** is enabled on the **Grouping** viewer toolbar. If the **Selection Mode** is enabled, selecting a Group will only highlight the associated messages in the **Analysis Grid** viewer.

---

     **More Information**
     **To learn more** about the **Grouping** viewer, including the **Filtering Mode** and **Selection Mode** of operation, refer to the [Grouping Viewer](grouping-viewer.md) topic.

---

11. Next, right-click the node for the Data Retrieval Session in **Session Explorer**, highlight **New Viewer**, and then select **Pattern Match** to display the **Pattern Match** viewer.

     To start the **Pattern** matching process, specify a built-in **Pattern** expression in the **AVAILABLE PATTERNS** list of the **Pattern Match** viewer, by selecting the check box of a chosen **Pattern** expression. For example, you might select the **TCP Retransmit Pairs** or **TCP Three-Way Handshake** **Pattern** expression to identify these types of sequential pattern matches across the retrieved message set, possibly to expose network or connectivity issues, respectively.

---

     **More Information**
     **To learn more** about **Pattern** matching, refer to the [Pattern Match Viewer](pattern-match-viewer.md) topic.

---

12. To quickly vary your analysis perspectives, poll through the various views of data by clicking the viewer nodes under each session name in **Session Explorer**, or select different viewer tabs in the Message Analyzer main analysis surface.

     As you select viewer nodes in **Session Explorer**, the data for each of the selected viewer nodes displays in separate viewer tabs in the main analysis surface. As you poll the data views, you obtain unique perspectives that enhances your analysis of the data.

13. Optionally, to obtain alternate but integrated views of the saved message data, select the **Message Stack** **Tool Window** from the **Windows** submenu of the global Message Analyzer **Tools** menu, if the window is not already open, to expose the underlying message stack that supported top-level transactions. Also select the **Diagnostics** **Tool Window** from the same menu location to display summary groups of the different types of diagnosis errors that occurred in the retrieved data.

    > [!IMPORTANT]
    >  The **Diagnostics** window is currently a preview feature. To use this tool, you must enable it on the **Features** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu, and you must then restart Message Analyzer.

> [!TIP]
>  You can compare Live Trace Session results with related data that is loaded into Message Analyzer from a Data Retrieval Session. This provides a convenient method for analyzing current and historical data side-by-side. To learn how to display data viewer tabs side by side, see [Redocking Data Viewers and Tool Windows](working-with-message-analyzer-window-layouts.md#BKMK_RedockViewersToolWindows).

<a name="BKMK_createSaveScenarioTemplate"></a>
## Creating and Saving a Customized Trace Scenario
 In the procedure that follows, you will create and save a **Trace Scenario** to serve as a trace template with predefined tracing functionality that you can run on demand. The **Trace Scenario** specified in this simple example enables you to isolate traffic to a specific IP address, where you can use two different methods of filtering to achieve that result.

#### To create and save a Trace Scenario

1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.

2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.

3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that the **New Session** dialog provides.

4.  Select the **Local Network Interfaces** **Trace Scenario** in the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog.

    > [!NOTE]
    >  If you are running the Windows 7, Windows 8, or Windows Server 2012 operating system, the **Microsoft-PEF-NDIS-PacketCapture** is added to the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. Otherwise, for later operating systems, the **Microsoft-Windows-NDIS-PacketCapture** provider (with remote capabilities) is added to the list.

5.  In the earlier operating system scenario, click the **Configure** link to the right of the **Microsoft-PEF-NDIS-PacketCapture** provider in the **ETW Providers** list to display the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog. Select the **Provider** tab in the dialog and then specify the configurations that follow:

    -   In the **Name** column under **System Network**, expand the **Machine** node, and then under **Adapters**, make sure that the **In** and **Out** check boxes for the Ethernet network adapter are selected. This ensures that the **Trace Scenario** will capture both inbound and outbound traffic on the Ethernet adapter. Deselect these check boxes for all other listed adapters.

    -   In the **Fast Filters** pane of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, click the black arrow next to the **Filter 1** designator in **Group 1** and select the **IPv4Address** option from the drop-down menu that displays.

        > [!NOTE]
        >  With a low-level IPv4 address **Fast Filter**, the **Trace Scenario** will deliver messages to the PEF Runtime that transited to or from a specified IPv4 address only, as the **Trace Scenario** is running. This avoids the additional parsing that would normally be required if you specify a similar **Session Filter** instead, thereby improving Message Analyzer performance.

    -   Specify an IPv4 address value in the format *192.168.1.1* in the text box adjacent to the drop-down menu, to isolate traffic to the specified IPv4 address. Make sure to substitute appropriately for the IP address placeholder italics value specified in this example.

    -   Highlight the row in which the Ethernet adapter exists in the **System Network** tree grid of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, and then click the **Apply to Highlighted** button in **Group 1**.

         The name of the Ethernet adapter displays as the **Target** of the filter **Group**. Click **OK** to exit.

        > [!NOTE]
        >  Instead of configuring a **Fast Filter**, you can optionally specify a **Session Filter** such as `IPv4.Address == 192.168.1.1` in the **Session Filter** text box of the **New Session** dialog. However, you should note that a **Session Filter** requires more processing time, as indicated earlier. If you choose to use a **Session Filter**, you can remove the previously set **Fast Filter** configuration.

---

     **More Information**
     **To learn more** about the filtering configurations that you can specify for the **Microsoft-PEF-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).

---

6.  In later operating system scenarios, click the **Configure** link to the right of the **Microsoft-Windows-NDIS-PacketCapture** provider in the **ETW Providers** list to display the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog. Select the **Provider** tab in the dialog and then specify an IP Address filtering configuration.

     You can do this by first selecting the Ethernet adapter in the **Adapters** list of the dialog and then specifying an IP address  in the **IP Addresses** text box in the **Filters** pane of the dialog. Make sure that the selected Ethernet adapter is the only one with  a check mark in  the corresponding **Enabled** check box; all others should be removed. Note that you could specify a MAC address for the Ethernet adapter instead of, or in addition to, an IP address.

---

     **More Information**
     **To learn more** about special filtering configurations that you can specify for the **Microsoft-Windows-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).

---

7.  Click the **Save Scenario** button on the **ETW Providers** toolbar to display the **Edit Trace Scenario** dialog and then specify values for the **Name**, **Description**, and **Category** fields.

    > [!NOTE]
    >  When you run your customized **Trace Scenario**, the trace results will display in the default data viewer that is specified in the **Default Profile** pane on the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. If you want to change the default viewer from this location, simply click the **Default Viewer** drop-down list and choose a viewer that you want as the default.

8.  When your **Trace Scenario** configuration is complete, click the **Save** button to exit the **Edit Trace Scenario** dialog.

 **Running the Custom Trace Scenario**
When you save a customized **Trace Scenario**, it becomes a new item in the **Trace Scenario** user Library in the **Category** that you specified. This **Category** will be located under the **My Items** top-level category of the Library, from where you can select and run it at any time. It also becomes part of the Message Analyzer Sharing Infrastructure, which enables you to mutually share the scenarios in the **Trace Scenario** user Library with others.

> [!TIP]
>  After you run a custom **Trace Scenario** template from the **New Session** dialog, you have the option to reopen the session configuration by clicking the **Edit Session** button on the global Message Analyzer toolbar. Thereafter, you can reconfigure the **Trace Scenario** as required and save the new template configuration again by clicking **Save Scenario**.

---

 **More Information**
 **To learn more** about creating **Trace Scenario** templates, see [Creating and Managing Custom Trace Scenarios](creating-and-managing-custom-trace-scenarios.md).
**To learn more** about managing the **Trace Scenarios** Library as part of the Message Analyzer Sharing Infrastructure, see [Managing Trace Scenarios](managing-trace-scenarios.md).

---

## See Also

 [Capturing Message Data](capturing-message-data.md)
 [Retrieving Message Data](retrieving-message-data.md)
 [Data Viewers](data-viewers.md)