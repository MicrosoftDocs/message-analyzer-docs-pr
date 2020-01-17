---
title: "Locating Supported Input Data File Types | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe77198e-4b3f-4832-b259-79fad6b11a4a
caps.latest.revision: 60
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Locating Supported Input Data File Types

To locate saved data that you want to load into Message Analyzer from supported file types and to access session configuration features prior to loading the data, you should first create a Data Retrieval Session as described in [Starting a Message Analyzer Session](starting-a-message-analyzer-session.md). To load data very quickly from supported file types into Message Analyzer without accessing the session configuration settings of the **New Session** dialog, you can use any of the methods described in [Performing Data Retrieval](performing-data-retrieval.md). The exception to these “fast” methods is for text log files with a .log extension, where instead, Message Analyzer automatically opens the **New Session** dialog so that you can select a **Text Log Configuration** file that is required for parsing text logs.  
  
> [!NOTE]
>  For Data Retrieval Sessions that contain a large message collection with many files targeted for loading data, you can search the files list to quickly locate any file by specifying file name characters in the search text box on the toolbar of the **Files** tab. For easy location capability, you should consider using relevant file naming conventions, as described in [Naming Saved Files](naming-saved-files.md), when saving files from which you expect to reload data at some point.  
  
## Supported Input File Types  

 The data that you load into Message Analyzer must be derived from one or more of the supported file types, as described in the table that follows. Some of these file types are in Message Analyzer default native format while others are non-native. Some input files have certain requirements, as indicated in the table. Note that you can save Message Analyzer data in the .matp native file format only, even if you initially loaded data from a message file that has a non-native format.  
  
### Table 9.  Message Analyzer Supported Input File Types  
  
|**Message file name extension**|**Description**|**Support**|**Uses/Requirements**|  
|-|-|-|-|  
|.aztable|Azure table storage|Non-native|Display data from Azure table storage (requires input connection information, as described in [Retrieving Azure Storage Table Data](retrieving-azure-storage-table-data.md)).|  
|.blg|Binary performance file (PerfMon)|Non-native|Standard input file support. A Message Analyzer **Profile** is available for this input file type.|  
|.cap|Network Monitor capture file|Native|Open Network Monitor .cap files. Note that Message Analyzer can export trace data in the .cap file format. Several Message Analyzer **Profiles** are available for this input file type.|  
|.csv|Comma Separated Value file|Non-native|Standard input file support.|  
|.dmp|Crash Dump Files|Non-native|Standard input file support.|  
|.etl|Windows event trace log file|Non-native|Open .etl files with embedded manifests containing event metadata per event. Otherwise, may require generating an ETL manifest; see [Understanding Event Parsing with a Provider Manifest](understanding-event-parsing-with-a-provider-manifest.md). Several Message Analyzer **Profiles** are available for this input file type.|  
|.evtx|Event log file|Non-native|Standard input file support. A Message Analyzer **Profile** is available for this input file type.|  
|.json|Javascript object notation log files|Non-native|Standard input file support.|  
|.log|Textual log file|Non-native|Requires either selecting or creating an OPN Configuration file; see [Opening Text Log Files](opening-text-log-files.md). Note that the OPN configuration file selection requirement also applies to Azure storage logs. Message Analyzer **Profiles** are available for this input file type.|  
|.matp|Compressed trace parsed file|Native|Open files saved in Message Analyzer native file format.|  
|.matu|Compressed trace unparsed file|Native|Open Message Analyzer unparsed (.matu) files or PowerShell initiated traces that are saved in the same unparsed file format; see the [Save-PefMessageCollection](http://technet.microsoft.com/library/dn456523.aspx) cmdlet documentation.|  
|.oms|Operations Management Suite (OMS) logs|Non-native|Requires an Azure Subscription and credentials to log in to Azure, as described in [Loading OMS Log Data](loading-oms-log-data.md).|  
|.opn|Open Protocol Notation files|Native|Display the source code for any OPN message parser.|  
|.pcap|Packet capture trace file|Non-native|Standard input file support. Message Analyzer **Profiles** are available for this input file type.|  
|.pcapng|PCAP next generation trace file|Non-native|Standard input file support. Message Analyzer **Profiles** are available for this input file type.|  
|.pmlcsv|Process monitor (procmon) trace file|Non-native|Requires changing a procmon file that was saved in .csv format to use the .pmlcsv file extension, to map properly to the correct Message Analyzer data loader.|  
|.pmlxml|Process monitor (procmon) trace file|Non-native|Standard input file support.|  
|.ps1|PowerShell script file|Non-native|Requires a script that runs a specified cmdlet, for example, to get event log data or target input files as a data source.|  
|.saz|Session Archive Zip files|Non-native|Open Fiddler archives containing HTTP(s) data. A Message Analyzer **Profile** is available for this input file type.|  
|.sqltable|SQL table files|Non-native|Standard input file support.|  
|.trc|Network Associates Sniffer - DOS files|Non-native|Standard input file support.|  
|.tsv|Tab Separated Value file|Non-native|Standard input file support.|  
|.xml|XML file|Non-native|Standard input file support.|  

---

 **More Information**   
 **To learn more** about how to use Message Analyzer **Profiles** to automatically display a predefined viewer and layout configuration for  a targeted analysis context when loading data from  applicable file types, see [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md).  
**To learn more** about different methods that you can use to quickly load data into Message Analyzer, see [Performing Data Retrieval](performing-data-retrieval.md).  
**To learn more** about saving your message data in the native .matp file format, see [Saving Files in Native Format](saving-files-in-native-format.md).  
**To learn more** about how to create an OPN Configuration file for a text log, see the [OPN Configuration File for Textlog Adapter](http://download.microsoft.com/download/C/D/E/CDED67DB-2C74-4FE4-B184-123CEE0E273F/OPN%20Configuration%20Guide%20for%20Text%20Log%20Adapter%20V2.docx) document download.   

---