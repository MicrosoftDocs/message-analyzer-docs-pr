---
title: "Acquiring Data From Other Input Sources | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bc46b46-fed8-4cf4-81a9-1a45ab451d42
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Acquiring Data From Other Input Sources

Beyond  live captures and saved files, Message Analyzer enables you to utilize  additional sources to acquire input data for enhanced analysis capabilities. As provided in the **New Session** dialog, you can create the configuration for a Live Trace Session by clicking the **Live Trace** button under **Add Data Source** to capture data live from the network. You can also create the configuration for a Data Retrieval Session by clicking the **Files** button under **Add Data Source** in the **New Session** dialog, which enables you to target save files (traces and logs) as input to Message Analyzer. However, there are several other input sources under **Add Data Source** from which you can load data into Message Analyzer through a Data Retrieval Session, as follows:

> [!NOTE]
> WPP-generated events are included in the list below because they are an additional input data source for Message Analyzer. However, the **Add Data Source** feature in the **New Session** dialog does not provide access to the configuration required to set up for processing WPP events. To learn more about how to capture or retrieve WPP events, see [Loading WPP-Generated Events](loading-wpp-generated-events.md).

- **Azure data** — provides access to data from an Azure table. You can create the input configuration by clicking the **Azure Table** button under **Add Data Source** in the **New Session** dialog.

     You an also acquire input data from Azure storage binary large object (BLOB) logs with the use of the **File Selector**, which is accessible from the global Message Analyzer **File** menu, by selecting **Open** and then clicking the **From Other File Sources** command.

- **Event logs** — a preview feature that provides access to data from **Microsoft Event Viewer** logs, such as **Applications and Services**, **Windows**, and others. You can create the input configuration by clicking the **Event Logs** button under **Add Data Source** in the **New Session** dialog.

- **PowerShell query** — a preview feature that provides access to data that is output by a PowerShell query, which you create with one or more PowerShell cmdlets. You can create the input configuration by clicking the **PowerShell** button under **Add Data Source** in the **New Session** dialog.

- **SQL query** — a preview feature that provides access to data from a SQL database table. You can create the input configuration by clicking the **Sql** button under **Add Data Source** in the **New Session** dialog.

- **WPP-Generated Events** — Message Analyzer can process Windows software trace preprocessor (WPP)-generated events. Because WPP events make use of the ETW framework, Message Analyzer can capture them live or load them from a saved event trace log (ETL) file.

- **Operations Management Suite (OMS) logs** — Message Analyzer can load OMS log data, which enables you to leverage Message Analyzer data viewers and analysis capabilities when working with this type of data.  To facilitate the process, Message Analyzer provides a search interface to OMS Log Analytics that you can access through the **Oms** data source feature of the **New Session** dialog during Data Retrieval Session configuration. Note that OMS is a preview feature.

> [!IMPORTANT]
> To use a preview feature, ensure that it is selected in the **Preview Features** list on the **Features** tab of the **Options** dialog, which you can access from the global Message Analyzer **Tools** menu. If you enable a previously disabled feature, you will need to restart Message Analyzer in order to use the feature.

 The above input data sources are described in the following topics of this section:

---

 [Handling Azure Data](handling-azure-data.md)
 [Loading System Event Log Data](loading-system-event-log-data.md)
 [Deriving Input Data with PowerShell Scripts](deriving-input-data-with-powershell-scripts.md)
 [Loading SQL Data](loading-sql-data.md)
 [Loading WPP-Generated Events](loading-wpp-generated-events.md)
 [Loading OMS Log Data](loading-oms-log-data.md)

---

## Combining Input Data Sources

 You can use any of the previously specified input data sources alone, or you can combine two or more input sources so that you can correlate and analyze related data from different sources. For example, you might combine a saved trace file with a particular Event Log to correlate data from captured messages versus event log entries, for enhanced analysis. Given that some of the input data sources  are preview features, you might also come up with some inventive ways to combine data sources in other ways. For example,  you might combine a PowerShell query or a SQL database table with another input source. In the case of a PowerShell query, you could acquire process IDs on a specified remote computer and correlate that data with a network trace saved in an ETL file. For this particular scenario, Message Analyzer has some assets that are specifically designed to process this type of data, for example, the **Grouping** viewer which can correlate process names and IDs.

---

## See Also

 [Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md)
 [Grouping Viewer](grouping-viewer.md)