---
title: "Merging and Aggregating Message Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307346b2-6b20-4e2b-b572-c4741f4c94e4
caps.latest.revision: 31
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Merging and Aggregating Message Data
A key feature of the Message Analyzer Browse-Select-View (BSV) model is that it enables you to merge the data from multiple files and aggregate data from multiple locations. This can be useful in scenarios where you are loading multiple log and/or trace files and you want to view and assess the data as a single message collection. If you start a Data Retrieval Session that loads data from multiple files at the same time, the data displayed by default in the **Analysis Grid** viewer will consist of an aggregation of chronologically sorted messages.  
  
## Merging Data From Multiple Sources and Locations  
 You can merge data from multiple sources by using the **Add Files** feature on the **Files** tab of a Data Retrieval Session. You can aggregate data from multiple locations by clicking the **New Data Source** tab in a Data Retrieval Session. Whenever you click this tab, a new **Files** tab displays, from where you can locate additional local or remote data sources. When you **Start** the Data Retrieval Session, the data from all sources is loaded into Message Analyzer and messages display in chronological order. You can also make use of the **New Data Source** tab when editing a session in the **Edit Session** dialog.  
  
> [!TIP]
>  After you specify multiple data sources with the use of the **New Data Source** tab in Data Retrieval Session configuration and you load the data, you can add the **DataSource** field to the **Analysis Grid** viewer as a new column. You can do this by right-clicking the **DataSource** field under the **General** node of the **Field Chooser** **Tool Window** and then selecting the **Add As Column** command. You can then right-click the **DataSource** column in the **Analysis Grid** viewer and select the **Group** command to conveniently group the messages according to the data source name.  
> In addition, if you have the **Grouping** viewer displayed, you can also add the **DataSource** field to this viewer as a new Group so you can organize the data by data source. You can do this by right-clicking the **DataSource** field in **Field Chooser** window and then selecting the **Add As Grouping** command. Thereafter, you can drag-and-drop the **DataSource** group label into the position occupied by the first group label in the current **Grouping** viewer **Layout**, as indicated by the red up and down arrows that display when a valid position is available on the **Layout** header. This action will organize your data into top-level **DataSource** groups, where the other groups of the displayed **Layout** will be sequentially nested subgroups.  
  
## Reconfiguring a Session to Aggregate More Data  
 To aggregate more data into an existing Data Retrieval Session for which results are being displayed, you can reconfigure it to add more saved data files. To begin, click the global Message Analyzer **Session** menu and then click the **Edit Session** command to display the **Edit Session** dialog. This dialog opens in the **Restricted Edit** mode as indicated in an information bar above the **Files** tab in the dialog. In this mode, you have only partial access to configuration features, which means that you can only add more files to the files list and **Apply** the change to load the messages contained in new file/s into the default data viewer. If you are loading a text log (.log file), you will also have access to the **Text Log Configuration** drop-down list for configuration file selection.  
  
 However, if you click the **Full Edit** button, you will have access to all the configuration features that are available for a Data Retrieval Session, such as a **Time Filter**, **Session Filter**, and check box selection/unselection of any files that existed in the session prior to reconfiguration. You should be aware that if you configure such features in **Full Edit** mode, it will trigger a reload of all the data from files that are selected in the files list when you **Apply** the changes. This is not critical, but performance could decline somewhat in this situation, depending on file sizes.  
  
> [!NOTE]
>  If you initially loaded data from one or more target input files and you then reconfigure the session by specifying one or more additional input files in the **Edit Session** dialog, the message data from the additional files will be *appended* to the existing message data in the **Analysis Grid** viewer after you load the data. If you also change to the **Full Edit** mode in the **Edit Session** dialog and make other configuration changes, Message Analyzer will reload all the data and then display it in chronological order in the **Analysis Grid** viewer, providing that you are using this viewer.  
  
 _____________\_  
  
## See Also  
 [Browse-Select-View Model](../messageanalyzer_content/browse-select-view-model.md)   
 [Editing Existing Sessions](../messageanalyzer_content/editing-existing-sessions.md)