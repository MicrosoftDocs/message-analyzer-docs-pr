---
title: "Configuring Session Scenarios with Selected Data Sources | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04a4e310-f1d6-4f9b-9174-fbf6ca30a694
caps.latest.revision: 33
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Configuring Session Scenarios with Selected Data Sources
When you are creating a Live Trace Session or  a Data Retrieval Session with Message Analyzer, you can make use of a flexible session framework that enables you to create session scenarios based on single or multiple data sources. For example, you might want to load data into Message Analyzer from a single set of related files, or you might be interested in correlating data from a particular system Event Log with a related set of trace results.  
  
 This section provides guidelines on how to use Message Analyzer to acquire data from one or more supported input data sources in any combination that you wish. You can take advantage of this capability when you need to correlate and analyze related data from different sources, given the enhanced analysis perspective that you can obtain in this context. This section describes input data source configurations, the data sources that are supported by Message Analyzer, an overview of creating input loading and capture configurations, along with a summary of guidelines that you can follow when configuring Live Trace Sessions or Data Retrieval Sessions with single or multiple input data sources.  
  
 As indicated in [Starting a Message Analyzer Session](../messageanalyzer_content/starting-a-message-analyzer-session.md), all session configuration begins with the **New Session** dialog.  
  
> [!IMPORTANT]
>  Message Analyzer does not support running a Live Trace Session and a Data Retrieval Session at the same time. Moreover, if you choose to run a Live Trace Session, all other supported input data sources are unavailable to add to the session.  
  
 The material of this section is covered in the following topics:  
  
 __________________________________\_  
  
 [Input Data Source Configurations](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_InputDataSourceConfigs)   
 [Supported Data Sources](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_SupportedDataSources)   
 [Live Trace Scenario Configuration](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_LiveTraceSessionConfig)   
 [Data Retrieval Scenario Configuration](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_DataRetrievalSessionConfig)   
 [Correlating Data from Multiple Input Sources](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_CorrelateDataFromInputSources)   
__________________________________\_  
  
<a name="BKMK_InputDataSourceConfigs"></a>   
## Input Data Source Configurations  
 When configuring session scenarios, you have the option to utilize a single input data source or multiple input data sources of different types. Drilling down further, you can also create session scenarios that use multiple inputs from one particular data source type that you choose. For example, you might create a session scenario that uses either of the following data source configurations:  
  
-   A single supported data source, optionally with multiple instances of such a single source, where  each instance specifies a unique session configuration with different filtering.  
  
     A single source might consist of a live trace that targets one or more computers on which to capture live data, or imported data that is sourced from a single file, a set of specified files, and/or multiple instances of either of these with different filtering configurations applied to each.  
  
-   Two or more different supported data sources, optionally with multiple instances of any particular source, where each instance specifies a unique session configuration with different filtering.  
  
     Different data sources might consist of two separate sets of files along with a PowerShell query, a SQL query, data from a specified Event Log, and/or multiple instances of these with different filtering configurations applied, that is, where it makes sense to do so.  
  
 The figure that follows is a Data Retrieval Session that is configured to retrieve data from two file sources and a PowerShell query. It also shows the other data source types that Message Analyzer supports on the **New Data Source** tab. Any of these sources could be added to this data loading configuration if correlation of data from such sources made sense.  
  
 ![Session configuration options](../messageanalyzer_content/media/fig39-session-configuration-options.png "Fig39-Session configuration options")  
  
 **Figure 39:  Session data source configuration options**  
  
 **Live Capture Configurations**   
For Live Trace Sessions, this means that you can create one or more unique capture configurations to acquire live data from  the local computer and/or from one or more remote computers. To create this type of session scenario, you would click the **Live Trace** button under **Add Data Source** in the **New Session** dialog. In the **New Session** dialog, you can accept the default and  collect live data from the local computer, or you can specify one or more remote computers on which to capture live data. If you want to create another capture configuration to acquire live data, for example from a different set of computers, simply click the **New Data Source** tab and then click the **Live Trace** button again to display the Live Trace Session configuration controls on another **Live Trace** tab. On each tab, the inherent controls enable you to create unique capture configurations that use different built-in **Trace Scenarios**, different ETW providers and provider configurations, and different types of filtering that together can create a capture focus that will return specific data from specified computers for analysis. You can then run all capture configurations simultaneously on the computers that you specified.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about creating capture configurations for Message Analyzer, see [Configuring a Live Trace Session](../messageanalyzer_content/configuring-a-live-trace-session.md).  
___________________\_  
  
 **Data Loading Configurations**   
For Data Retrieval Sessions, this means that you can create a unique data loading configuration that specifies a single data source consisting of a set of saved files that contain the data you want to examine with Message Analyzer. To create this type of session scenario, you  would click the **Files** button under **Add Data Source** in the **New Session** dialog. The controls for configuring a Data Retrieval Session then appear on a new **Files** tab, which can include various types of filtering features, truncation, and text log parsers. However, as previously indicated, you have the option to create multiple *sets* of input files, each with different loading configurations, by simply clicking the **New Data Source** tab and then clicking the **Files** button again. You could also create unique loading configurations that specify different target data sources. For example,  you could combine **Files**, **Event Log**, **PowerShell** query results, and data from other sources that you can load into Message Analyzer all at the same time for correlation and analysis. In addition, you have the option to specify multiple inputs for any of these sources, for example, multiple PowerShell queries that you specify on different **PowerShell** data source tabs.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about creating data loading configurations for Message Analyzer, see [Configuring a Data Retrieval Session](../messageanalyzer_content/configuring-a-data-retrieval-session.md).  
___________________\_  
  
<a name="BKMK_SupportedDataSources"></a>   
## Supported Data Sources  
 As previously indicated, Message Analyzer provides a separate configuration space for each type of data source, which appears as a separate tab in the **New Session** dialog when you click  a particular data source button under **Add Data Source** in the dialog. The input data sources that Message Analyzer supports consist of the following:  
  
> [!IMPORTANT]
>  Some of the following are preview features. To use a preview feature, ensure that it is selected in the **Preview Features** list on the **Features** tab of the **Options** dialog, which you can access from the global Message Analyzer **Tools** menu. If you enable a previously disabled feature, you will need to restart Message Analyzer in order to use the feature.  
  
-   **Live Trace** — enables you to capture live data from the network. You can create the input configuration for a Live Trace Session by clicking the **Live Trace** button under **Add Data Source** in the **New Session** dialog. A summary of the configuration features for a Live Trace Session is indicated  below in [Live Trace Scenario Configuration](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_LiveTraceSessionConfig).  
  
-   **Files** — enables you to retrieve data from saved trace and log files. You can create the input configuration for a Data Retrieval Session by clicking the **Files** button under **Add Data Source** in the **New Session** dialog. A summary of the configuration features for a Live Trace Session is indicated  below in [Data Retrieval Scenario Configuration](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_DataRetrievalSessionConfig).  
  
-   **Azure Table** — enables you to access data from an Azure table. You can create the input configuration by clicking the **Azure Table** button under **Add Data Source** in the **New Session** dialog.  
  
     You can also acquire input data from Azure storage binary large object (BLOB) logs with the use of the **File Selector**, which is accessible from the global Message Analyzer **File** menu, by selecting **Open** and then clicking the **From Other File Sources** command.  
  
     The configuration features that you can utilize when targeting Azure data is described in [Handling Azure Data](../messageanalyzer_content/handling-azure-data.md).  
  
-   **Event logs** — a preview feature that enables you to access data from **Microsoft Event Viewer** logs, such as **Applications and Services**, **Windows**, and others. You can create the input configuration by clicking the **Event Logs** button under **Add Data Source** in the **New Session** dialog.  
  
     The configuration features that you can utilize when targeting Event Log data is described in [Loading System Event Log Data](../messageanalyzer_content/loading-system-event-log-data.md).  
  
-   **PowerShell** query — a preview feature that enables you to access data that is output by a PowerShell query, which you create with one or more PowerShell cmdlets. You can create the input configuration by clicking the **PowerShell** button under **Add Data Source** in the **New Session** dialog.  
  
     The configuration features that you can utilize when targeting PowerShell query output data is described in [Deriving Input Data with PowerShell Scripts](../messageanalyzer_content/deriving-input-data-with-powershell-scripts.md).  
  
-   **SQL** query — a preview feature that enables you to access data from a SQL database table. You can create the input configuration by clicking the **Sql** button under **Add Data Source** in the **New Session** dialog.  
  
     The configuration features that you can utilize when targeting SQL table data is described in [Loading SQL Data](../messageanalyzer_content/loading-sql-data.md).  
  
-   **WPP-Generated Events** — Message Analyzer can process Windows software trace preprocessor (WPP)-generated events. Because WPP events make use of the ETW framework, Message Analyzer can capture them live or load them from a saved event trace log (ETL) file.  
  
-   **Operations Management Suite (OMS) logs** — Message Analyzer can load OMS log data, which enables you to leverage Message Analyzer data viewers and analysis capabilities when working with this type of data. To facilitate the process, Message Analyzer provides a search interface to OMS Log Analytics that you can access through the **Oms** data source feature of the **New Session** dialog during Data Retrieval Session configuration.  
  
<a name="BKMK_LiveTraceSessionConfig"></a>   
## Live Trace Scenario Configuration  
 To start the configuration for a Live Trace Session, open the **New Session** dialog from the **Start Page** and click the **Live Trace** button to display the configuration features for capturing data live with Message Analyzer. The configuration controls are contained on a **Live Trace** tab, which enable you to specify **Target Computers**, a built-in **Trace Scenario**, additional ETW providers, filtering configurations, and so on. Note that whenever you click the **New Data Source** tab in the **New Session** dialog for a Live Trace Session, you have the option to open another **Live Trace** tab in which you can specify a different **Trace Scenario** along with specified target hosts, unique filtering  criteria, and so on. In this session scenario, you can optionally specify any combination of the following for each selected **Trace Scenario**:  
  
-   **Computers** — the target computers on which to capture data.  
  
-   **Providers** — additional system ETW providers to enhance the scope of data capture, optionally with **Keyword** and/or **Level** filters set.  
  
-   **Provider Filters** — filtering configurations in the **Advanced Settings** dialog for message providers such as the **Microsoft-PEF-NDIS-PacketCapture** provider, **Microsoft-Windows-NDIS-PacketCapture** provider, and the **Microsoft-PEF-WFP-MessageProvider**. The **Advanced Settings** dialog is accessible by clicking the provider’s **Configure** link in the **ETW Providers** list on any **Live Trace** tab, after you select a **Trace Scenario** that contains one of the indicated providers. This enables you to create a unique filtering configuration for the selected **Trace Scenario** on each **Live Trace** tab.  
  
-   **ETW Session configuration** — settings for the underlying ETW Session for each **Trace Scenario**, which are accessible by clicking the **Configure ETW Session** button on each corresponding **Live Trace** tab.  
  
-   **Session Filtering** — a **Session Filter** will apply to any specified **Trace Scenario**.  
  
-   **Customized Parsing** — a **Parsing Level** will apply to any specified **Trace Scenario**.  
  
 After you start the Live Trace Session, Message Analyzer applies the filtering configurations and other settings that you specified to the live capture on the target computer/s. If you specified any remote computers in the **Target Computers** list on any **Live Trace** tab, Message Analyzer creates a separate sub-session of the Live Trace Session that captures messages on each specified remote computer. The data from all sub-sessions is returned and aggregated to the originating Live Trace Session when the session is stopped.  
  
> [!TIP]
>  After you have captured data from multiple data sources, in many cases you can organize them into separate data source groups in the **Analysis Grid** viewer by right-clicking the **DataSource** field in the **General** category of **Field Chooser** and then selecting the **Add as Grouping** command in the context menu that appears.  
  
### Live Trace Scenario Guidelines Summary  
 The following scenarios provide guidelines that summarize the approaches you can take to session configuration when you are preparing to capture messages live with Message Analyzer:  
  
-   **Local Capture : Single Live Trace configuration tab as data source** — enables you to capture messages from the local host with a single **Trace Scenario** and message provider configuration specified on one **Live Trace** tab when running a single Live Trace Session. Filtering configurations expectedly apply to the local host on which data is being captured.  
  
-   **Local Capture : Multiple Live Trace configuration tabs as data sources** — enables you to capture messages from the local host with different  **Trace Scenarios** and message provider configurations specified on separate **Live Trace** tabs when running a single Live Trace Session. Enables you to focus the trace results on messages at one or more stack levels or messages that pass specific filtering criteria.  
  
-   **Remote Capture : Single Live Trace configuration tab as data source** — enables you to capture messages concurrently from different target hosts with a *single* **Trace Scenario** and message provider configuration specified on one **Live Trace** tab when running a single Live Trace Session. Filtering configurations apply equally to all hosts on which data is being captured. Each trace that is running on a specified remote host is considered a sub-session of the originating Live Trace Session. Data that is captured in each sub-session is aggregated into the overall Live Trace Session results that display in a chosen data viewer.  
  
-   **Remote Capture : Multiple Live Trace configuration tabs as data sources** — enables you to capture messages concurrently from different target hosts with *different* **Trace Scenarios** and provider configurations specified on two or more **Live Trace** tabs when running a single Live Trace Session. You can apply unique filtering configurations independently for the providers in each **Trace Scenario** on different **Live Trace** tabs.  
  
     For example, you might specify different **Advanced Settings** for the **Microsoft-Windows-NDIS-PacketCapture** provider on each **Live Trace** tab. You could also utilize a different message provider and settings on the second or a subsequent **Live Trace** tab, such as the **Microsoft-PEF-WFP-MessageProvider**. Each trace that is running on a specified remote host is considered a sub-session of the originating Live Trace Session. Data that is captured in each sub-session is aggregated into the overall Live Trace Session results that display in a chosen data viewer.  
  
> [!NOTE]
>  In the **Target Computers** list on each **Live Trace** tab that you select during Live Trace Session configuration, you can specify a different set of hosts on which to capture data.  
  
<a name="BKMK_DataRetrievalSessionConfig"></a>   
## Data Retrieval Scenario Configuration  
 To start the configuration for a Data Retrieval Session, open the **New Session** dialog from the **Start Page** and click any button under **Add Data Sources** to display the configuration features for loading the particular type of data into Message Analyzer that you are targeting. For example, if you clicked the **Files** button, then you can use the **Add Files** feature in the **New Session** dialog to locate and target input files that contain the message data you want to load. After you specify an initial data source by clicking an appropriate button under **Add Data Source**, you can click the **New Data Source** tab in the **New Session** dialog to specify another data source type or another of the same source type to add to your initial input data source configuration.  
  
 For example, if you initially clicked the **Files** tab, you can specify a set of target input files from which to retrieve data by using the **Add Files** feature. At this point you can add a different data source as described in [Supported Data Sources](../messageanalyzer_content/configuring-session-scenarios-with-selected-data-sources.md#BKMK_SupportedDataSources), or you can create another set of input files by clicking the **New Data Source** tab, clicking the **Files** button, and then locating new files with the **Add Files** feature. In this example session scenario, you can optionally apply a differently configured input **Time Filter** to each target set of input files. After you start the Data Retrieval Session, Message Analyzer filters, loads, and chronologically merges all the data into a single viewer, which by default is the **Analysis Grid** viewer.  
  
 In any Data Retrieval Session, you can specify settings for the features that follow, although some of these might not have an effect on all the supported input data source types from which you can select. For example, in a  Data Retrieval Session that uses the **Files** button to import data from saved trace and log files, you can specify an input **Time Filter** to limit the data you retrieve to a specified window of time. Note that a **Time Filter** is available for use only with a target set of input files on the **Files** tab of a Data Retrieval Session, and not for any other data source:  
  
-   **Session Filter** — the effects apply  globally across all input data sources in a Data Retrieval Session.  
  
-   **Parsing Level** — the effects apply  globally across all input data sources in a Data Retrieval Session.  
  
-   **Time Filter** — the effects apply  only to specific input data source types in a Data Retrieval Session.  
  
> [!TIP]
>  After you have loaded data from multiple data sources, in many cases you can organize them into separate data source groups in the **Analysis Grid** viewer by right-clicking the **DataSource** field in the **General** category of **Field Chooser** and then selecting the **Add as Grouping** command in the context menu that appears.  
  
### Data Retrieval Scenario Guidelines  
 The following scenarios provide guidelines that summarize the approaches you can take to session configuration when you are preparing to load messages from one or more input sources into Message Analyzer:  
  
-   **Single data source and configuration tab** — enables you to retrieve messages from a single input data source that is specified on a single configuration tab in the **New Session** dialog. If you are retrieving data from one or more saved files or logs in this scenario, filtering configurations such as an input **Time Filter** or **Session Filter** apply equally to all specified input files. The Data Retrieval Session begins as soon as you click the **Start** button in the **New Session** dialog. The data that you load into Message Analyzer will appear in the viewer that you choose from the **Start With** drop-down list in the **New Session** dialog.  
  
    > [!TIP]
    >  If the input data source that you choose in this scenario is **Files**, each file that you target for data retrieval is effectively a data source.  
  
-   **Multiple data sources and configuration tabs** — enables you to retrieve messages from multiple input data sources that are each specified on a separate data source configuration tab in the **New Session** dialog. For example, if you are retrieving data from saved files in this scenario and you are using multiple data source tabs with a different set of input files on each tab, you can configure an input **Time Filter** that is specific only to the set of input files that appear on the  tab where you configure the filter. This enables you to independently apply different **Time Filter** parameters to different sets of input files on separate data source tabs. However, if you configure a**Session Filter** or **Parsing Level**, these will apply equally to all specified input files on all data source tabs in the session.  
  
     By utilizing multiple data source configurations with different filtering, you can create an output that merges specific messages from multiple input sources that you specified on two or more data source tabs. The Data Retrieval Session begins as soon as you click the **Start** button in the **New Session** dialog. The data that you load into Message Analyzer will appear in the viewer that you choose from the **Start With** drop-down list in the **New Session** dialog.  
  
<a name="BKMK_CorrelateDataFromInputSources"></a>   
### Correlating Data from Multiple Input Sources  
 Message Analyzer provides tools that are specifically designed to help you deal with the convergence of related data from multiple input sources. For example, if you had a hypothetical trace and log file that referred to an identical command with different names, you could create a **Union** that enables you to display the correlated field values under the **Union** name in a single data column of the **Analysis Grid** viewer. You can do this by using  the **Add as Column** command from the **Field Chooser** **Tool Window** context menu.  
  
 You could also make use of the **Group** feature in the **Analysis Grid** viewer to reorganize the data into grouped message configurations based on the values of chosen columns. For example, you could group all messages in a set of trace results by the values in the **ProcessId** column (a Global Property), so that you can view the message volume associated with each process. Moreover, you might also use the **Grouping** viewer, which performs a similar function,  although this viewer provides built-in view **Layouts** that you can select for a more focused analysis of  specific groups of data. The **Grouping** viewer also enables you to correlate messages that exist in any particular group, which can include a **Data Source** group,  by driving the display of those messages in the **Analysis Grid** viewer for a detailed level of analysis. You can also make use of the **Selection** **Tool Window** to keep track of correlated messages that you select, for example, the messages that you selected in the **Analysis Grid** viewer, or groups of messages that you selected in the **Grouping** viewer when the **Selection Mode** is active.  
  
 Other Message Analyzer tools that support data correlation include **Filters**, **Viewpoints**, and sorting. For example, you can use a view **Filter** to isolate specific data that you want to examine, by filtering for only the types of messages you want to analyze. You could also use a **Viewpoint** to remove messages above a selected **Viewpoint** module that are irrelevant to your analysis goals. Sorting can be particularly useful when you have acquired data from multiple sources that have time stamp differences. In many cases, you will want to correlate your input data sources by time so that you can more easily correlate data that is identical or  closely related, but with different time stamps. For example, you could sort the **Timestamp** column in the **Analysis Grid** viewer, and when necessary, add a **Time Shift** to messages from a log that gathered data in a different time zone or where message data is offset because of other factors such as skewed system times.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about **Unions**, see [Configuring and Managing Message Analyzer Unions](../messageanalyzer_content/configuring-and-managing-message-analyzer-unions.md).  
**To learn more** about the **Group** feature in the **Analysis Grid** viewer, see [Using the Analysis Grid Group Feature](../messageanalyzer_content/using-the-analysis-grid-group-feature.md).  
**To learn more** about the **Grouping** viewer, see the [Grouping Viewer](../messageanalyzer_content/grouping-viewer.md) topic.  
**To learn more** about the **Selection** **Tool Window**, see the [Selection Tool Window](../messageanalyzer_content/selection-tool-window.md) topic.  
**To learn more** about **Filters**, see [Applying and Managing Filters](../messageanalyzer_content/applying-and-managing-filters.md).  
**To learn more** about **Viewpoints**, see [Applying and Managing Viewpoints](../messageanalyzer_content/applying-and-managing-viewpoints.md).  
**To learn more** about setting time shifts, see [Setting Time Shifts](../messageanalyzer_content/setting-time-shifts.md).  
___________________\_  
  
## See Also  
 [Acquiring Data From Other Input Sources](../messageanalyzer_content/acquiring-data-from-other-input-sources.md)   
 [Configuring a Live Trace Session](../messageanalyzer_content/configuring-a-live-trace-session.md)   
 [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md)   
 [Configuring a Data Retrieval Session](../messageanalyzer_content/configuring-a-data-retrieval-session.md)