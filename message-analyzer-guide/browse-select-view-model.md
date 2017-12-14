---
title: "Browse-Select-View Model | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a30b8967-b0ee-41e3-a849-c9c89b1db7bc
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Browse-Select-View Model
Microsoft Message Analyzer utilizes a unique set of Browse-Select-View (BSV) features that provide a versatile model for acquiring data, selecting specific data from the acquisition process, and presenting the data in various viewer formats. The BSV model allows you to navigate to saved log and trace files and to create a retrieval configuration that targets the data in specific files from which you choose to retrieve data. The model also enables you to extract subsets of message data from high volume trace files rather than extracting all data in target files, which can affect performance, impact memory usage, and make it difficult to work with the data.  Because you can extract specific data from saved files, you save time upfront and clarify your troubleshooting efforts later on. The model also enables you to combine data from different sources, such as logs and trace files, and to view data from multiple sources in a single merged view.  
  
 The data selection aspect of the BSV model also applies to acquiring specific data through a live capture. For example, you can use various filters and different **Trace Scenarios** to isolate the precise data that you need to work with to quickly solve problems. In Message Analyzer, the goal of data selection is to acquire the least amount of data necessary to resolve an issue, in order to minimize consumption of system resources, improve performance, and streamline the data analysis process.  
  
## Acquiring Input Data  
 Although Message Analyzer makes use of two distinct paths in which to acquire input data for a session, Data Retrieval Sessions use the first of the following paths only:  
  
-   **Loading saved data** — this path handles historical/saved data that is loaded into Message Analyzer through a Data Retrieval Session.  
  
-   **Capturing live data** — this path handles new data that is captured in a Live Trace Session.  
  
 For each of these data acquisition paths, Message Analyzer uses common aspects of the BSV model to provide a similar data selection and viewing experience in both types of sessions. A Data Retrieval Session and a Live Trace Session also share another common characteristic, which is that they both enable you to acquire input from multiple data sources. For example, you can retrieve historical data from one or more saved source files in a single Data Retrieval Session; or you can capture data simultaneously from the local computer and/or multiple remote computers in a single Live Trace Session that establishes a subsession for each computer on which Message Analyzer is capturing data. Message Analyzer also has the capability to run multiple Live Trace Sessions at the same time, where you can start up multiple sessions one after the other.  
  
 The Message Analyzer BSV model supports the following operations when acquiring input data:  
  
-   **Browse for data sources** — you can browse for and load data from one or more data sources, such as saved trace and log files.  See [Targeting Saved Data as an Input Source](targeting-saved-data-as-an-input-source.md) for more information.  
  
     The features of the BSV model not only facilitate loading data into Message Analyzer, but also enable you to select specific data that you want to load by using a **Session Filter** and/or a **Time Filter**, and also enable you to display data in several different viewer formats. You can also select an option that applies a pared-down parser set to input files that have truncated messages to improve performance and limit the types of messages retrieved. In addition, you can select configuration files that enable Message Analyzer to parse messages in text logs.  
  
-   **Capture message data** — you can capture new message data live by selecting one of the Message Analyzer default **Trace Scenarios**, as described in [Built-In Trace Scenarios](built-in-trace-scenarios.md). You can also select one or more system ETW Providers to create a unique provider configuration and resulting captured message set for a Live Trace Session; or you can select ETW Providers to add to the predefined configuration of a default **Trace Scenario** to enhance the scope of data capture. See [Capturing Message Data](capturing-message-data.md) for more information.  
  
     Moreover, the data selection aspect of the BSV model that extends to capturing data live enables you to choose specific data that you want your Live Trace Session to capture, for example, with the use of any of the following:  
  
    -   **Fast Filter**  
  
    -   **Keyword** bitmask filter  
  
    -   **Session Filter**  
  
    -   **EtherType** and **IP Protocol Number** filters in a remote **Trace Scenario**  
  
    -   **Parsing Level** filter  
  
 You can also view data from a Live Trace Session in the exact same presentation formats that you can apply to data that you load into Message Analyzer through a Data Retrieval Session.  
  
---  
  
 **More Information**   
 **To learn more** about applying filters to a Data Retrieval Session, see the following topic:  
[Selecting Data to Retrieve](selecting-data-to-retrieve.md)  
**To learn more** about applying filters that are common to either session type, see the following topics:   
[Filtering Message Data](filtering-message-data.md)  
[Setting the Session Parsing Level](setting-the-session-parsing-level.md)  
**To learn more** about applying filters in a Live Trace Session, see the following topics:  
[PEF-NDIS Fast Filters](pef-ndis-fast-filters.md)  
[PEF-WFP Layer Set Filters](pef-wfp-layer-set-filters.md)  
[WebProxy Filters](webproxy-filters.md)  
[Working with Session Filters in a Live Trace Session](working-with-session-filters-in-a-live-trace-session.md)  
[Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md)  
[Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md)  
[System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md)  
---