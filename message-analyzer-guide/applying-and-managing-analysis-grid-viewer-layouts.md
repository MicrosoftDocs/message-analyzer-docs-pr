---
title: "Applying and Managing Analysis Grid Viewer Layouts | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ead93f1-5189-403c-b632-31468620d396
caps.latest.revision: 47
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Applying and Managing Analysis Grid Viewer Layouts
Message Analyzer enables you to apply built-in and custom column layout configurations to the **Analysis Grid** viewer to create unique data viewing capabilities that expose other data fields of interest beyond the default **Analysis Grid** viewer column configuration. These layout configurations are included in the **Message Analyzer View Layouts** asset collection Library, which is accessible from the **Layout** drop-down list on the **Analysis Grid** viewer toolbar. By default, this Library contains a list of built-in view **Layouts** and a customizable **Example** layout, which are included in every Message Analyzer installation. The **Layout** drop-down list also has several commands that enable you to save, restore, and manage the **Layouts**. The main reason why you might change the default **Layout** is to reconfigure the **Analysis Grid** viewer data column arrangement to one that is more applicable to the type of troubleshooting or analysis tasks you are performing. When you select a built-in **Layout**, Message Analyzer adds new data columns that expose additional message field values. By doing this, you can expose hidden data that might be critically important to your data analysis perspectives.  
  
 You can change the default column arrangement by applying any built-in **Layout** or by creating, saving, and applying any custom **Layout** of your own. You can create your own custom **Layouts** by using the **Field Chooser** **Tool Window** to add new columns to the **Analysis Grid** viewer, or you can similarly customize the **Example** **Layout** however you want. Note that you can even apply the **Group** function to one or more **Analysis Grid** viewer data columns, by right-clicking chosen data columns and selecting the **Group** command from the context menu, and then save the resulting grouped configuration as a new view **Layout** asset collection Library item. You can also sort any column and the sort configuration will be persisted when you save the **Layout**.  
  
 The commands that facilitate these features, along with the built-in **Layout** functions, are described in the sections that immediately follow.  
  
## Applying Built-in View Layouts  
 Message Analyzer provides several built-in view **Layouts** that you can quickly apply to a message collection in the **Analysis Grid** viewer by simply selecting them from a drop-down list. These layouts consist of many different column configurations that expose data that can be useful for troubleshooting common problems, for example, when the TCP or HTTP protocol is the focus of analysis. In addition, the built-in **Layouts** provide various grouped message presentations that streamline analysis of data from Perfmon, WPP,  ProcMon, and other logs. The built-in **Layouts** are contained in the following subcategories of the top-level **Message Analyzer** category:  
  
-   **Azure Storage** category  
  
    -   **All .Net Client Columns** — displays all data columns from a .Net client log.  
  
    -   **Grouped by ClientRequestId and Module** — provides a grouped **Layout** of **ClientRequestId** at top-level and **Module** as a nested group, for Client, Storage, and Network logs.  
  
    -   **Storage Log** — provides a **Layout** that displays key data columns from Azure Storage logs such as **ClientRequestId**, **EndToEndLatencyMS**, **ServerLatencyMS**, **RequestStartTime**, **RequestStatus**, and **StatusCode**.  
  
-   **Cluster** category  
  
    -   **Cluster Log** — provides a **Layout** that is useful for analyzing Cluster logs with data columns such as **ProcessId**, **InfoLevel**, **Subcomponent**, and **RemainingText**. Enables you to correlate process IDs with various debug levels and Cluster Service components where errors and warnings may have occurred, respectively. This **Layout** is intended to work with the **Cluster Logs** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from a Cluster.log file and the **Cluster Logs** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **Cluster Logs** **Profile** in the table of the indicated topic for more information about  how to analyze these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which  are also described there.  
  
-   **Windows Event Tracing** category  
  
    -   **ETW** — provides a **Layout** that is useful for analyzing ETW messages that contain **ProcessId** and **ThreadId** data. The **ProcessId** is a number that is used by the operating system kernel to uniquely identify an active process for which an ETW provider or some other component is generating events. The **ThreadId** is a unique identifier of an execution thread that is running under a particular process. This **Layout** also includes a **TimeDelta** column that exposes the running time at which each message was captured, similar to the way **TimeOffset** does in the Network Monitor view.  
  
         This **Layout** is intended to work with the **ETW Guids and IDs** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this  **Analysis Grid** viewer **Layout** automatically displays if data from an event trace log (\*.etl) file is loaded into Message Analyzer while the **ETW Analysis** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **ETW Analysis** **Profile** in the table of the indicated topic for more information about  how to analyze these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is also described there.  
  
-   **Examples** category  
  
    -   **Event Log (.evtx)** — provides a **Layout** that is useful for analyzing ETW event data. This **Layout** is intended to work with the **Event Viewer** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from a \*.evtx file and the **Event Logs** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **Event Logs** **Profile** in the table of the indicated topic for more information about  how to analyze these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is also described there.  
  
-   **HTTP** category  
  
    -   **Fiddler SAZ** — provides a **Layout** that is useful for analyzing HTTP data in an environment that is similar to Fiddler, with data fields such as **StatusCode**, **Uri.Schema**, **Method**, **Uri.Host**, **Uri.AbsPath**, **PayloadLength**, **ContentType**, and **Payload**. This **Layout** is intended to work with the **Fiddler Grouping** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from a \*.saz file and the **Fiddler Traces** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **Fiddler Traces** **Profile** in the table of the indicated topic for more information about  how to analyze the data in these files, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is also described there.  
  
-   **File Sharing** category  
  
    -   **File Sharing Perf SMB2/SMB** — provides a **Layout** that enables you to analyze SMB/SMB2 performance in terms of **ResponseTime** and **TimeElapsed** values for SMB/SMB2 request and response messages. Also provides other data columns that are useful for SMB analysis such as **SessionIdName**, **TreeIdNameReference**, **FileNameReference**, and **MessageId**. This **Layout** is intended to work with the **File Sharing SMB/SMB2** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from files in any of the following formats and the **File Sharing Perf SMB2/SMB** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic:  
  
        -   *.etl  
  
        -   *.cap  
  
        -   *.pcapng  
  
        -   *.pcap  
  
         See the **File Sharing Perf SMB2/SMB** **Profile** in the table of the indicated topic for more information about  how to analyze the data in these files, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is described there.  
  
    -   **File Sharing SMB/SMB2** — provides a layout that groups by SMB **SessionId**, **TreeId**, and **FileName** to assist SMB troubleshooting.  
  
    -   **SMB Flat** — provides an SMB/SMB2 analysis environment that includes data columns such as **TimeDelta**,  **SessionIdName**, **TreeIdNameReference**, **FileNameReference**, and **Header.MessageId**. After your data displays, click the **Flat Message List** button in the Filtering toolbar to remove Operations and simulate the Network Monitor view.  
  
    -   **SysLog** — provides an environment for analyzing SambaSysLogs with data columns such as **level**, **source_file**, **file_line**, **function**, and **content**. This **Layout** is intended to work with the **SysLog** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from a SambaSysLog.log file and the **Samba Logs** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **Samba Logs** **Profile** in the table of the indicated topic for more information about  how to analyze the data in these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is described there.  
  
-   **Network** category  
  
    -   **HTTP** — provides a **Layout** that is useful for troubleshooting HTTP issues, which includes the **ResponseTime**, **ContentType**, **StatusCode**, and **Summary** information columns. **ResponseTime** data is particularly useful because it can provide an indication of server performance in terms of the time it takes for the first server response to HTTP requests. **StatusCode** can quickly expose client and server errors and **ContentType** can provide an indication of the loads that the server is handling.  
  
    -   **Network Conversation Tree with Process ID** — provides a layout that groups by **DataSource**, **ProcessId**, **Network**, and **Transport**, to enable correlation of conversations with process IDs in *.etl files.  
  
    -   **Network Monitor** — displays the default Network Monitor view, with exception of several columns being named differently in Message Analyzer, but which are functionally equivalent to the corresponding columns in the default Network Monitor layout.  
  
    -   **Process Name and Conversations** — provides a nested group configuration, where each top-level group node is identified by a **ProcessName** and nested groupings consist of **Network** and **Tranport** groups. Enables you to view the IP conversations and the TCP ports that carried those conversations for each process that is identified in the **ProcessName** group. This **Layout** also adds a **ProcessName** column to the **Analysis Grid** viewer column configuration.  
  
        > [!NOTE]
        >  Message Analyzer can identify process names from .etl files that are generated with the Netsh utility. Therefore, you might use the **Process Name and Conversations** view **Layout** when you are working with event logs (\*.etl), to expose data for the **ProcessName** group in the **Analysis Grid** viewer.  
  
    -   **TCP Deep Packet Analysis with ABSOLUTE Sequence Number Flat** — provides a **Layout** that adds several columns to the default **Analysis Grid** viewer column configuration to expose the values of fields that can help you troubleshoot TCP and network layer issues. Added columns consist of the **TimeDelta**, **Flags**, **SourcePort**, **DestinationPort**, **PayloadLength**, **SequenceNumber**, **NextSequenceNumber**, **AcknowledgementNumber**, **WindowScaled**, **TopModule**, **Options**, and so on. Absolute sequence numbers are the long version of such numbers, as in the original format that is transmitted on the wire.  
  
    -   **TCP Deep Packet Analysis with ABSOLUTE Sequence Number with Grouping** — provides a **Layout** that creates a hierarchy of **Network**, **Transport**, and **Sourceport** groups that isolate network conversations at top-level, the transport that carried them in the first nested group, and the ports over which the conversations transited in the second nested group. The **Network** and **Transport** groups provide quick access to data that can assist you in troubleshooting the network layer and related communication ports, for example IP addresses,  conversation direction, and conversation ports. The columns in this **Layout** are identical to those of the **TCP Deep Packet Analysis with ABSOLUTE Sequence Number Flat**, as is the use of absolute sequence numbers.  
  
    -   **TCP Deep Packet Analysis with RELATIVE Sequence Number Flat** — provides a **Layout** that  exposes the values of fields that can help you troubleshoot TCP and network layer issues. The columns in this **Layout** add relative sequence number and relative block (**RelBlock**) columns to the ones previously described in the **TCP Deep Packet Analysis with ABSOLUTE Sequence Number Flat** **Layout**. Relative sequence numbers are the short version of such numbers for easier reading, as modified from the original wire format.  
  
    -   **TCP Deep Packet Analysis with RELATIVE Sequence Number with Grouping** — provides a **Layout** that creates a hierarchy of **Network**, **Transport**, and **Sourceport** groups that isolate network conversations at top-level, the transport that carried them in the first nested group, and the ports over which the conversations transited in the second nested group. The **Network** and **Transport** groups provide quick access to data that can assist you in troubleshooting the network layer and related communication ports, for example IP addresses,  conversation direction, and conversation ports. The columns in this **Layout** are identical to those of the **TCP Deep Packet Analysis with RELATIVE Sequence Number Flat** **Layout**, as is the use of relative sequence numbers.  
  
        > [!NOTE]
        >  If you also specify a **TCP** **Viewpoint** with the TCP **Layouts** described here, you can isolate all TCP traffic as top-level messages for ease of analysis.  
  
-   **IIS** category  
  
    -   **IIS** — provides a **Layout** of data columns that is useful for troubleshooting Internet Information Server (IIS) logs. This **Layout** is intended to work with the **IIS** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer **Layout** displays by default if you are loading data from an IIS.log file and the **IIS Logs** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **IIS Logs** **Profile** in the table of the indicated topic for more information about  how to analyze the data in these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is described there.  
  
-   **Netlogon** category  
  
    -   **Netlogon** category — provides a **Layout** of data columns that is a basic environment for  troubleshooting Netlogon logs. This **Layout** is intended to work with the **Netlogon Group by Message Type** **Layout** of the **Grouping** viewer to create an interactive analysis environment. In addition, this **Analysis Grid** viewer  **Layout** displays by default if you are loading data from a Netlogon.log file and the **Netlogon Logs** **Profile** is enabled in the **Options** dialog, as described in the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.  
  
         See the **Netlogon Logs** **Profile** in the table of the indicated topic for more information about  how to analyze the data in these logs, where such analysis is enhanced by complementary **Layouts** for the **Grouping** and **Chart** viewers, which is described there.  
  
-   **Common** category  
  
    -   **Perfmon Log** — provides a **Layout** with grouping for Perfmon logs that are saved as comma-separated value (CSV) files.  
  
    -   **Performance Top Down** — provides a **Layout** that is useful for analyzing performance issues associated with **TimeElapsed** and **ResponseTime** field values. In this **Layout**, the **TimeElapsed** data column is sorted in descending order (top-down) to expose Operations that are taking a long time to complete, for example with protocols that use request/response messages such as  DNS, HTTP, and SMB. This may be an indication of a network issue if the corresponding server first response (**ResponseTime**) is a relatively low value. On the other hand, if the **ResponseTime** is a high value and the **TimeElapsed** is only slightly higher, this might indicate a slowly responding server rather than a network issue.  
  
    -   **Process View** — provides a **Layout** that enables top-down performance analysis, similar to the **Performance Top Down** **Layout**. However, this **Layout** also adds a **ProcessName** column for traces that contain process name information, so that you can correlate processes with **TimeElapsed** and **ResponseTime** data.  
  
    -   **ProcMon Logs** — provides a grouped **Layout** by process name and includes other data columns such as **Time Delta**, **PID**, **Operation**, and so on, for ProcMon logs.  
  
    -   **Protocol/Module Summary** — provides a grouped **Layout** by Module with nested message Types for a high-level overview of such data.  
  
    -   **WPP ETL** — provides a **Layout** with grouping and special data columns for WPP-generated events that are logged in a *.etl file.  
  
-   **My Column Layouts** category  
  
    -   **Raw Text Log** — provides a **Layout** that contains  **MessageNumber** and **Summary** columns only. You can apply this **Layout** to the data that you load into Message Analyzer from any log file to obtain a high-level view of the log data.  Note that none of the log fields that exist in the **Summary** column are provided a separate column for displaying their data in the **Analysis Grid** viewer.  
  
         However, you may be able to parse the summary data into individual fields/columns, if a configuration file exists for the log type with which you are working.  You can select different built-in configuration files from the **Text Log Configuration** drop-down list in the **New Session** dialog for a Data Retrieval Session after you add a log file to the files list. If it is a log type for which a configuration file already exists, the drop-down list is enabled for selection. For more information about working with text logs, see [Opening Text Log Files](opening-text-log-files.md).  
  
-   **My Items** category  
  
    -   **Example View Layout** — provides a sample **Layout** based on TCP fields that you can modify as you wish. You can save your changes with a new **Layout** name that is appropriate for the type of analysis it supports.  
  
## Managing View Layouts  
 The **Layout** asset collection Library drop-down list also provides a set of commands that enable you to manage your view **Layouts**. Most commands are accessible in a submenu that displays when you click the **Manage Layouts** item in the **Layouts** drop-down list, as described in the "Manage Layout Commands" section below. However, the following frequently used command is directly accessible from the **Layout** drop down list for convenience:  
  
-   **Save Current Layout As…** — enables you to save view **Layouts** that reflect unique column configurations that you create with **Field Chooser**, so that they appear as items in a specified **Category** in your local asset collection **Layout** Library. Thereafter, you can reapply them whenever you want to by selecting them from the **Layout** Library, or you can export them to a designated location for sharing with other users.  
  
     When you use this command to save the current **Layout**, the **Edit Item** dialog displays to enable you to specify a **Name**, **Description**, and **Category** in which to place the **Layout**. Note that any **Layouts** that you save from the **Edit Item** dialog will display in a subcategory under the top-level **My Items** category.  
  
 **Manage Layout Commands**   
Other commands that are available for managing view **Layouts** display in a submenu that appears when you select the **Manage Layouts** item in the **Layout** drop-down list, as follows:  
  
-   **Save Current as Default User Layout** — enables you to save the current **Analysis Grid** viewer column configuration as the default **Layout** for the **Analysis Grid**, which then displays whenever you specify the **Analysis Grid** as the viewer for session results, providing that an enabled **Profile** does not override that **Layout**.  
  
-   **Load Default User Layout** — enables you to restore the **Layout** that you saved as the default with the **Save Current as Default User Layout** command, as needed.  
  
-   **Restore Application Default Layout** — enables you to restore the default view **Layout** for the **Analysis Grid** that ships with Message Analyzer, as described in the [Analysis Grid Viewer](analysis-grid-viewer.md) topic.  
  
-   **Manage…** — displays the **Manage Column Layouts** dialog from where you can export one or more **Layouts** as shareable items so that other users can take advantage of your **Layout** configurations. You can also import one or more **Layouts** that other users have made available as shareable items, to expand your local **Layout** Library. In addition, you can edit the information for any column **Layout** in the **My Items** category of the dialog by executing the **Edit** command from the dialog's right-click context menu.  
  
## Sharing View Layout Items  
 When you save a view **Layout**, it becomes part of a local asset collection Library containing **Layout** items that you can manage and share with others. Message Analyzer provides a simple way to expose these **Layout** items to others for sharing, or to retrieve **Layouts** that others have shared. From the **Manage Column Layout** dialog, you can share **Layout** items directly with others by selecting the item/s you want to share and then clicking the **Export** button on the dialog tool bar. The **Save Library** dialog then displays so that you can enter **Title**, **Description**, and **Organization** data. Thereafter, you can specify the file share location where you want to post your items. You can also use the **Import** feature in the same dialog to access **Layout** items that have been shared by others to a designated file share. The **Manage Column Layout** dialog is accessible by selecting the **Manage…** item in the submenu that appears when you select the **Manage Layouts** item from the **Layout** asset collection Library drop-down list on the **Analysis Grid** viewer toolbar.  
  
 You can also share your **Layout** items through the Message Analyzer Sharing Infrastructure by creating a user feed from the **Settings** tab of the **Asset Manager** dialog, which is accessible from the Message Analyzer global **Tools** menu. When you create your own user feed, you will point it to a file share or other designated location where you post your **Layout** items. To post your items, click the **Export** button on the **Manage Column Layout** dialog tool bar and navigate to the designated share location. Thereafter, you can update existing items or add others and make them available to team members or other users through the configured feed, where users can view, download, and synchronize to updates to your **Layout** items. However, the synchronization feature will be available only in a future Message Analyzer release, at which time the Sharing Infrastructure publishing features will enable others to automatically synchronize to any updates that you make to your **Layout** items on a user feed. In the meantime, you can perform a manual configuration process that enables users to synchronize to your **Layout** asset collection updates, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
 Microsoft also provides a default **Message Analyzer** feed on the **Downloads** tab of the **Asset Manager** dialog that enables you to download **Message Analyzer View Layouts** or **Azure Storage View Layouts** asset collections from a Microsoft web service and to synchronize with asset collection updates that are periodically pushed out by the service.  At any time, you can perform a download of an auto-synced collection from the **Settings** tab of the **Asset Manager** dialog.  
  
> [!NOTE]
>  **Message Analyzer View Layouts** that apply to the **Analysis Grid** viewer and **Message Analyzer Grouping View Layouts** that apply to the **Grouping** viewer are separate and function independently of each other. You can view these asset collections in the **Asset Manager** dialog.  
  
---  
  
 **More Information**   
 **To learn more** about sharing asset collections in Message Analyzer, including further details about the common **Manage** ***\<AssetType>*** dialog, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.  
**To learn more** about the **Field Chooser**, see the [Field Chooser Tool Window](field-chooser-tool-window.md) topic.  
**To learn more** about the **Analysis Grid** viewer **Group** function, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).  
**To review** some simple examples of TCP troubleshooting with Message Analyzer, see [Procedures: Using the Data Filtering Features](procedures-using-the-data-filtering-features.md).  
---