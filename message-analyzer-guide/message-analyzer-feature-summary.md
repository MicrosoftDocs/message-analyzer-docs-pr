---
title: "Message Analyzer Feature Summary | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: be4102f8-9b89-4396-b053-219223893972
caps.latest.revision: 118
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Message Analyzer Feature Summary

Microsoft Message Analyzer contains a broad and versatile range of features that build upon and exceed many of those of its predecessor, Microsoft Network Monitor. These features are designed to improve your usability experiences and to expand your capabilities set when loading, capturing, analyzing, and troubleshooting message traffic with Message Analyzer. The following provides a summary of these features that is broken down according to the means by which you can access them.

<a name="BKMK_GlobalMenus"></a>
## Global Menus

 Message Analyzer provides  global menus for quick access to various features that you will regularly use. The global menu names are located in the upper-left section of the Message Analyzer user interface and are described in the following sections:

 **File Menu**
The global Message Analyzer **File** menu provides access to the features described in the list that follows.

-   **[New Session](starting-a-message-analyzer-session.md)**  — click this item to open the **New Session** dialog, from where you can choose a source from which to acquire data; for example a **Live Trace** or saved **Files**. Clicking the **New Session** item also displays a submenu that contains various items that determine what type of session you will start. With the exception of the first two bullet items immediately below, the remaining submenu items also appear in the **New Session** dialog as **Data Source** buttons that you can click to begin the configuration of a new session, based on the type of input message data you want to acquire:

    -   **Blank Session** — opens the **New Session** dialog from where you can select a data source under **Add Data Source** to use as input to Message Analyzer.

    -   **From Current Session** — opens the **New Session** dialog to a new session configuration that derives configuration settings from the current in-focus session.

    -   **[Live Trace](configuring-a-live-trace-session.md)**  — opens the **New Session** dialog with the **Live Trace** tab selected, from where you can specify one or more target computers on which to capture data; select a built-in **Trace Scenario** from the scenario Library; and configure various provider settings and filters to customize your trace configuration before starting a live trace. The **New Session** dialog also enables you to specify global session settings such as a **Session Filter**, **Start With** data viewer selection, and **Parsing Level**.<br />You also have the capability to run multiple concurrent Live Trace Sessions with different message providers on different target computers by adding one or more **Live Trace** input sources by clicking the **New Data Source** tab and specifying the hosts from which to capture the data. You can also use a single session with a specified message provider to collect data from multiple specified host machines.

---

**More Information**  
**To learn more** about starting a new Live Trace Session, see [Starting a Message Analyzer Session](starting-a-message-analyzer-session.md).

---

> [!NOTE]
>  If you intend to *capture* messages that are encrypted with the Transport Layer Security (TLS) or Secure Sockets Layer (SSL) security rotocols, for example, HTTPS and Remote Desktop Protocol (RDP) messages, you have the option to enable any Live Trace Session for *Decryption** so that you can view the decrypted data along with decryption session statistics. For more information, see [Decrypting TLS and SL Encrypted Data](decrypting-tls-and-ssl-encrypted-data.md).

    - **[Files](configuring-a-data-retrieval-session.md)**  — opens the **New Session** dialog with the **Files** tab selected, from where you can configure a Data Retrieval Session to acquire data that exists in one or more saved files. You can also select specific data to retrieve from such sources by using filters, for example a **Time Filter** and/or **Session Filter**.

    A **Truncated Parsing** check box is also included in the **Files** tab configuration to indicate when truncated messages exist in files from which you are retrieving data, at which time Message Analyzer switches to a pared-down truncation parser set. You have the option to unselect this check box or to select it manually if Message Analyzer did not automatically detect truncated messages.

---

**More Information**  
**To learn more** about starting a new Data Retrieval Session, see [Starting a Message Analyzer Session]starting-a-message-analyzer-session.md).

---

> [!NOTE]
>  If you intend to *retrieve* messages that are encrypted with the Transport Layer Security (TLS) or Secure Sockets Layer (SSL) security protocols, for example, HTTPS and Remote Desktop Protocol (RDP) messages, you have the option to enable the Data Retrieval Session for **Decryption** so that you can view the decrypted data along with decryption session statistics. For more information, see [Decrypting TLS and SSL Encrypted Data](decrypting-tls-and-ssl-encrypted-data.md).

    In addition, the **Files** tab configuration provides you with the capability to retrieve data from textual log files and to select from a list of configuration files that support log file parsing. The **Truncated Parsing**, **Decryption**, and text log parsing features are described in [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md).

    - **[Azure Table](retrieving-azure-storage-table-data.md)**  — opens the **New Session** dialog to a configuration interface that enables you to specify an **Account Name**, **Account Key**, and **Table Name**, from which you can load Azure event log data into Message Analyzer.
    - **[Event Logs](loading-system-event-log-data.md)**  — opens the **New Session** dialog to the **Event Logs** tab, which contains a large list of event logs that were generated on your computer. You can select one or more of the event log check boxes and click **Start** to retrieve the data from the selected logs.
    - **[PowerShell](deriving-input-data-with-powershell-scripts.md)**  — opens the **New Session** dialog to the **PowerShell** tab, from where you can write a PowerShell query. If your PowerShell script obtains data from a remote source, you can specify a **Host** name and connection credentials in the **New Session** dialog. Note that if your PowerShell script captures event or network traffic and logs to an event log (*.etl) or Message Analyzer \*.matp file, respectively, you can import the data from such files through a subsequent Data Retrieval Session.
    - **[Sql](loading-sql-data.md)**  — opens the **New Session** dialog to the **Sql** tab, from where you can load data into Message Analyzer from any SQL database table. Provides facilities to specify a **Connection** string, user credentials, **Table** name, **Timestamp**, and a **WHERE** clause.
    - **[Oms](loading-oms-log-data.md)**  — opens the **New Session** dialog to the configuration interface for access to Operations Management Suite (OMS) logs. Specify user credentials to log on to Azure, select a **Subscription**, select a **Workspace** that you have configured, and then specify an Azure Resource Manager (ARM) query to extract OMS data from logs that are written by solutions that are enabled in a Workspace you created.

-   **[Open](performing-data-retrieval.md)**  — provides a submenu with the following two items:

    -   **From File Explorer** — click this item to launch Windows Explorer and locate data from a saved file, such as a trace or log, and immediately load it into the Message Analyzer default **Analysis Grid** viewer.

    -   **From Other File Sources** — click this item to display the **File Selector** dialog, from where you can specify input file sources that have a unique format. Currently, the **File Selector** is limited to working with Azure storage binary large objects (BLOBs) only. For more information, see [Handling Azure Data](handling-azure-data.md).

-   **Recent Files** — click this item to see a list of up to 10 recent files from which you loaded data into Message Analyzer. Data from a file in the **Recent Files** list is immediately loaded into Message Analyzer, as no further configuration is required.

-   **[Favorite Scenarios](performing-a-live-capture.md)**  — click this item to quickly start a Live Trace session with a single click on a **Trace Scenario** item in the list, for example, the **Local Network Interfaces**, **Loopback and Unencrypted IPSEC**, or **Pre-Encryption for HTTPS** scenario.

-   **Save** — saves changes to a Data Retrieval Session such as bookmarks, comments, and time shifts. If you click this item after capturing data from a Live Trace Session that is not yet saved, the **Save/Export Session** dialog displays with several options for saving data.

-   **[Save As](saving-session-data.md)**  — opens the **Save/Export Session** dialog that provides several save configuration options for the current set of trace results, which includes saving filtered, selected, or all messages in the data set.

-   **[Start Page](quick-session-startup.md)**  — click this item in the **File** menu to display the Message Analyzer **Start Page**.

-   **Exit** — click this item to close Message Analyzer. If you have any unsaved changes, you will be prompted with the option to save them.

**Session Menu**  
The global Message Analyzer **Session** menu provides access to the features described in the list that follows.

-   **[New Viewer](selecting-a-session-data-viewer.md)**  — click this item to open the **New Viewer** drop-down list, from where you can choose one of the built-in data viewers. You can also select a built-in **Layout** or a custom **Layout** that you created for the **Chart**, **Analysis Grid**, or **Grouping** viewers, for the current in-focus session. Data viewers that you can select from  the list consist of the following:

    -   **Analysis Grid**

    -   **Grouping**

    -   **Pattern Match**

    -   **Gantt**

    -   **Chart**

    -   **Interaction**

    -   **Message Summary Tiles**

    -   **Message Summary Lists**

    -   **PerfMon**

    -   **Charts (Deprecated)**

-   **[Edit Session](editing-existing-sessions.md)**  — click this item to launch the **Edit Session** dialog, which displays the initial configuration of either a Data Retrieval Session or Live Trace Session, depending on the type of existing session that is currently in focus. Enables you to edit the session configuration and then re-run it with your applied changes.

-   **Reparse** — click this command to reparse the messages in the current set of trace results. For example, you could reparse a displayed set of trace results after adding an SSL certificate for decryption in the **Options** dialog, so that you can display the decrypted data.

-   **[Shift Time](setting-time-shifts.md)**  — click this item to display a submenu with the following items:

    -   **Shift Time** — click this item to display the **Shift Time** dialog, from where you can specify a time shift for message **Timestamps** in a set of session results, to accommodate for time zone changes or skewed clock values in a message collection that is comprised of multiple disparate sources.

    -   **Remove All Time Shifts** — click this command to remove any previously specified time shifts from the current in-focus session.

-   **[Data Source Filter](filtering-data-sources.md)**  — click this item to display a submenu with the following items for manipulating the display of data sources:

    -   **Edit** — click this item to display the **Data Source Filter** dialog, from where you can select one or more data sources that exist in a set of trace results for which you want to view data. Data for any unselected data source will not display after you click **Apply** to exit the dialog.

    -   **Apply** — this command is enabled only after you have created a  data source configuration, applied it, and then removed it with the **Remove** command. Enables the **Remove** command to toggle into the enabled state. Working together with the **Remove** command, it enables you to alternately **Apply** and **Remove** the current   data source configuration.

    -   **Remove** — click this command to remove the current  data source configuration that you specified in the **Data Source Filter** dialog. Enables the **Apply** command to toggle into the enabled state. Working together with the **Apply** command, it enables you to alternately **Remove** and **Apply** the current  data source configuration.

-   ***ViewerName***  — a placeholder for which the name changes depending on the type of session viewer that is currently in focus. For example, if the **Grouping** viewer is in focus, then the name of this **Session** menu item changes to **Grouping**. If an **Analysis Grid** session tab is currently in focus, the item name changes to **Analysis Grid**, and so on. Click the viewer name item in the **Session** menu to display a submenu with a set of commands that apply to the indicated data viewer only. Typically reproduces the commands that exist on the respective data viewer toolbar.

**Tools Menu**  
The global Message Analyzer **Tools** menu provides access to the features described in the list that follows.

-   **[Windows](tool-windows.md)**  — utilize interactive **Tool Windows** that respond to message selection or session selection to provide additional message details. The **Tool Windows** that are available consist of the following:

    -   [Session Explorer Tool Window](session-explorer-tool-window.md) — monitor operational status and session statistics, and observe real-time progress indicators when loading, capturing, filtering, sorting, finding, grouping data, and applying sequence matching; navigate among different data viewers in various sessions; and select new data viewers from a context menu.

    -   [Message Details Tool Window](message-details-tool-window.md) — view field names and values for any message that you select in the **Analysis Grid**.

    -   [Message Data Tool Window](message-data-tool-window.md) — highlight hexadecimal values for any field that you select in the **Details** window or **Analysis Grid**, including payloads.

    -   [Field Data Tool Window](field-data-tool-window.md) — display the value of any field that you select in the **Details** window.

    -   [Bookmarks Tool Window](bookmarks-tool-window.md) — mark one or more messages of interest, which includes adding links, attachments, and different colored flags.

    -   [Comments Tool Window](comments-tool-window.md) — quickly add basic comments to one or more messages.

    -   [Diagnostics Tool Window](diagnostics-tool-window.md) — currently a preview feature that summarizes diagnosis errors and through selection, enables you to easily jump to a corresponding diagnosis message in the **Analysis Grid** viewer. You can also filter **Diagnostics** **Tool Window** columns to isolate specific column data.

    -   [Message Stack Tool Window](message-stack-tool-window.md) — display the message stack for any selected message row in the **Analysis Grid** viewer.

    -   [Decryption Tool Window](decryption-tool-window.md) — display statistics, summary, and analysis information for a decryption session.

    -   [Selection Tool Window](selection-tool-window.md) — undo erroneous message selections or maintain the context of multiple message selection in the **Analysis Grid** viewer in a separate space that is independent of the grid selection, to facilitate ease of analysis.

    -   [Compare Fields Tool Window](compare-fields-tool-window.md) — enables you to display the values of an identical selected field in two separate messages for comparison and analysis.

    -   [Field Chooser Tool Window](field-chooser-tool-window.md) — specify additional message fields in the [Analysis Grid Viewer](analysis-grid-viewer.md) when it is in focus, for deeper analysis of message data. Specify additional message field Groups in the [Grouping Viewer](grouping-viewer.md), when it is in focus. Expands the scope of data presentation and further enhances data examination and troubleshooting. Also use **Field Chooser** for configuration tasks when creating **Pattern Expressions**, **Chart** formulas, **Unions**, and so on.

    -   [Output Tool Window](output-tool-window.md) — display this tool window to monitor the Message Analyzer log file output for errors when loading modules.

    -   [Window Layout](working-with-message-analyzer-window-layouts.md) — this list item provides access to built-in **Window Layouts** that organize the **Analysis Grid** viewer with different **Tool Windows** as preset configurations that enable you to customize your working analysis environment. The presets consist of the following:

        -   **Simple**

        -   **Simple with Field Data**

        -   **Network**

        -   **Multiple Sessions**

        -   **Protocol Development**

        -   **Advanced**

-   **Add-Ins** — click this item to display a submenu with the **Compare (Preview)** tool. A preview feature that displays the **Session Comparison Utility**, which performs type and field check differences between two specified sessions.

-   **[Aliases](using-and-managing-message-analyzer-aliases.md)**  — click this item to display the **Aliases** drop-down list, from where you can select an **Alias** to apply to the currently in-focus session viewer tab. An **Alias** substitutes for cryptic or otherwise unfriendly field values that display in the Message Analyzer **Analysis Grid** viewer, for example an IPv6 address or a TCP port, for ease of analysis. Also edit and manage **Aliases** from this drop-down list.

-   **[Unions](configuring-and-managing-message-analyzer-unions.md)**  — configure and manage **Unions** of two or more fields that have identical values but different names in different data sources. Enables the correlation of field values from such sources with a single field name in Message Analyzer, for ease of analysis.

-   **[Asset Manager](asset-manager.md)**  — click this item to display the **Asset Manager** dialog, from where you can manage Message Analyzer asset collections such as **Message Analyzer Chart View Layouts**, **Message Analyzer Color Rules**, **Message Analyzer Correlations**, **Message Analyzer Filters**, **Message Analyzer Profiles**, **OPN Parsers**, and so on. Enables you to download asset collections and auto-sync them for automatic updates provided by a Microsoft web service. Also enables you to create custom feeds where you can share Message Analyzer assets that you developed on your own.

-   **[Options](setting-message-analyzer-global-options.md)**  — click this item to open the **Options** dialog, which displays the following configuration tabs:

    -   **General** tab — enables you to specify various default global settings for Message Analyzer, as follows:

        -   **Live Trace Message Buffer** — provides settings that determine the rate at which packets are dropped when exceeding the ETW buffer limit.

        -   **Text Log Files** — provides a drop-down menu that enables you to select a predefined default or custom configuration file for parsing text logs.

        -   **Updates** — enables you to check for updates to your Message Analyzer installation, either manually or automatically.

    -   **Display** tab — provides the controls for setting the format for date-time and Binary Values:

        -   **Time Display** — enables you to specify the date-time format that Message Analyzer will use across all features that display time data.

        -   **Binary Values** — enables you to specify different formats for the display of numeric data, which includes **ASCII**, **Hex**, and **Decimal** options.

    -   **[Decryption](decrypting-tls-and-ssl-encrypted-data.md)**  tab — provides the controls that allow you to import and select server certificates and to specify passwords that are required to enable Message Analyzer to decrypt traffic that is encrypted with the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) security protocols.

    -   **Features** tab — provides for selection of preview features such as viewers and **Tool Windows** that you want to enable in Message Analyzer.

    -   **Memory** tab — specifies the current memory statistics for Message Analyzer, the current state of **Server Garbage Collection**, and instructions for how to disable **Server Garbage Collection** to reduce memory consumption.

    -   **Parsing** tab — enables you to reparse a set of trace results based on alternate ports that you specify for specific protocols, to accommodate for network traffic that used alternate ports for security purposes.

    -   **Privacy** tab — enable Microsoft to collect information about stability issues, system configuration, and your frequently used features to help improve your Message Analyzer experience. Also enables you to opt-in to provide feedback on features, if you opted-out at the first Message Analyzer start up.

    -   **[Profiles](working-with-message-analyzer-profiles.md)**  tab — enables you to select built-in **Profiles** that provide preset **Analysis Grid**, **Grouping**, and **Chart** viewer **Layouts** that create an interactive and integrated analysis environment for specific types of data associated with different file types. A selected **Profile** triggers when you load data from a specific file type, such as a .cap, .pcap, .etl, or .log file, with which the selected **Profile** is functionally associated. You can also create and edit your own custom **Profiles**.

    -   **[WPP](loading-wpp-generated-events.md)**  tab — provides a convenient interface that simplifies the input configuration for specifying symbol files that are required to parse WPP-generated events.

**Help Menu**  
The global Message Analyzer **Help** menu provides access to the features described in the list that follows.

-   **[Feedback Center](message-analyzer-feedback.md)**  — click this item to open the **Feedback Center** dialog, from where you can provide feedback for predefined questions about various Message Analyzer features. Note that the feedback features are reproduced by the **Feedback Center** and **Feedback** controls in the upper-right section of the Message Analyzer user interface.

-   **[Message Analyzer Feedback](message-analyzer-feedback.md)**  — click this item to display a submenu that offers the following options for providing feedback:

    -   **Send a Smile** — tell us what you liked.

    -   **Send a Frown** — tell us what we can do better.

    -   **Report a Bug** — provide us with details about problems that you encountered.

    -   **Request a Feature**— request a feature that you think would improve your experiences with Message Analyzer.

-   **View Help** — click this item to access the  [Message Analyzer Operating Guide](https://technet.microsoft.com/en-us/library/jj649776.aspx) on TechNet.

-   **Message Analyzer Team Blog** — click this item to open the [Message Analyzer Team Blog](https://technet.microsoft.com/en-us/library/dn281804.aspx) site to review regularly posted blog articles on various Message Analyzer subjects. Also enables you to provide comments, ask questions, and receive feedback directly from Microsoft.

-   **Discussion Forum** — click this item to open the [Message Analyzer Forum](https://technet.microsoft.com/en-us/library/dn386831.aspx) site, where you can start a discussion thread and view responses from the Message Analyzer community of users and Microsoft.

-   **Check for Updates** — enables you to manually initiate a check for updates to your Message Analyzer installation.

-   **About** — displays release information such as the current Message Analyzer version and build number, along with a Privacy Alert.

## Global Toolbar
 Message Analyzer also provides a global toolbar, from which you can access most of the same features that are provided in the global menus, but with fewer clicks and submenu selections. Fuller descriptions for many of these features are provided in the [Global Menus](message-analyzer-feature-summary.md#BKMK_GlobalMenus) section. The global Message Analyzer toolbar contains the following items:

-   **[New Session](starting-a-message-analyzer-session.md)**  — click this toolbar item to open the **New Session** dialog, where you can choose a source from which to acquire data, as described earlier.

-   **[Favorite Scenarios](performing-a-live-capture.md)**  — click this toolbar item to quickly start a Live Trace session with a single click on a **Trace Scenario** item in the list.

-   **[Open](performing-data-retrieval.md)**  — provides a submenu that enables you to display either the **Open** dialog for Windows Explorer, or the **File Selector**, which is currently configured to open Azure storage BLOBs only.

-   **[Save](saving-session-data.md)**  — click this toolbar button to save bookmarks, comments, and time shifts, as described earlier.

-   **[New Viewer](selecting-a-session-data-viewer.md)**  — click this toolbar drop-down list to open additional data viewers against a set of live trace results or loaded data, for diagnostic and analysis purposes. For example, you might select the **Grouping** viewer or **Chart** viewer with a chosen **Layout** for your selection.

-   **[Edit Session](editing-existing-sessions.md)**  — click this toolbar button to open the **Edit Session** dialog to reconfigure an existing Data Retrieval Session or Live Trace Session, and then apply your changes by clicking the **Apply** button in the dialog. Note that the session will reload all data  if the changes you make are in **Full Edit** mode, otherwise, you can add  data from more files without incurring a reload of existing data.

-   **Restart** — this toolbar button enables you to restart a stopped Live Trace Session, which starts a new Live Trace Session and causes you to lose any previous data that you collected. You can also restart a stopped Live Trace Session that you edited. For example, after you edit an existing Live Trace Session through the **Edit Session** dialog, click the **Restart** button to apply the configuration changes that you specified. Note that this action also starts a new Live Trace Session and abandons any previous data you collected. Also note that the **Restart** control is included on the global toolbar only if you are displaying a set of trace results from a Live Trace Session.

-   **Pause/Resume** — click this toolbar button to pause a Live Trace Session in progress and then click it again to resume capturing data again. Toggles back and forth between the paused state and the capture resumed state as you click this button successively. Note that this control is included on the global toolbar only if you are displaying a set of trace results from a Live Trace Session.

-   **Stop** — click this toolbar button to stop the capture of messages in a Live Trace Session. Note that this control is included on the global toolbar only if you are displaying a set of trace results from a Live Trace Session.

-   **[Shift Time](setting-time-shifts.md)**  — specify time shifts that enable you to adjust the time stamps in a message set, for example to compensate for machine skew or time-zone changes across multiple data sources.

-   **[Aliases](using-and-managing-message-analyzer-aliases.md)**  — click this toolbar item to display the **Aliases** drop-down list, from where you can select a one of the default **Aliases** or a custom **Alias** that you created, and apply it to data in the currently in-focus session viewer.

-   **[New Union](configuring-and-managing-message-analyzer-unions.md)**  — click this toolbar item to display the **Edit Union** dialog, from where you can create a **Union** of two or more fields that have identical values but different names in different data sources.

-   **[Window Layout](working-with-message-analyzer-window-layouts.md)**  — click this toolbar item to display a list of **Window Layouts** from which you can select a preset **Tool Window** layout to accompany the **Analysis Grid** viewer. Enables you to create a custom working environment that accommodates the type of analysis that you typically perform.

## Start Page
 The Message Analyzer **Start Page** contains a top row of button commands for quick access to the following features or functions:

-   **[New Session](starting-a-message-analyzer-session.md)**  — to start  a new Data Retrieval Session or a Live Trace Session, open the **New Session** dialog with a single click on the **New Session** button.

-   **[Start Local Trace](performing-a-live-capture.md)**  — start a local Link Layer trace in a basic configuration with a single click, with no additional configuration required.

-   **[Open](performing-data-retrieval.md)**  — launch the Windows Explorer **Open** dialog with a single click, to locate a saved file containing message data and quickly load it into Message Analyzer.

-   **[Discussion/Voting Forum](message-analyzer-online-forum.md)**  — go to the Message Analyzer Forum to start a discussion thread, where you can get feedback from Microsoft. Also vote on discussions that you find helpful.

-   **[Message Analyzer Team Blog](message-analyzer-team-blog.md)**  — go to the Message Analyzer Blog to review numerous Blog postings about Message Analyzer features and use. Also, leave comments, rate articles, and get feedback from Microsoft. In addition, you will find a link to Message Analyzer training Videos on this site under **Important Links**.

From the **Start Page**, you can also view **Recent Files**, **Favorite Scenarios**, edit **Favorite  Scenarios**, and review **News** items.

## Layouts for the Chart Viewer
 Message Analyzer enables you to select various built-in **[Chart Viewer Layouts](chart-viewer-layouts.md)** against a set of trace results to enhance your data analysis perspectives. Message Analyzer also provides the configuration tools and other features needed to create, edit, save, and share **Layouts** for the **Chart** viewer that you can configure with custom **Bar** element, **Pie** slice, **Timeline** graphic, and **Table** grid visualizer components. Note that each of these components are used in the built-in **Protocol Dashboard** viewer, which is accessible from the **Charts (Deprecated)** drop-down list in the **New Viewer** drop-down on the global Message Analyzer toolbar.

 When creating new **Layouts** for the **Chart** viewer, you can use the  **Field Chooser** **Tool Window** to specify message fields for your **Layout** so that you can monitor  values and you can also configure  data manipulation formulas to create diverse top-level data summary configurations and statistical displays that empower visual analysis capabilities. Note that Message Analyzer **Chart** viewer **Layout** configurations also support **Unions** and **Union** sets. You can access the configuration controls for creating new **Layouts** by clicking the **Edit** item in the **Chart** drop-down list that appears on the global Message Analyzer **Session** menu whenever a **Chart** is displayed and currently in focus.

## Sharing Infrastructure
 Message Analyzer provides a **[Sharing Infrastructure](sharing-infrastructure.md)** that enables you to download default user asset collections to your local Libraries for manipulating and viewing data; this also includes downloading OPN packages for parsing messages that you capture with Message Analyzer. You can synchronize these collections and packages for automatic updates that are periodically pushed out by a Microsoft web service to the default **Message Analyzer** subscriber feed. You can view this feed from the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu. Because the user **Libraries** are integrated with the Sharing Infrastructure, you can import, export, and share these items with others, including any that you create or modify. Library item types include **Message Analyzer Trace Scenarios**, **Message Analyzer Filters**, **Message Analyzer Chart View Layouts**, **Message Analyzer Color Rules**, **Message Analyzer Profiles**, **Message Analyzer Viewpoints**, and so on. To enable sharing these Library items, you can configure your own user feeds or post items to a user file share. You can also manage all user Library types with the common and centralized management dialog.

## Other Capabilities
 Other prominent Message Analyzer capabilities include the following:

-   **[Configuring a Remote Capture](configuring-a-remote-capture.md)**  — capture remote traffic on Windows 8.1, Windows Server 2012 R2, and Windows 10 hosts.   Use the **Remote Network Interfaces** **Trace Scenario** with the **Microsoft-Windows-NDIS-PacketCapture** provider to target one or more computers with supported operating systems for remote capture in a Live Trace Session.

-   **[Configuring Host Adapter and Hyper-V-Switch Filters](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md#BKMK_HostSwitchFilterConfig)**  — capture traffic from one or more host adapters and/or virtual machines (VMs) that are serviced by a Hyper-V Switch on remote Windows 8.1, Windows Server 2012 R2, or Windows 10 hosts, or on the local computer. Customize the capture configuration by specifying packet traversal paths on  switch extension layers and on the NDIS driver filter stack, along with configuring other special filters, such as packet **Truncation**, **EtherType**, and **IP Protocol Number** filters through use of the **Advanced Settings - Microsoft-Windows-NDIS PacketCapture** dialog.

-   **[Processing MOF-Generated Events](message-analyzer-tutorial.md#BKMK_MOFProviders)**  — fully parse messages that are captured by Message Analyzer from MOF-instrumented providers. Message Analyzer supports registered event providers on your system that use the MOF schema as the basis of generating their events.

-   **[Processing WPP-Generated Events](loading-wpp-generated-events.md)** — parse and display Windows software trace preprocessor (WPP)-generated events. Because such events make use of the ETW framework, Message Analyzer can capture them live or load them from a saved event trace log (ETL) file.  To enable parsing of WPP-generated events, users must provide supplementary information that defines the WPP event structure.

-   **[PEF-WFP Fast Filters](pef-wfp-fast-filters.md)**  — specify **Fast Filters** for the **Microsoft-PEF-WFP-MessageProvider** in a **Loopback and Unencrypted IPSEC** trace.

-   **[PEF-NDIS Fast Filters](pef-ndis-fast-filters.md)**  — configure logically chained **Fast Filter** groups that you assign to host adapters by using the **Advanced Settings - Microsoft-PEF-NDIS PacketCapture** dialog in a **Local Network Interfaces** trace on Windows 8 and earlier hosts.

-   **[Microsoft-Windows-NDIS-PacketCapture Provider](microsoft-windows-ndis-packetcapture-provider.md)**  — enabled for capturing remote traffic, with support for capturing from VMs that are managed by a Hyper-V-Switch. Also supports advanced filtering that includes packet direction, NDIS stack, and Hyper-V extension layer filters.

-   **[Microsoft-PEF-WFP-MessageProvider](microsoft-pef-wfp-messageprovider.md)**  — since Message Analyzer v1.3, the **Microsoft-PEF-WFP-MessageProvider** has had the capability to capture messages from remote computers that are running the Windows 10 operating system. You can capture this data in any **Trace Scenario** that uses this provider by starting a Live Trace Session from any computer that is running the Windows 8.1, Windows Server 2012 R2, or the Windows 10 operating system.

-   **[Capturing in Promiscuous Mode (P-Mode)](configuring-a-remote-capture.md#BKMK_PromiscuousMode)**  — configure the **Microsoft-Windows-NDIS-PacketCapture** provider to capture local or remote traffic on network adapters that support p-mode by simply selecting supporting adapters  in the interface selection list of the [Advanced Settings - Microsoft-Windows-NDIS-PacketCapture](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md) dialog.

-   **[Filtering Language](writing-filter-expressions.md)**  — discover how to write your own Filter Expressions for filtering data that is loaded into Message Analyzer, captured live, or analyzed after trace results are complete.

-   **[ResponseTime](average-response-time-for-operations.md)**  — add this **Global Annotation** entity from the **Field Chooser** as a data column in the **Analysis Grid** viewer. Enables you to measure the time interval between a request operation to a server and the first server response, to provide a context for assessing server performance.

-   **[OPN Definitions](viewing-opn-source-code.md)**  — display OPN definitions for capture modules or message fields from the **Analysis Grid** viewer or **Details** window context menu, respectively.

-   **[Analysis Grid Toolbar Features](analysis-grid-viewer.md#BKMK_AnalysisGridToolbar)**  — the **Analysis Grid** viewer now provides a toolbar for quick access to tools that assist in common analysis tasks.

-   **[Grouping Viewer](grouping-viewer.md)**  — select the **Grouping** viewer to organize your traffic into summary group hierarchies that expose targeted information that you can quickly extract from a large data set, which can otherwise be difficult to achieve.

-   **[Track Fields and Properties](message-details-tool-window.md#BKMK_UsingDetailsTracking)**  — a **Details** window feature that exposes the values of message-specific  fields, along with the additional global message properties and global annotations that are generated by Message Analyzer, to enable you to do the following from the **Details** window context menu:

    -   Utilize these new entities when configuring filters, groupings, adding columns, and so on.

    -   Track any message field, global property, or global annotation value — this enables you  to compare the value of the same field or property in other messages that you select or scroll to in the **Analysis Grid** viewer.

-   **[Pattern Match Viewer](pattern-match-viewer.md)**  — enables you to execute predefined **Pattern** expressions that locate message sequences or patterns that occur across a set of trace results, for example, a **TCP Three-Way Handshake** pattern. Also provides facilities for creating your own **Pattern** expressions, with or without user interface automation assistance.

-   **[Parse As](setting-message-analyzer-global-options.md)**  — a global **Options** dialog feature that enables you to parse an existing set of trace results with a different port value, for example, one that deviates from a standard port value for a particular protocol. Accommodates traces that used alternate port values for security purposes.

<a name="BKMK_NetmonUsers"></a>
## Important for Network Monitor Users
 Microsoft       Message Analyzer dramatically extends the network traffic diagnostics and analysis capabilities of Microsoft Network Monitor. This is enabled by a diverse set of data viewers and graphical view **Layouts** that create high-level data summaries; top-level messages and Operations with message stack and fragment encapsulation; **Viewpoints**, **Profiles**, and **Diagnosis** messages; and so on. In addition, Message Analyzer implements  former Network Monitor features that enable you to do the following:

-   Correlate process name and process ID data natively in Message Analyzer.

-   Simulate the Network Monitor message display with the Message Analyzer **Flat Message List** feature.

-   Simulate the Network Monitor **Network Conversations** tree with the Message Analyzer **Grouping** viewer.

For a high-level comparison of  Message Analyzer and Network Monitor features and why new approaches have been taken for capturing, displaying, and analyzing message traffic, see the following Message Analyzer Blog articles.

[Message Analyzer v1.3 vs Network Monitor v3.4](http://blogs.technet.com/b/messageanalyzer/archive/2015/07/23/microsoft-message-analyzer-v1-3-versus-network-monitor-v3-4.aspx)
[Message Analyzer: Why so different from Network Monitor?](http://blogs.technet.com/b/messageanalyzer/archive/2013/09/25/message-analyzer-why-so-different-from-network-monitor.aspx)