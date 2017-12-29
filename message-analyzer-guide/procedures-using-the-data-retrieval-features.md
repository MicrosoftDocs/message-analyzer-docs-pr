---
title: "Procedures: Using the Data Retrieval Features | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b4ad6ef-3c14-4ee1-8df2-0656b990e065
caps.latest.revision: 76
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Using the Data Retrieval Features

The procedures in this section encapsulate some of the main functionalities described in [Retrieving Message Data](retrieving-message-data.md). They serve as simple examples that demonstrate how to use Message Analyzer features to retrieve saved logs and files in the most efficient manner. These procedures, rather than serving as troubleshooting scenarios, also demonstrate the use of some data analysis tools that manipulate loaded data.  
  
> [!NOTE]
>  Although these procedures demonstrate the use of Message Analyzer capabilities in some basic scenarios, they are only a sampling of what you can accomplish with Message Analyzer, given that you can also apply the methodologies described here to many other scenarios.  
  
---  
  
  **Procedure Overviews**   
A brief description of each procedure is included here for review, as follows.  

---  
  
 **[Load and Display Saved Data](procedures-using-the-data-retrieval-features.md#BKMK_load-displayTraceData)**  — shows how to browse for saved files that contain a message collection you want to load into Message Analyzer through a Data Retrieval Session and display it in a selected data viewer.  
  
 **[Select Specific Data from a Saved Trace File](procedures-using-the-data-retrieval-features.md#BKMK_selectTraceDataFromSource)**  — shows how to select specific data from a saved file by applying a **Session Filter** to the data loading process via a Data Retrieval Session.  
  
 **[Display Different Data Viewers for Session Results](procedures-using-the-data-retrieval-features.md#BKMK_displayDifferentViews)**  — shows how to view results in selected data viewers that provide different presentation formats to enhance your data analysis perspectives.  
  
 **[Load Saved Data with the Open Feature](procedures-using-the-data-retrieval-features.md#BKMK_loadDataQuikOpen)**  — shows how to quickly load and display data from a saved file by using the **Open** feature.  
  
 **[Load Saved Data From Recent Files or Drag-and-Drop](procedures-using-the-data-retrieval-features.md#BKMK_loadDataRecentFiles)**  — shows how to quickly load and display data from a saved file by using the **Recent Files** list. Also describes the use of drag-and-drop as an alternate method for opening files.  
  
 **[Apply a Time Filter to Data Loading and Save the Message Collection](procedures-using-the-data-retrieval-features.md#BKMK_importSaveMsgCollection)**  — shows how to load a message collection from multiple input files with a **Time Filter** applied; and how to save it to a single file in the default Message Analyzer .matp format.  
  
 **[Load Saved Data from a Text Log](procedures-using-the-data-retrieval-features.md#BKMK_LoadTextLogFileData)**  — demonstrates how to load data from a textual .log file into Message Analyzer with the use of a built-in **Text Log Configuration** file.  
  
 **[Retrieve Data from Log Files in Azure Storage BLOB Containers or from an Azure Table](procedures-using-the-data-retrieval-features.md#BKMK_RetrieveAzureData)**  — demonstrates how to access, load, and view log data that is stored in Azure Storage binary large object (BLOB) containers or data that exists in an Azure table.  
  
> [!IMPORTANT]
>  At least one procedure in this section makes use of the drag-and-drop feature. If you have not logged off Windows after the first installation of Message Analyzer, please log off and then log back on if you wish to use drag-and-drop. This action ensures that the subsequent logon that follows installation has the appropriate privileges from the Message Capture User Group, which in turn enables Message Analyzer to have the same security context as Windows Explorer; otherwise, drag-and-drop will not work.  
>   
>  Also note that if you run Message Analyzer as an Administrator, the security context between applications that is established prevents drag-and-drop from working properly.  
  
<a name="BKMK_load-displayTraceData"></a>   
## Load and Display Saved Data  
 In the following procedure, you will load saved trace data through a Data Retrieval Session and display it in the Message Analyzer default **Analysis Grid** viewer.  
  
#### To use a Data Retrieval Session to load and display saved data  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Click the global Message Analyzer **File** menu, point to **New Session**, and then click **Files** in the **New Session** submenu to display the **New Session** dialog for Data Retrieval Session configuration.  
  
3.  On the **Files** tab toolbar of the **New Session** dialog, click **Add Files** to launch the **Open** dialog and then navigate to the file/s that contain the data of interest.  
  
4.  In the **Open** dialog, select the file/s containing the data you want to load and then click **Open** to exit the dialog.  
  
    > [!TIP]
    >  Comparing data from a Live Trace Session with associated data that is loaded from a Data Retrieval Session provides a convenient method for analyzing current and historical data.  
  
5.  In the files list that displays, ensure that there is a check mark in the check box next to the file/s that contain the data you want to load, or alternatively, remove the check mark from files that contain data which, for the moment, you do not want to load.  
  
     If you have a large number of files in the list and you need to search for suitably named files that contain specific data, as described in [Naming Saved Files](naming-saved-files.md), enter the appropriate file name characters in the search box on the **Files** tab toolbar to highlight them in the list.  
  
6.  Ensure that the **Start With** drop-down list in the **New Session** dialog specifies the default **Analysis Grid** viewer, or alternatively, select a different viewer.  
  
7.  Click the **Start** button in the **New Session** dialog to begin loading data from the selected files into Message Analyzer.  
  
     The loaded data displays in the specified Message Analyzer data viewer.  
  
8.  To load data from one or more additional files, for example, files that you *unselected* in the initial data loading configuration, click the **Edit Session** icon on the global Message Analyzer toolbar to open the **Edit Session** dialog and expose the configuration of the current Data Retrieval Session, as you originally specified it.  
  
9. Select additional files in the files list or click **Add Files** to locate and add one or more files to the files list, and then place a check mark in the check box next to each file that contains the data you want to load into your existing message collection. By default, the **Restricted Edit** mode in which the **Edit Session** dialog opens only enables you to add more files to the files list, since other configuration features are disabled in this mode.  
  
    > [!TIP]
    >  If you add a check mark to the **Select Added Files** check box on the toolbar of the **Files** tab, all files that you add to the files list with the **Add Files** feature are automatically selected for inclusion in the data loading process.  
  
10. Click the **Apply** button in the **Edit Session** dialog to load the new data into the previously specified Message Analyzer data viewer.  
  
     If your data viewer is the **Analysis Grid**, note that the new data you are adding is appended to the existing set of messages in the tree grid of this viewer.  
  
> [!TIP]
>  When analyzing data that you loaded from multiple input data sources, as described in [Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md), you have the option to organize and summarize the loaded data into Groups that are labeled by data source name. To do this, locate the **DataSource** field in the **General** category of the **Field Chooser**  **Tool Window** and then execute the **Add as Grouping** command by selecting it from the context menu that displays after you right-click the **DataSource** field.  
  
<a name="BKMK_selectTraceDataFromSource"></a>   
## Select Specific Data from a Saved Trace File  
 In the following procedure, you will select specific trace data to load into Message Analyzer through a Data Retrieval Session, by applying a **Session Filter** to the data loading process.  
  
#### To select specific data in a Data Retrieval Session  
  
1.  Perform steps 1 and 2 of the procedure in [Load and Display Saved Data](procedures-using-the-data-retrieval-features.md#BKMK_load-displayTraceData).  
  
2.  On the **Files** tab toolbar, ensure that there is a check mark in the **Select Added Files** check box, so that all files that you add to the files list with the **Add Files** feature are automatically included in your data loading configuration.  
  
3.  On the **Files** tab toolbar, click **Add Files** to launch the **Open** dialog and then navigate to the file/s that contain the trace data of interest.  
  
4.  In the **Open** dialog, select the file/s containing the data you want to load into Message Analyzer and then click **Open** to exit the dialog.  
  
5.  From the **Library** drop-down list on the toolbar above the **Session Filter** text box, select a built-in Filter Expression, or alternatively, create your own custom Filter Expression to specify the filtering criteria that you want to apply to the input messages that are to be loaded into Message Analyzer.  
  
     For example, you might specify a simple expression such as `IPv4.Address==192.168.1.1`, to filter for messages that contain a specified IP address only. You can also select a recently used filter from the **History** drop-down list on the previously indicated toolbar in the **New Session** dialog. In this example, the IP address in italics is a placeholder for an actual IP address that you will include in this filter.  
  
6.  Optionally, select a data viewer from the **Start With** drop-down list of the **New Session** dialog, or simply accept the default data viewer, for example, the **Analysis Grid**.  
  
    > [!NOTE]
    >  At any time prior to loading data in the next step, you have the option to remove the check mark from any files that contain data you do not want to load at the moment.  
  
7.  Click the **Start** button in the **New Session** dialog to begin loading your selected data into Message Analyzer.  
  
8.  At your discretion, you can return to the configuration of your Data Retrieval Session to specify a different Filter Expression or message collection configuration for loading data into Message Analyzer, by clicking the **Edit Session** icon on the Message Analyzer global menu.  
  
     The **Edit Session** dialog opens in the **Restricted Edit** mode, with an information bar that specifies the following:   
    *Add new files or data sources without causing a data reload. Other configuration changes in Full Edit mode cause a reload of all data.*  
    This means that you can add new data files into the target files list and load that data without Message Analyzer having to also reload the data from the existing files. But any other configuration changes that you specify for the current Data Retrieval Session will cause Message Analyzer to reload all data, which includes messages from all files that represent the original message collection, in addition to messages from any new files you are adding. When this occurs, you might notice slower performance as Message Analyzer reloads the data.  
  
9. In the **Edit Session** dialog, click the **Full Edit** button to enable all configuration features for your Data Retrieval Session.  
  
10. In the **Edit Session** dialog, select a different **Session Filter** from the centralized Filter Expression **Library**, for example, `#DiagnosisTypes==2`. If you select this filter, you will load and view only the messages that contain validation errors, for analysis purposes. A validation error is an indication that a message does not align with its protocol definition, as described in the [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.  
  
11. After you have modified the Data Retrieval Session by selecting a different **Session Filter** from the centralized **Library**, click the **Apply** button to view the results of the new Data Retrieval Session configuration in the data viewer that you initially selected.  
  
     **Note** When modifying an existing Data Retrieval Session, you cannot change the data viewer in which to display your data, as this capability is disabled in the **Edit Session** dialog. As a result, the messages that load from your modified Data Retrieval Session after you click the **Apply** button will continue to display in the data viewer that you initially specified. If you want to see the loaded data in a different data viewer, you can select one from the **New Viewer** drop-down list on the global Message Analyzer toolbar, as described in the procedure that follows.  
  
---  
  
**More Information**   
**To learn more** about the **Edit Session** dialog, see [Editing Existing Sessions](editing-existing-sessions.md).  
---  
  
<a name="BKMK_displayDifferentViews"></a>   
## Display Different Data Viewers for Session Results  
 In the following procedure, you will display different views of a loaded message collection by launching other data viewers. Doing so can help you obtain different analytical perspectives when assessing your data.  
  
#### To display data in different viewers  
  
1.  Start a Data Retrieval Session with the default **Analysis Grid** viewer and load data into Message Analyzer by following the steps of one of the previous procedures, as appropriate.  
  
     Thereafter in this procedure, you will be selecting other viewers.  
  
2.  Observe that the loaded data displays in the Message Analyzer **Analysis Grid** viewer, or whichever viewer is set as the default.  
  
3.  Confirm that the **Session Explorer** **Tool Window** is open. If not, open it by selecting the **Session Explorer** item in the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu.  
  
4.  To create a different view of your data, right-click anywhere in the **Session Explorer** window and highlight **New Viewer** in the context menu, highlight **Charts (Deprecated)**, and then select the **Protocol Dashboard** item. Alternatively, you can select the **Protocol Dashboard** viewer from the same location in the **New Viewer** drop-down list that is accessible from the global Message Analyzer toolbar.  
  
5.  Observe that the loaded data displays in the **Protocol Dashboard** viewer as a separate viewer tab in the same session.  
  
     The **Protocol Dashboard** viewer contains several graphic data visualizers that include **Top Level Protocols Summary** components in **Table** grid, **Bar** element, and **Pie** slice formats that correlate message count versus module/protocol types, in addition to a **Top Level Protocols Over Time** chart in X-Y axis format that displays message count per module/protocol versus the trace timeline.  
  
6.  To create a another view of your data, right-click anywhere in the **Session Explorer** window and highlight **New Viewer** in the context menu, and then select the **Top Talkers Top 20** view **Layout** from the **Chart** drop-down in the **New Viewer** drop-down list,.  
  
    > [!NOTE]
    >  This **Layout** contains a **Bar** element chart that displays the distribution of traffic volume for each IPv4 or IPv6 conversation that occurred across the timeline of a set of trace results. It also provides a relative indication of the percent bandwidth consumed by each conversation with respect to the total message count in the trace.  
  
7.  Right-click again anywhere  in the **Session Explorer** window, highlight **New Viewer**, and then select the **Pattern Match** item.  
  
8.  Execute a Pattern Expression in the **AVAILABLE PATTERNS** pane, by placing a check mark in a chosen Pattern Expression check box.  
  
     For example, you could select the **TCP Three-Way Handshake** check box to view and analyze the messages — respectively sent from and received by source and destination nodes — that successfully participated in TCP connection handshake communications across the trace timeline.  
  
    > [!TIP]
    >  Because the **Pattern Match** viewer can interact with the **Analysis Grid** viewer, it may be useful to redock these viewers so that you can more effectively see the results of **Pattern Match** viewer message selection as it displays in the **Analysis Grid** viewer. See [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md) for more information.  
  
9. To create a another view of your data, right-click anywhere in the **Session Explorer** window and highlight **New Viewer** in the context menu, and then select the **Gantt** viewer.  
  
     This viewer shows the distribution of messages in each IP conversation across the timeline of a trace for each protocol that generated such messages. The protocols  are color-coded in a **LEGEND** for quick identification, where you can select the protocol messages you wish to view.  
  
10. Repeat these steps to specify different data viewers as needed. For example, you might specify one of the many other **Layouts** for the **Chart** viewer, which exist in the **Message Analyzer Chart View Layouts** asset collection. Note that this collection is accessible from the **New Viewer** drop-down list, wherever it appears, in every Message Analyzer installation.  
  
11. To enhance your analysis perspectives, poll through the various data viewers by clicking the session nodes for each viewer type in the **Session Explorer** window, for the current Data Retrieval Session. Note that you can also manually select the corresponding session tabs to look at the data format of each viewer.  
  
---  
  
 **More Information**   
 **To learn more** about the **Protocol Dashboard** viewer,  see the [Protocol Dashboard](protocol-dashboard.md) topic.    
**To learn more** about the many **Layouts** that you can display for the **Chart** viewer,  see the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.  
**To learn more** about Pattern Expressions, including the built-in Pattern Expressions, see the [Pattern Match Viewer](pattern-match-viewer.md) section.    
**To learn more** about the  **Gantt** viewer,  see the [Gantt Viewer](gantt-viewer.md) topic.  

---  
  
<a name="BKMK_loadDataQuikOpen"></a>   
## Load Saved Data with the Open Feature  
 In the procedure that follows, you will display data quickly from a saved trace or log file by using the **Open** feature.  
  
#### To quickly open a saved file and display its data  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Click the global Message Analyzer **File** menu, select **Open**, and then click the **From File Explorer** item to launch the **Open** dialog. You can also use the keyboard shortcut `Ctrl+O` to open the dialog.  
  
3.  Navigate to the saved file containing the data you want to display, select the file, and then click **Open**.  
  
     The saved data displays in the default data viewer, for example, the **Analysis Grid** viewer.  
  
> [!CAUTION]
>  If you load a custom \*.log file through the **Open** feature, Message Analyzer will open the **New Session** dialog first to display the configuration for a Data Retrieval Session. This action enables you to select a **Text Log Configuration** file that will fully parse the log data after you **Start** the session, otherwise, it is likely that Message Analyzer will be unable to  parse the data in your custom log data.  
>   
>  The exception to this is when you have a default configuration file already specified in the **Text Log Files** pane on the **General** tab of the  **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. When this is the case, Message Analyzer does not display the **New Session** dialog, but rather, automatically begins parsing and loading the data from the \*.log file into the default data viewer. Note that Message Analyzer will *fully* parse the .log file data only if the right configuration file is specified, which might be either a custom configuration file that you created, or one of the default configuration files that is provided with every Message Analyzer installation. For more information, see [Opening Text Log Files](opening-text-log-files.md).  
  
> [!NOTE]
>  If you load a trace file that was saved with one or more out-of-date parsers, Message Analyzer prompts you to reparse the trace.  
  
<a name="BKMK_loadDataRecentFiles"></a>   
## Load Saved Data From Recent Files or Drag-and-Drop  
 In the procedure that follows, you will quickly load and display trace data by using the **Recent Files** feature or the drag-and-drop feature, as alternate methods for loading data into Message Analyzer. To ensure that drag-and-drop functions properly, you will need to have logged off and back on Windows at least once since you installed Message Analyzer, as previously indicated in this section. In addition, ensure that you do not run Message Analyzer as Administrator if you want to use the drag-and-drop feature. If you do, the inconsistent  security contexts of Message Analyzer and **Windows/File Explorer** will prevent drag-and-drop from working properly.  
  
#### To quickly load and display saved data  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Click the global Message Analyzer **File** menu and then select **Recent Files** to display the list of recently accessed trace and log files.  
  
3.  In the **Recent Files** submenu, click a file that contains data that you want to quickly display in the default data viewer, providing that you have one or more files in the list.  
  
    > [!NOTE]
    >  If you load a text .log file through the **Recent Files** feature, the same behavior that is described in the previous **Caution** applies.  
  
4.  Alternatively, drag-and-drop one or more saved trace files from **Windows/File Explorer** to any location on the Message Analyzer user interface, such as the **Start Page**, global toolbar, or onto the **Session Explorer** **Tool Window**.  
  
     Message Analyzer immediately displays the trace file data in the default session viewer, providing that reparsing is not required, in which case you are advised that Message Analyzer needs to reparse the data. If you drag-and-drop more than one trace file, the data for each file is appended in a single session viewer tab.  
  
     Note that you can also drag-and-drop saved .log files onto the files list on the **Files** tab of the **New Session** dialog. This can be useful if you know in advance that you will need to specify a **Text Log Configuration** file in the dialog.  
  
<a name="BKMK_importSaveMsgCollection"></a>   
## Apply a Time Filter to Data Loading and Save the Message Collection  
 In the procedure that follows, you will load a message collection consisting of data from multiple files while applying a **Time Filter** and you will save the results to a single file in the default Message Analyzer .matp file format.  
  
#### To apply a Time Filter to the data loading process and save the message collection  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Click the global Message Analyzer **File** menu, point to **New Session**, and then select **Files** in the **New Session** submenu to display the **New Session** dialog for a Data Retrieval Session.  
  
3.  On the toolbar of the **Files** tab, click **Add Files** to launch the **Open** dialog and then navigate to the file/s that contain the data you want to load into Message Analyzer.  
  
4.  In the **Open** dialog, select the file/s containing the data you want to load and then click **Open** to exit the dialog.  
  
     This might consist of any combination of .matu, .matp, .cap, .log, .etl, or other files that contain message data that was captured or logged in a similar time frame. For example, this could be data from several large log files that you want to aggregate and load into Message Analyzer for analysis purposes.  
  
5.  In the files list that displays, ensure that you have a check mark in the check box next to the file/s that contain the data you want to load.  
  
6.  In the **Time Filter** pane on the **Files** tab of the **New Session** dialog, adjust the left and right time slider controls to define a window of time in which to view data.  
  
     For example, if you have one or more large input files with target data, you might want to focus on a particular time slot in which you suspect that a particular issue has occurred to minimize consumption of system resources, rather than load all the message data contained in the input files. You can do this with a **Time Filter**, which loads only the messages with timestamp values that fall within a specified window of time.  
  
> [!NOTE]
>  If you have a collection of target input files, the **Start Time** and **End Time** values that display in the **Time Filter** configuration are inclusive of the earliest and latest chronological time value, respectively, that is detected in any input file in the files list.  
  
7.  Optionally, select or configure a **Session Filter** for your Data Retrieval Session to isolate specific information that you want to focus on, as follows.  
  
     If you want to be even more specific about the data that you load from target input files into Message Analyzer, you can specify a Filter Expression in the **Session Filter** text box of the **New Session** dialog, either by selecting a built-in filter from the centralized Filter Expression **Library**, or by configuring one manually.  
  
     For example, for an input trace file, you might add a filter such as: `IPv4.DestinationAddress == 192.168.1.1`, to load the traffic that went to or from the specified address only; or for a log file, you might use a filter such as: `*Summary contains <“searchString”>`, to exclude all messages except those that contain a specified string in the **Summary** column of the **Analysis Grid** viewer.  
  
8.  Click the **Start** button in the **New Session** dialog when you are ready to load the data.  
  
     The data from the target files that you specified in the Data Retrieval Session configuration is filtered and loaded into Message Analyzer; it then displays in the default data viewer, for example, the **Analysis Grid**.  
  
9. Create different data analysis perspectives by applying various Message Analyzer data assessment and analysis tools, as follows.  
  
     After the data is loaded, you can optionally apply additional data manipulation techniques to further analyze or isolate specific messages of interest for enhancement of your analytical perspectives. For example, you can do this with any of the following operations.  
  
    -   Sorting columns.  
  
    -   Adding new columns with the **Field Chooser** to display other field data of a protocol or module that exists in your trace results. See [Field Chooser Tool Window](field-chooser-tool-window.md) for further details.  
  
    -   Executing a right-click **Group** command on one or more **Analysis Grid** viewer columns to group data, for example, the **DiagnosisTypes** column. See [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md) for further details.  
  
    -   Specifying **Column Filters** in the column search boxes that appear when you click the **Show Column Filter Row** icon next to the **MessageNumber** column of the **Analysis Grid** viewer. See [Filtering Column Data](filtering-column-data.md) for further details.  
  
    -   Specifying a **Viewpoint** from the Filtering toolbar above the main analysis surface where viewer data displays. See [Applying and Managing Viewpoints](applying-and-managing-viewpoints.md) for further details.  
  
    -   Specifying a  view **Filters** from the Filtering toolbar. See [Applying and Managing Filters](applying-and-managing-filters.md) for further details.  
  
    -   Choosing different viewer **Layouts** that focus on the data of different fields, which includes  **Chart** viewer **Layouts** that contain different types of visualizer components, in **Bar** element, **Pie** slice, **Timeline**, or **Table** grid formats. See [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md), [Grouping Viewer Layouts](grouping-viewer.md#BKMK_GroupViewLayouts), and  [Chart Viewer Layouts](chart-viewer-layouts.md) for further details.  
  
    -   Selecting different data viewers that enhance your analytical perspectives. See [Data Viewers](data-viewers.md) for further details.  
  
    -   Applying a removable **Time  Filter** from the Message Analyzer Filtering toolbar to further define the window of time in which to view data. See [Applying a Time Filter to Session Results](applying-a-time-filter-to-session-results.md) for further details.  
  
10. Save your data by using the **Save/Export Session** dialog, as follows.  
  
     When you have a set of messages that exposes a particular issue you are working on, such as a group of errors that might have occurred in some module at a specific source or destination address; or if you simply need to save your data to resume analysis later on, you can do so by clicking the **Save** item in the global Message Analyzer **File** menu or by clicking the **Save** icon on the global Message Analyzer toolbar to display the **Save/Export Session** dialog, and then doing one of the following:  
  
    -   Select the **All Messages** option to save all the data in a message collection.  
  
    -   Select the **Filtered Messages** option to save a message collection to which a view **Filter** was applied.  
  
    -   Choose the **Selected Messages** option after selecting/highlighting one or more messages with your mouse.  
  
     Note that you have the option to save a message collection in the Message Analyzer native .matp file format, or you can export to a .cap file for use in other applications. See [Compatibility with Exported CAP Files](compatibility-with-exported-cap-files.md) for more information about .cap file interoperability with other network troubleshooting tools.  
  
11. From the **Save As** dialog, navigate to the directory location where you want to save the selected message data.  
  
12. In the **File name** text box of the **Save As** dialog, specify a name for the message file, or use the default name if one displays.  
  
13. Click **Save** when finished.  
  
---  
  
 **More Information**   
 **To learn more** about manipulating message data for analysis purposes, see the [Analysis Grid Viewer](analysis-grid-viewer.md), [Common Data Viewer Features](common-data-viewer-features.md), and [Procedures: Using the Data Filtering Features](procedures-using-the-data-filtering-features.md) topics.  
**To learn more** about how to create an input window of time configuration in which to view retrieved data, see [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).  

---  
  
<a name="BKMK_LoadTextLogFileData"></a>   
## Load Saved Data from a Text Log  
 This procedure shows you how to load data from a text-based .log file. To successfully parse a text log, Message Analyzer requires an OPN configuration file to parse the fields of data in the log. After you load a \*.log file into the **New Session** dialog for a Data Retrieval Session, you will find a **Text Log Configuration** drop-down list that enables you to select from a collection of built-in text log parsers that have common configurations, as described in the “Built-In OPN Configuration Files” section of [Parsing Input Text Log Files](message-analyzer-tutorial.md#BKMK_ParsingLogFiles). However, if there is no configuration file in this list that can adequately parse your text log, you will need to create an OPN configuration file to extend Message Analyzer’s parsing capabilities.  
  
---  
  
 **More Information**   
 **To learn more** about OPN configuration files, see the latter sections of [Parsing Input Text Log Files](message-analyzer-tutorial.md#BKMK_ParsingLogFiles).  
**To learn more** about how to create an OPN configuration file, download the [OPN Configuration Guide for Text Log Adapter](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) and use it as a development reference to walk through the process of creating a configuration file for your log.  

---  
  
#### To load saved data from a text log  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Click the **New Session** button on the Message Analyzer **Start Page** to create a blank session that displays in the **New Session** dialog.  
  
3.  In the **New Session** dialog, click the **Files** button under **Add Data Source** to display the configuration features for a Data Retrieval Session.  
  
4.  Click the **Add Files** button on the **Files** tab toolbar to display the **Open** dialog, from where you can navigate to one or more text .log files that contain the data you want to view.  
  
5.  After you select the .log file/s for which you want to view data, click **Open** to exit the dialog and display the selected .log file/s in the files list on the **Files** tab of the Data Retrieval Session configuration.  
  
6.  For each .log file that contains target input data for Message Analyzer, click the **Text Log Configuration** drop-down list to the right of each file and select the appropriate configuration file to parse the log.  
  
    > [!NOTE]
    >  As described earlier, if there is no configuration file that can parse your log/s, you will need to create a custom OPN configuration file for each log file that has a custom format.  
  
7.  Optionally, configure a **Time Filter** if you want to narrow the focus of the data retrieval process to a specific window of time, as described in [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).  
  
8.  Optionally, select a built-in Filter Expression from the centralized **Library** or configure your own, to create a set of results that focuses on a specific type of data.  
  
9. Ensure that the **Analysis Grid** viewer is selected in the **Start With** drop-down list and click **Start** to exit the **New Session** dialog and begin the data retrieval process.  
  
10. After Message Analyzer has finished loading and parsing the data, observe that the data fields for the text log display appropriately in the **Analysis Grid** viewer.  
  
11. Optionally, add other data fields that were parsed by Message Analyzer to the **Analysis Grid** viewer by using the **Field Chooser** **Tool Window** to configure them as new columns in the **Analysis Grid**, for enhanced analysis.  
  
<a name="BKMK_RetrieveAzureData"></a>   
## Retrieve Data from Log Files in Azure Storage BLOB Containers or from an Azure Table  
 The procedures in this section show how to retrieve data from one or more logs that are saved in Azure Storage binary large object (BLOB) containers and from an Azure table. Note that when you retrieve data from an Azure log, a **Text Log Configuration** file is required for parsing the log data. However, this is not the case for Azure tables because Message Analyzer automatically parses each property in an Azure table as a field. For more background information about retrieving Azure data, see [Handling Azure Data](handling-azure-data.md).  
  
<a name="BKMK_LoadAzureLogData"></a>   
#### To access, load, and view log data from Azure storage BLOB containers  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  Ensure that you have the **AzureStorageLog** parser. You will have it if you have auto-synced the **Azure Storage Parsers Version 1.0** asset collection from the **Asset Manager** dialog and restarted Message Analyzer. If not, follow the general instructions in [Using the AzureStorageLog Parser](retrieving-azure-storage-blob-data.md#BKMK_UsingAzureStorageLogParser) to obtain the parser. The Message Analyzer restart is required after you auto-sync to download the **Azure Storage Parsers** package.  
  
3.  Click the global Message Analyzer **File** menu, highlight **Open**, and then select **From Other File Sources** to open the **File Selector** dialog.  
  
4.  In the **File Selector** dialog, click the **Add Azure Connection** button to display the **Add Azure Storage Connection** dialog and  then specify an **Account name** and **Account key** in the appropriate text boxes — see [Accessing Log Data in Azure Storage BLOB Containers](retrieving-azure-storage-blob-data.md#BKMK_AccessingAzureLogs).  
  
5.  In the Add Azure Storage Connection dialog, ensure that the **Use HTTPS (Recommended)** option is selected as the **Connection** protocol, then click **OK** to exit the dialog.  
  
     A top-level **Azure Storage** node should appear in the left pane of the **File Selector** dialog, along with a data feed subnode beneath it.  
  
6.  Expand the feed subnode to expose the **Blobs** container and then navigate to the log/s that contain the data you want to load into Message Analyzer.  
  
7.  Select one or more .log files that contain the data of interest and then click **OK** to exit the **File Selector** dialog.  
  
     The **New Session** dialog opens in configuration mode for a Data Retrieval Session, with the Azure .log files that you specified appearing in the files list.  
  
8.  In the **Text Log Configuration** drop-down list that displays to the right of each file name, select the **AzureStorageLog** configuration file.  
  
9. Optionally, configure an input **Time Filter** in the **New Session** dialog to narrow the scope of retrieved data to a specified window of time, in order to create a focused data set and accelerate Message Analyzer parsing and loading time.  
  
10. Optionally, if you have downloaded the **Azure Storage Filters** asset collection through the **Asset Manager** dialog, select a built-in Azure Filter Expression from the **Azure Storage** category in the drop-down list of the centralized filter **Library** that appears in the **New Session** dialog, to further focus your retrieval results to a specific type of data.  
  
11. Ensure that the **Analysis Grid** viewer is selected in the **Start With** drop-down list and then click **Start** to exit the **New Session** dialog.  
  
     Message Analyzer begins to parse and load the Azure .log data into the **Analysis Grid** viewer.  
  
12. When data retrieval is complete, observe that the .log data displays in the **Analysis Grid** viewer with data populating the **MessageNumber**, **Timestamp**, **Module**, and **Summary** columns for each message by default.  
  
     Given that the default view **Layout** for Azure .log data is minimalistic, you might want to specify one of several other Azure **Layouts** for the **Analysis Grid** viewer by selecting it from the **Layouts** drop-down list on the **Analysis Grid** viewer toolbar. You can also populate any existing **Layout** with additional columns of data, based on Azure .log field names, as described in the next few steps.  
  
13. Open the **Field Chooser** **Tool Window**, if it is not already open, by selecting **Field Chooser** from the **Windows** submenu of the Message Analyzer **Tools** menu.  
  
14. In **Field Chooser**, navigate to the **AzureStorageLog** node and then expand it to display the **AzureStorageLogEntry** node. In turn, when you expand this node, **Field Chooser** will display all the fields that Message Analyzer parsed with the use of the **AzureStorageLog** configuration file.  
  
15. Add a new data column to the **Analysis Grid** viewer for a field of interest by selecting a particular field name and clicking the **Add** button in the **Field Chooser** window. You can also add a new column by right-clicking the field and then selecting the **Add As Column** command in the context menu that displays.  
  
     Perform this step for as many field-columns that you want to add for analysis purposes.  
  
    > [!TIP]
    >  You also have the option to add columns to the **Analysis Grid** by right-clicking a field in the **Details** **Tool Window** and selecting the **Add Column for \<** ***fieldname*** **>** command, where *fieldname* is a placeholder for an actual field name in **Details**. Note that you can also use the right-click method for fields in **Details** to add a view **Filter** or to apply grouping to isolate different field values into Groups for enhanced analysis.  
  
16. Alternatively, if you have downloaded the **Azure Storage View Layouts** asset collection through use of the **Asset Manager** dialog, change the **Analysis Grid** viewer column **Layout** by selecting the **Storage Log** item in the **Layout** drop-down list on the **Analysis Grid** toolbar. This **Layout** is specifically designed to include key data fields for analysis of Azure storage logs, such as **ClientRequestId**, **EndToEndLatency**, **ServerLatency**, **RequestStatus**, **StatusCode**, and so on.  
  
     In addition, if you have downloaded the **Azure Storage Charts** asset collection through use of the **Asset Manager** dialog, you can view latency statistics for your Azure storage log data by displaying the **Azure Storage End2End Latency** and **Azure Storage Server Latency** **Layouts** for the **Chart** viewer, which are accessible from the **Charts** drop-down of the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
---  
  
 **More Information**   
 **To learn more** about working with Azure logs, see [Retrieving Azure Storage Blob Data](retrieving-azure-storage-blob-data.md).  
**To learn more** about the **Asset Manager**, see [Managing Message Analyzer Assets](managing-message-analyzer-assets.md).   
**To learn more** about using the **Field Chooser**, see the [Field Chooser Tool Window](field-chooser-tool-window.md) topic.   
**To learn more** about view **Filters**, see [Applying and Managing Filters](applying-and-managing-filters.md).   
**To learn more** about the **Analysis Grid** grouping feature, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).  
**To learn more** about creating grouped data views, see the [Grouping Viewer](grouping-viewer.md) topic.   

---  
  
<a name="BKMK_LoadAzureTableData"></a>   
#### To access, load, and view data stored in an Azure table  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to create a blank session that displays in the **New Session** dialog.  
  
3.  In the **New Session** dialog, click **Azure** under **Add Data Source** to open a Data Retrieval Session from where you can target Azure Storage table data.  
  
4.  On the **Azure** tab of the **New Session** dialog, enter the **Account Name**, **Account Key**, and **Table Name** connection information in the appropriate text boxes. See [Retrieving Azure Storage Table Data](retrieving-azure-storage-table-data.md) to locate this information.  
  
5.  Under the text boxes, select the appropriate connection **Protocol** option to use, which will be either **HTTP** or **HTTPS**.  
  
6.  In the **Start With** drop-down list, ensure that the **Analysis Grid** viewer is selected.  
  
7.  Begin the data retrieval process by clicking the **Start** button in the **New Session** dialog.  
  
8.  When data loading completes, observe that the Azure table data displays in the **Analysis Grid** viewer, with the field data displaying in the **Summary** column.  
  
9. Optionally, display selected Azure table fields in separate columns in the **Analysis Grid** viewer, by utilizing the **Field Chooser** **Tool Window** to expose other data fields of interest. You will need to look for a module in **Field Chooser** that is associated with the Azure table you specified to find the fields you can add for enhanced data analysis.  
  
## See Also  

- [Retrieving Azure Storage Blob Data](retrieving-azure-storage-blob-data.md)   
- [Retrieving Azure Storage Table Data](retrieving-azure-storage-table-data.md)