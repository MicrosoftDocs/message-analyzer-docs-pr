---
title: "Using the Go To Message Feature | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 66a69ebf-86ed-48c1-9228-1418b26d421a
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Using the Go To Message Feature
To simplify the search for a specific message by message number, Message Analyzer provides the **Go To Message** dialog, which is accessible from the **Analysis Grid** viewer toolbar. As a tool that enables you to quickly navigate to a particular message in a large data set, it can accelerate your analysis process, for example, in analysis scenarios where you are being directed to quickly locate specific data. Note that the **Go To Message** feature is enabled for multiple data sources, meaning that you can elect to search all data sources or a specified source.  
  
## Locating Messages  
 The **Go To Message** feature locates messages in the **Analysis Grid** viewer only, based on entering a numerical message number in the **Go To Message** dialog. This also includes locating messages in any Grouped message display that you create in the **Analysis Grid** viewer. If a match is found, the message of interest is highlighted in the **Analysis Grid** viewer. Even if the message is hidden within unexposed origin tree nodes, the **Go To Message** feature expands the origins nodes to whatever level is necessary to select the message of interest and make that selection visible. In addition, if you happen to have a Grouped display of message data in the **Analysis Grid** viewer, the **Go To Message** feature will expand any Group node in which the message exists, select the message, and thereby make the selection visible. This provides a quick and convenient method for locating specific messages that you want to examine.  
  
## Searching Multiple Data Sources  
 The **Go To Message** dialog also provides several options for searching through trace results, based on selection of sources that collected data for the particular session in which you are searching for messages. These options consist of the following:  
  
-   **Search All Data Sources** — select this check box in the **Go To Message** dialog to search all session data sources for a specified message number entry. Currently, the **Go To Message** will find only the first message in any data source that matches the message number you entered in the dialog.  
  
-   **Data Source** drop-down list — select an item from this list to specify the data source that contains the message source you want to search for a specified message number entry.  
  
 The previously described options appear in the **Go To Message** dialog only if a particular session contains more than one data source. This scenario is common when you have multiple traces or logs that contain related message data that you need to consolidate for analysis purposes. When you load this type of input data configuration into Message Analyzer, it results in messages from such consolidated data sources displaying in chronological order, interlacing them as the chronology requires it. Note that there are two ways that you can create a session that has more than one data source, as follows:  
  
-   **Add files** — when configuring a Data Retrieval Session, you can use the **Add Files** feature in the **New Session** dialog to add multiple files to the file list on the **Files** tab. Each file that you add is considered a data source, which could be a saved trace or log file. Thereafter, when you launch the **Go To Message** dialog, the data sources listed in the **Data Source** drop-down list might be identified by a trace file name, log file name, or could be associated with a session GUID.  
  
-   **New data sources** — when configuring a Live Trace Session, you can select different **Trace Scenarios** on two or more **Live Trace** tabs to create multiple data sources. To do this, you will create at least one additional **Live Trace** tab to contain a **Trace Scenario** by clicking the **New Data Source** tab.  
  
    > [!NOTE]
    >  When configuring a Data Retrieval Session, you can likewise make use of the **New Data Source** tab to specify multiple **Files** tabs in the **New Session** dialog, where each **Files** tab contains a different data source, such as a saved trace or log file. On each **Files** tab, you can locate the saved traces or logs that will be your data sources by clicking the **Add Files** button and navigating to those sources.  
  
## Displaying the Go To Message Dialog  
 To display the **Go To Message** dialog, an **Analysis Grid** viewer session tab must be in focus in order to expose the toolbar on which the **Go To Message** button exists. Then, you can either click the **Go To Message** button on the **Analysis Grid** viewer toolbar, or you can simply use the keyboard shortcut `Ctrl+G` to open the dialog.  
  
## Improved Method for Locating Messages  
 Prior to the introduction of this feature, you may have experienced the inconvenience of having to write a **Find Message** filter to locate a message. If you did, then it probably looked similar to the following:  `#messagenumber==1234`. Matches found in these cases are located to the top-level message only, which was then highlighted.  
  
 At that point, if you performed a subsequent click of the **Find** binoculars icon, a **Find Message** information bar displayed with the message “**Finished finding all messages**”, as if the message was found, when actually it was not. When this occurred, you needed to perform multiple successive clicks to expand nodes and navigate the message layers until the actual message of interest was found. Even if the top-level message node and underlying child nodes were completely expanded to expose the message stack, you were still required to perform subsequent clicks of the **Find** binoculars icon to step through the open layers in succession. Even then, the search may have unexpected results at times.  
  
 The **Go To Message** feature enables you to avoid all this, as it provides a more convenient and quicker method for locating messages. However, please note that the **Find Messages** feature is still very useful in finding messages that meet the criteria of a **Find Messages** filter that you specify from the **Message Analyzer Filters** asset collection **Library** drop-down list and apply to a search.