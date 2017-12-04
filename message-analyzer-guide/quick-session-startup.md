---
title: "Quick Session Startup | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f1e720a-6481-4c11-bf20-88145ffe0186
caps.latest.revision: 21
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Quick Session Startup
If you have not yet started Message Analyzer, see [Starting Message Analyzer for the First Time](../messageanalyzer_content/installing-and-upgrading-message-analyzer.md#BKMK_StartingMAFirstTime). After you start Message Analyzer, the first user interface that displays is the **Start Page**. This page is designed to enable you to acquire input data very quickly, for example, through a Data Retrieval Session or a Live Trace Session.  
  
> [!IMPORTANT]
>  To start a Live Trace Session immediately with a single action and no further configuration, click the **Start Local Trace** button on the **Start Page**, as shown in the figure below, to begin capturing live traffic at the Link Layer with the **Local Network Interfaces Trace Scenario**. Note that you should be running Message Analyzer as an Administrator for this scenario to function properly.  
  
 Other methods for quick access to input data are described in [Performing a Live Capture](../messageanalyzer_content/performing-a-live-capture.md).  
  
## Start Page Organization For Quick Access to Input Data  
 The **Start Page** is organized into an upper row of action buttons that provide fast access to input message data, and below that are recent files and scenario lists that likewise also provide quick access to input data. Input message data consists of message traffic that you capture live or saved data that you import into Message Analyzer. The **Start Page** facilitates the acquisition of this input data by enabling you to get started very quickly with a Live Trace Session or a Data Retrieval Session, where you capture network traffic live or load data from saved files or logs into Message Analyzer, respectively. The Message Analyzer **Start Page** is shown in the following figure:  
  
 ![Message Analyzer Start Page](../messageanalyzer_content/media/fig01-message-analyzer-start-page.png "Fig01-Message Analyzer Start Page")  
  
 **Figure 1:  Message Analyzer Start Page**  
  
 The following provides  details about the **Start Page** features that enable quick access to input data:  
  
-   **New Session** button — contained in the upper row of action buttons. Click this control to start the [configuration phase](../messageanalyzer_content/configuring-a-live-trace-session.md) of a Live Trace Session or Data Retrieval Session, by displaying the **New Session** dialog. This dialog contains configuration screens that enable you to quickly access the settings and components that you want to specify for a live trace or data import, for example, a predefined **Trace Scenario**, ETW Provider, Filters, a session viewer, target host/s, saved traces or logs, and so on.  
  
     **For additional information** about Message Analyzer sessions, see [Starting a Message Analyzer Session](../messageanalyzer_content/starting-a-message-analyzer-session.md).  
  
-   **Start Local Trace** button — contained in the upper row of action buttons. Click this control to immediately start a local Link Layer trace while using the **NDIS-PacketCapture** provider with no additional configuration required, although you need to run Message Analyzer with the **Run as administrator** startup option in this case. This trace captures network traffic with either the **Microsoft-PEF-NDIS-PacketCapture** provider or the **Microsoft-Windows-NDIS-PacketCapture** provider, depending on which operating system your computer is running, as described in [Built-In Trace Scenarios](../messageanalyzer_content/built-in-trace-scenarios.md). When you use this feature to capture live data, Message Analyzer automatically creates a Live Trace Session and displays the results in the **Analysis Grid** viewer or in the viewer that is set as the default in the **Default Profile** pane on the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu.  
  
     **For additional details**, see [Performing a Live Capture](../messageanalyzer_content/performing-a-live-capture.md).  
  
-   **Open** button — contained in the upper row of action buttons. Click this control to load data into Message Analyzer from saved trace or log files that are supported by Message Analyzer, as described in [Locating Supported Input Data File Types](../messageanalyzer_content/locating-supported-input-data-file-types.md). When you click the **Open** button on the **Start Page**, the Windows **Open** dialog displays, from where you can navigate to a saved trace or log file. By default, this dialog opens to the `Documents\MessageAnalyzer\Traces\` folder on your computer; however, if you change the location for storing your files, the **Open** dialog will persist that location.  
  
     After you select one or more files containing the data you want to load, Message Analyzer automatically creates a Data Retrieval Session configuration in the **New Session** dialog, which lists the files you selected. At this point, prior to starting the Data Retrieval Session, you have the option to configure a **Time Filter**, **Session Filter**, and/or a **Parsing Level**, and you can also select a data viewer of choice. Note that when you load data into Message Analyzer through the **Open** feature, the resulting message set will be chronologically ordered in the **Analysis Grid** viewer (assuming this is the data viewer you are using).  
  
     **For related information**, see [Performing Data Retrieval](../messageanalyzer_content/performing-data-retrieval.md).  
  
-   **Recent Files** list — contains a list of trace and log files that you recently saved or accessed from Message Analyzer. This list displays a maximum of 10 files and enables you to very quickly resume work from a previous Analysis Session. When you click a trace or log file in the list, Message Analyzer immediately loads the data and displays it in the default data viewer, such as the **Analysis Grid**. In addition, Message Analyzer automatically creates a Data Retrieval Session that you can edit later on by clicking the **Edit Session** button on the global Message Analyzer toolbar. You might do this to alter the data display by specifying a **Time Filter**, **Session Filter**, or **Parsing Level**.  
  
-   **Favorite Scenarios** list — contains a list of **Trace Scenarios** that are set to Favorite status. By default, the list contains the predefined **Local Network Interfaces**, **Loopback and Unencrypted IPSEC**, and **Pre-Encryption for HTTPS**  scenarios. When you click one of the **Trace Scenarios** in this list, Message Analyzer automatically starts a local Live Trace Session with no additional configuration required, at which point Message Analyzer begins to capture data in accordance with the scenario's built-in design. After stopping the session, you have the option to edit it as previously described.  
  
     Note that you can add other predefined **Trace Scenarios** or custom scenarios of your own to the **Favorite Scenarios** list, by clicking the **Edit Favorites** link above the list. This action displays the **Edit Favorites** dialog that enables you to set a new Favorite or undo an existing one. To configure a Favorite, click the white-colored star to the left of the scenario in the **Edit Favorites** dialog, at which time the star changes to the color yellow and the scenario is added to the **Favorite Scenarios** list on the **Start Page** and to the **Favorites** category of the **Message Analyzer Trace Scenarios** asset collection. To undo a Favorite, simply click the yellow star to remove the scenario from the **Favorite Scenarios** list and the **Favorites** category of the asset collection.  
  
    > [!NOTE]
    >  The **Message Analyzer Trace Scenarios** asset collection also appears in the **Select Scenario** drop-down list on the **Live Trace** tab of the **New Session** dialog. You can also set Favorites from this location.  
  
     ___________________\_  
  
     **More Information**   
     **To learn more** about the built-in **Trace Scenarios** provided with Message Analyzer, see the [Built-In Trace Scenarios](../messageanalyzer_content/built-in-trace-scenarios.md) topic.  
    ___________________\_