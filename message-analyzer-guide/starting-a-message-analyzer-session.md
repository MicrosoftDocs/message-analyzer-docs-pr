---
title: "Starting a Message Analyzer Session | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 601acb0e-83dc-4f6a-bae6-21ae3b23bff8
caps.latest.revision: 42
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Starting a Message Analyzer Session

The basic unit of workflow and starting point of all Message Analyzer operations is a session. A *session* is the instrument that you will configure and then use to collect data that you want to analyze, whether you capture it live on a network or load it into Message Analyzer from saved message files, logs, or other sources. The user interface (UI) for configuring a new session is designed to provide an optimal workflow experience and enables you to utilize essentially two types of Message Analyzer sessions to acquire input data, as follows:  
  
-   **Live Trace Session** — enables you to specify a session configuration that captures message data live from network traffic, system components, or devices.  
  
-   **Data Retrieval Session** — enables you to specify a session configuration that acquires input message data from multiple disparate data sources, such as saved files, logs, and others.  
  
---  
  
 **Go To Quick Session Startup**   
To learn how to immediately start a Message Analyzer session that captures live data at the Link Layer with a single click, see the [Quick Session Startup](quick-session-startup.md) topic.  
---  
  
 **Streamlining Session Input Workflow**   
The Message Analyzer UI provides a streamlined input workflow architecture that is designed to support expansive data collection capabilities, which includes the future addition of new data sources. Currently, Message Analyzer data collection capabilities include the simultaneous capture of live data from a local host and/or multiple remote target computers, as described in [Configuring a Live Trace Session](configuring-a-live-trace-session.md), [Configuring a Remote Capture](configuring-a-remote-capture.md),  and [Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md); in addition to retrieval of data from multiple saved data sources, as described in [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md) and [Acquiring Data From Other Input Sources](acquiring-data-from-other-input-sources.md).  
  
 Message Analyzer also provides an integrated session configuration workflow that minimizes the number of clicks and dialogs you need to get a Live Trace Session or a Data Retrieval Session running, while making configuration features that are common to both session types readily accessible and easy to configure.  
  
 **Configuring a New Session: Overview**   
All of the foregoing capabilities are unified through the use of a common interface that is called the **New Session** dialog. This dialog is accessible by clicking the **New Session** item in the Message Analyzer **File** menu, or by simply clicking the **New Session** button on the Message Analyzer **Start Page** or on the global Message Analyzer toolbar. From the **New Session** dialog, you can choose the type of session you want to start, such as a Live Trace Session or a Data Retrieval Session:  
  
-   **Live Trace Session** — you can begin the configuration of a Live Trace Session by clicking the **Live Trace** button under **Add Data Source** in the **New Session** dialog. The configuration features that are unique to this type of session enable you to do the following:  
  
    -   Target local and/or remote computers from which to capture live data with the use of the **Edit Target Computers** dialog, which is accessible by clicking the **Edit** button next to the **Target Computers** text box, as described in [Configuring a Remote Capture](configuring-a-remote-capture.md).  
  
    -   Choose a built-in **Trace Scenario** from the **Select Scenario** drop-down list that includes one or more message providers that capture network messages through different stack layers, or from system components and other devices, as described in [Selecting a Trace Scenario](selecting-a-trace-scenario.md).  
  
    -   Add one or more system ETW Providers to any **Trace Scenario** to enhance the scope of data retrieval, by selecting them from the **Add Providers** drop-down list, as described in [Adding a System ETW Provider](adding-a-system-etw-provider.md).  
  
    -   Specify various filtering configurations for message providers, including **Fast Filters**, **WFP Layer Set** filters in **Trace Scenarios** that use the **Microsoft-PEF-WFP-MessageProvider**; event **Keyword** and error **Level** filters; adapter filters and logically chained **Fast Filter** groups in **Local Network Interfaces** traces; NDIS stack, Hyper-V-Switch extension layer, and other special filters in traces that use the **Microsoft-Windows-NDIS-PacketCapture** provider, for example **Remote Network Interfaces** traces that have remote capture capability; and so on, as described in [Configuring a Live Trace Session](configuring-a-live-trace-session.md).  
  
    -   Specify **ETW Session Configuration** parameters to control performance of the underlying ETW sessions in all traces, as described in [Specifying Advanced ETW Session Configuration Settings](specifying-advanced-etw-session-configuration-settings.md).  
  
-   **Data Retrieval Session** — you can begin the configuration of a Data Retrieval Session by clicking the **Files** button under **Add Data Source** in the **New Session** dialog. The configuration features that are unique to this type of session enable you to do the following:  
  
    -   Locate saved files and logs from which to retrieve message data, as described in [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md).  
  
    -   Enable the **Truncated Parsing** mode to initiate a smaller Message Analyzer parsing set that improves performance when loading saved files that contain truncated messages, for example a .cap file, as described in [Detecting and Supporting Message Truncation](detecting-and-supporting-message-truncation.md).  
  
    -   Decrypt the data in saved files, as described in [Decrypting Input Data](decrypting-input-data.md).  
  
    -   Configure a **Time Filter** that specifies a window of time in which to view data, to focus results and improve performance, as described in [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).  
  
    -   Configure and apply a **Session Filter** to focus results on specific data and improve performance, as described in [Applying a Session Filter to a Data Retrieval Session](applying-a-session-filter-to-a-data-retrieval-session.md).  
  
    -   Select a **Text Log Configuration** file for parsing a custom textual log file, as described in [Opening Text Log Files](opening-text-log-files.md).  
  
    -   Load data that is derived from execution of PowerShell scripts, as described in [Deriving Input Data with PowerShell Scripts](deriving-input-data-with-powershell-scripts.md).  
  
    -   Load data from Azure storage tables and from text log files that are stored in binary large object (BLOB) containers, as described in [Handling Azure Data](handling-azure-data.md).  
  
    -   Load data from various other input sources such as system Event Logs, SQL databases, WPP-generated events, and OMS log data, as described in [Acquiring Data From Other Input Sources](acquiring-data-from-other-input-sources.md).  
  
 The configuration features of the **New Session** dialog that are common to both session types enable you to do the following:  
  
-   Specify a **Session Filter** that limits the data you capture or retrieve based on specific filtering criteria.  
  
-   Select a **Parsing Level** to limit how far up the stack Message Analyzer will parse, for better performance and focused message sets, as described in [Setting the Session Parsing Level](setting-the-session-parsing-level.md).  
  
-   Choose a data viewer in which to display your trace results by selecting one in the **Start With** drop-down list, or use the default viewer setting, as described in [Selecting a Session Data Viewer](selecting-a-session-data-viewer.md).  
  
-   Provide a **Name** for the new session, as described in [Naming a Session](naming-a-session.md).  
  
 **Using Session Options**   
The **New Session** item in the Message Analyzer **File** menu provides the following submenu items as options for creating a session:  
  
-   **Blank Session** — creates an unconfigured new session.  
  
-   **From Current Session** — creates a new session based on the configuration of a currently open and selected session.  
  
 **Creating a New Session: Workflow Overview**   
To familiarize yourself with the workflow you will generally follow when creating a basic session configuration, follow the steps below to create a session that captures data live or retrieves data from saved files and logs:  
  
### General Workflow Process  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. If you have not logged off and back on after first installing Message Analyzer, then restart Message Analyzer and use the right-click **Run as Administrator** option.  
  
2.  Click the **New Session** button on the Message Analyzer **Start Page** to display the **New Session** dialog.  
  
     Alternatively, click the **New Session** item in the Message Analyzer **File** menu to display the **New Session** dialog.  
  
3.  To start session configuration, do one of the following under **Add Data Source** in the **New Session** dialog:  
  
    -   Click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains in the **New Session** dialog, to begin configuration of a Live Trace Session.  
  
    -   Click the **Files** button to display the **Files** tab along with the associated session configuration features that it contains in the **New Session** dialog, to begin configuration of a Data Retrieval Session.  
  
4.  If you chose to configure a Live Trace Session, do the following to create a basic configuration; otherwise, proceed to step 5:  
  
    -   Use the default **Localhost** setting in the **Target Computers** list on the **Live Trace** tab of the **New Session** dialog, to capture data from the local computer only.  
  
    -   Choose a built-in **Trace Scenario** in the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **Live Trace** tab to define the scope of the data you will capture.  
  
    -   Optionally, select a built-in Filter Expression from the **Library** drop-down list on the toolbar above the **Session Filter** text box to create a **Session Filter** that narrows the scope of data capture, so you can focus on a specific type of data in your trace results.  
  
    -   Choose a data viewer in which to display the results of your Live Trace Session by selecting it in the **Start With** drop-down list of the **New Session** dialog; or accept the default setting.  
  
    -   To review additional configuration options for a Live Trace Session, see [Configuring a Live Trace Session](configuring-a-live-trace-session.md).  
  
5.  If you chose to configure a Data Retrieval Session, do the following to create a basic configuration:  
  
    -   Navigate to the trace or log files that contain the data you want to load into Message Analyzer by clicking the **Add Files** button on the toolbar of the **Files** tab in the **New Session** dialog; this action launches the **Open** dialog.  
  
    -   From the **Open** dialog, locate and select the files that contain the data to be loaded into Message Analyzer. Click **Open** to exit the dialog.  
  
         The file names appear in the files list on the **Files** tab. Note that this list indicates only the supported files that are targeted for file reads during the data loading process, given that at this point, no data has yet been loaded into Message Analyzer.  
  
    -   Optionally, select specific files in the files list on the **Files** tab of the **New Session** dialog to create a collection of messages to be loaded from a specified subset of files.  
  
    -   Optionally, configure a **Time Filter** to define a window of time in which to retrieve data and create focus on a smaller and targeted set of retrieved messages for enhanced analysis.  
  
    -   Optionally, select a built-in Filter Expression from the **Library** drop-down list on the toolbar above the **Session Filter** text box to create a **Session Filter** that narrows the scope of data retrieval, so you can focus on a specific type of data in your retrieved results.  
  
    -   To review additional configuration options for a Data Retrieval Session, see [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md).  
  
---  
  
 **What You Will Learn**   
In the topics of this section, you will learn in detail how to  perform the tasks that are described below, which includes how to: capture data live, retrieve saved data, configure different session scenarios, and edit an existing Data Retrieval Session or Live Trace Session.   

---  
  
## In This Section  
 **[Capturing Message Data](capturing-message-data.md)**  — learn how to use Message Analyzer assets to target live data as an input source in a local or remote capture; configure, run, and edit a Live Trace Session; create your own custom **Trace Scenarios**; and use various methods to perform a live capture.  
  
 **[Retrieving Message Data](retrieving-message-data.md)**  — learn how to use Message Analyzer to target saved data and other repositories as an input source; configure, run, and edit a Data Retrieval Session; and use various methods to perform data retrieval.  
  
 **[Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md)**  — learn how to use Message Analyzer's flexible session framework to create session configurations based on single or multiple data sources. Also review some example scenarios and guidelines for Data Retrieval Sessions and Live Trace Sessions.  
  
 **[Editing Existing Sessions](editing-existing-sessions.md)**  — learn how to reconfigure an existing session to obtain different results.  
  
---  
  
 **Go To Procedures**   
To proceed directly to procedures that demonstrate how to use the network tracing features, see **[Procedures: Using the Network Tracing Features](procedures-using-the-network-tracing-features.md)**.  
To proceed directly to procedures that demonstrate how to browse for saved messages, retrieve selected data from saved files, and view the resulting message set, see **[Procedures: Using the Data Retrieval Features](procedures-using-the-data-retrieval-features.md)**.   

---