---
title: "Retrieving Azure Storage Blob Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a08bb925-f3e2-4377-a502-8e8a98d3f9f1
caps.latest.revision: 26
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Retrieving Azure Storage Blob Data
This topic shows you how to access and load data into Message Analyzer version 1.3 and later from log files that exist in Azure Storage binary large object (BLOB) containers. For Message Analyzer to successfully load and display this log data, you will need to provide some input connection information in order to access the BLOB repositories where the log data is saved. To access these repositories, you will use the **File Selector** dialog to select the files that contain the data you want to work with. After you specify such files and you exit the dialog, you must select a particular configuration file in your Data Retrieval Session for parsing the log data. If the **AzureStorageLog** configuration file does not exist in the **Text Log Configuration** drop-down list in your Data Retrieval Session configuration, you will need to download it through the Message Analyzer sharing infrastructure, as described in [Using the AzureStorageLog Parser](../messageanalyzer_content/retrieving-azure-storage-blob-data.md#BKMK_UsingAzureStorageLogParser), and then restart Message Analyzer.  
  
 __________________\_  
  
 **Go to Procedure**   
To proceed directly to a detailed procedure that you can follow to retrieve log data from Azure Storage BLOB containers, see [To access, load, and view log data from Azure storage BLOB containers](../messageanalyzer_content/procedures-using-the-data-retrieval-features.md#BKMK_LoadAzureLogData). Otherwise, you can review the [Workflow Overview](../messageanalyzer_content/retrieving-azure-storage-blob-data.md#BKMK_AzureWrkflowOverview).  
__________________\_  
  
<a name="BKMK_AccessingAzureLogs"></a>   
## Accessing Log Data in Azure Storage BLOB Containers  
 To connect with the Azure Storage BLOB repositories, you will need an **Account name** and **Account key**, which you should be able to obtain from your Azure portal. To input this information, you will need to open the **File Selector** dialog, which is accessible by clicking  **Open** from the Message Analyzer **File** menu and then selecting **From Other File Sources**. Thereafter, the **File Selector** dialog enables you to enter the connection information in the **Add Azure Storage Connection** dialog that displays when you click the **Add Azure Connection** button. After you specify the input connection data, you can navigate to the Azure Storage BLOB containers and select one or more log files from which to load data into Message Analyzer.  
  
> [!NOTE]
>  It is necessary to specify the input connection information only once for access to Azure logs, as long as you are still running the same Message Analyzer session where you initially specified such connection information. Otherwise, for security purposes, Azure account access is not persisted across Message Analyzer sessions.  
  
 The user interface for the **File Selector** dialog is shown in the figure that follows.  
  
 ![Azure  Blob File Selector dialog](../messageanalyzer_content/media/fig32-azure-blob-file-selector-dialog.png "Fig32-Azure  Blob File Selector dialog")  
  
 **Figure 32: Azure File Selector dialog**  
  
<a name="BKMK_UsingAzureStorageLogParser"></a>   
## Using the AzureStorageLog Parser  
 To load log file data into Message Analyzer from Azure Storage BLOB containers, a **Text Log Configuration** file is required for parsing the log data. After you target specific log files for input data and you click **OK** to exit the **File Selector** dialog, Message Analyzer displays the **New Session** dialog for a Data Retrieval Session, where the logs you specified are listed on the **Files** tab. In the session configuration, you will need to select the **AzureStorageLog** configuration file in the **Text Log Configuration** drop-down list to parse your Azure logs. If this file does not exist in the list, you will need to download it through the Message Analyzer sharing infrastructure.  
  
 The Azure parsers are available in the **Azure Storage Parsers Version x.x** asset collection that is accessible by clicking the Message Analyzer **Tools** menu and then selecting the **Asset Manager** command to display the **Asset Manager** dialog. To acquire the parsers in this collection, click the download icon (with the down-arrow indicator) to the right of the **Azure Storage Parsers** package on the **Downloads** tab of the **Asset Manager** dialog and then select the auto-sync option that appears in the **Item Download Options** dialog. When you click **OK** to exit this dialog, the Azure parser collection is downloaded to your Message Analyzer installation. Thereafter, you will receive automatic collection updates as they become available, as described in [Downloading Assets and Auto-Syncing Updates](../messageanalyzer_content/downloading-assets-and-auto-syncing-updates.md).  
  
 You can now select the **AzureStorageLog** configuration file in the **Text Log Configuration** drop-down list during Data Retrieval Session configuration.  
  
## Analyzing Azure Data  
 After Message Analyzer loads your Azure data, you can analyze and correlate the fields from the parsed input log file data by viewing it in **Analysis Grid** viewer columns. You can also make use of the **Field Chooser** **Tool Window** to display additional Azure data fields of interest, by adding them as columns to the **Analysis Grid** viewer for further analysis. The additional fields appear under the **AzureStorageLog** node when it is expanded in the **Field Chooser** window.  
  
<a name="BKMK_AzureWrkflowOverview"></a>   
## Workflow Overview  
 The following procedure outlines the general steps you can follow when configuring a Data Retrieval Session to load log data from Azure Storage BLOB containers into Message Analyzer:  
  
1.  Ensure that you have the **AzureStorageLog** parser before you get started. If you need this parser, follow the general instructions in [Using the AzureStorageLog Parser](../messageanalyzer_content/retrieving-azure-storage-blob-data.md#BKMK_UsingAzureStorageLogParser) to obtain it.  
  
2.  Open the **File Selector** dialog from the Message Analyzer **File** menu by highlighting **Open** and then selecting the **From Other File Sources** command.  
  
3.  In the **Add Azure Storage Connection** dialog, specify **Account name** and **Account key** information, as described in [Accessing Log Data in Azure Storage BLOB Containers](../messageanalyzer_content/retrieving-azure-storage-blob-data.md#BKMK_AccessingAzureLogs).  
  
4.  In the **Add Azure Storage Connection** dialog, ensure that the **Use HTTPS (Recommended)** option is selected as the **Connection** protocol.  
  
5.  Expand the nodes in the **File Selection** dialog until you expose the **Blobs** container and subfolders, so you can navigate to the log data you want to retrieve.  
  
6.  Select one or more .log files and then click **OK** to exit the **File Selector** dialog, at which time the **New Session** dialog displays to enable additional configuration of your Data Retrieval Session.  
  
7.  Select the **AzureStorageLog** configuration file in the **Text Log Configuration** drop-down list for each Azure log file in the files list of the **New Session** dialog.  
  
8.  Optionally, configure a **Time Filter** in the **New Session** dialog to narrow the scope of data retrieval, as described in [Applying an Input Time Filter to a Data Retrieval Session](../messageanalyzer_content/applying-an-input-time-filter-to-a-data-retrieval-session.md).  
  
9. Optionally, if you have the **Azure Storage Filter** asset package downloaded, select a predefined Azure filter from the **Azure Storage** category in the Filter Expression **Library** to create a resulting data set that focuses on specific information, as described in [Applying a Session Filter to a Data Retrieval Session](../messageanalyzer_content/applying-a-session-filter-to-a-data-retrieval-session.md).  
  
10. Ensure that the **Analysis Grid** viewer is selected in the **Start With** drop-down list and click **Start** to exit the **New Session** dialog and begin data retrieval.  
  
11. Observe that the log data displays in the **Analysis Grid** viewer.  
  
12. Optionally, use the **Field Chooser** window to enhance the view layout for the log data by adding one or more **Analysis Grid** viewer columns based on other fields of the parsed Azure log data.  
  
     Optionally, if you have the **Azure Storage View Layouts** asset package downloaded, change the **Analysis Grid** viewer column layout by selecting the **Storage Log** item in the **Layout** drop-down list. This layout is specifically designed to include key data fields for analysis of Azure storage logs.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about downloading and auto-syncing Message Analyzer assets, see [Managing Asset Collection Downloads and Updates](../messageanalyzer_content/managing-asset-collection-downloads-and-updates.md).   
**To learn more** about the **Field Chooser**, see the [Field Chooser Tool Window](../messageanalyzer_content/field-chooser-tool-window.md) topic.   
___________________\_  
  
## See Also  
 [Retrieving Azure Storage Table Data](../messageanalyzer_content/retrieving-azure-storage-table-data.md)