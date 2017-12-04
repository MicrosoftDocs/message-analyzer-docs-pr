---
title: "Handling Azure Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 692cc27b-c94a-4d93-ae91-12ef6d523e5c
caps.latest.revision: 24
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Handling Azure Data
To enhance your troubleshooting experience in the Cloud environment, Message Analyzer provides a simple way for you to browse for, select, and view data from log files that are stored in Azure binary large object (BLOB) containers. To access Azure logs in these containers, Message Analyzer provides a special dialog called the **File Selector**, which enables you to specify Azure connection information, navigate through folders and files in the BLOB containers, and then select the Azure log files you want to open. Message Analyzer also enables you to load input data from Azure tables by creating an **Azure** input configuration from the **New Session** dialog that specifies Azure connection information. The primary difference between Azure table data and the data obtained from an Azure log that is stored in a BLOB container is the format. Azure tables store messages in each row, whereas each column contains a corresponding message property that Message Analyzer parses as a field. Azure log data is typically stored in .log file format, which requires an OPN configuration file for Message Analyzer to parse it, as described in [Using the AzureStorageLog Parser](retrieving-azure-storage-blob-data.md#BKMK_UsingAzureStorageLogParser).  
  
> [!NOTE]
>  The **File Selector** was created to access stored files that Windows **File Explorer** does not support.  
  
## Limiting the Azure Data Retrieved  
 Just like any other input source that can provide data to Message Analyzer, you can configure and apply a **Time Filter** to limit the amount of Azure data you are loading, for better performance and to create focus on specific data that you want to view. Also, in the case of Azure log files, you can include a **Session Filter** from the **Azure Storage** category in the Message Analyzer Filter Expression **Library** that is accessible in the **New Session** dialog, to further narrow the scope of the data you want to retrieve. Because you can select one or more log files from Azure Storage BLOB containers as input to Message Analyzer, these filtering techniques are essential to facilitate cross-log analysis when you are merging and aggregating similar data from multiple high-volume logs. However, note that you might need to download the **Azure Storage Filters** asset collection with the use of the **Asset Manager** dialog, as accessible from the Message Analyzer **Tools** menu, to update your centralized Filter Expression **Library** to contain appropriate Azure filters in the **Azure Storage** category.  
  
## Viewing Azure Data  
 After Message Analyzer loads the data from your Azure log/s or table, you can view it as fields of data in the **Analysis Grid** viewer columns. You can also employ the **Field Chooser** **Tool Window** to add new data columns to the **Analysis Grid** viewer based on field names that are specific to the Azure storage logs or table, for enhanced analysis.  
  
## Specifying Azure Connection Information  
 In order to access Azure data from the previously mentioned sources, you will need to provide specific connection information. In the case of Azure tables, you will also need to enable the **Azure Table Import** preview feature on the **Features** tab of the global **Options** dialog and restart Message Analyzer.  
  
## Loading Azure Data  
 The following subtopics of this section describe how to get started with loading Azure data into Message Analyzer.  
[Retrieving Azure Storage Blob Data](retrieving-azure-storage-blob-data.md)  
[Retrieving Azure Storage Table Data](retrieving-azure-storage-table-data.md)  
  
 __________________\_  
  
 **Go To Procedure**   
For an example of how to retrieve Azure data, see the procedural topic [Retrieve Data from Log Files in Azure Storage BLOB Containers or from an Azure Table](procedures-using-the-data-retrieval-features.md#BKMK_RetrieveAzureData).   
__________________\_