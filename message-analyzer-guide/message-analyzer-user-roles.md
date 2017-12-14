---
title: "Message Analyzer User Roles | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: a839fa26-afeb-4a7f-b4cc-6a42ef2fc560
caps.latest.revision: 20
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Message Analyzer User Roles
The Message Analyzer user audience primarily consists of network administrators,  support analysts, and developers. However, other personnel who support this audience often use Message Analyzer in a limited capacity that is restricted to the task of taking traces and forwarding the data to others for analysis. The list that follows briefly describes  the types of tasks that typical Message Analyzer users perform.  
  
-   **Network Administrator** — uses  Message Analyzer as a network troubleshooting and analysis tool.  
  
-   **Network Support Analyst** — uses  Message Analyzer in  Help Desk scenarios to capture data for clients or to aggregate log and trace data from multiple sources and different time zones for analysis.  
  
-   **Protocol Developer** — generates  network protocol code and uses Message Analyzer as a  validator of protocol  behavior, architecture, message field values, and state.  
  
-   **Event Tracing Developer** — instruments applications with ETW technology and uses Message Analyzer to capture the events from ETW providers.  
  
-   **Tracer** — typically a client who is experiencing issues in some area and is requested to take a trace for in-depth analysis by a Network Administrator or Support Analyst.  
  
 The diverse audience described above can be represented  in two high-level categories of User Roles, basic and advanced, as described immediately below. The list that follows briefly summarizes each high-level User Role and provides pointers to the appropriate topics in this Operating Guide for each User Role to get started with Message Analyzer. The information in this list should help you determine the User Role that best fits your use of Message Analyzer.  
  
-   **Basic User Role** — if you are a **Tracer** and you intend to use Message Analyzer only to take traces, save them to file, and then pass them along to colleagues, administrators, or support personnel for analysis, proceed to the following topics to get started quickly with these tasks.  
  
    -   [Quick Session Startup](quick-session-startup.md) — describes all the options for starting a trace session. For example, you can start a Live Trace Session immediately with no session configuration required, by clicking the **Start Local Trace** button on the Message Analyzer **Start Page** to capture messages on the local computer at the Link Layer.  
  
         You can also start a Data Retrieval Session to import saved data into Message Analyzer, with no session configuration required, by clicking the **Open** button on the Message Analyzer **Start Page** and then navigating to saved files for selection.  
  
    -   [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md) — optionally, create a basic data display environment by choosing one of the simple built-in **Window Layouts** that organizes data viewers and **Tool Windows** into a preset configuration.  
  
    -   [Performing a Live Capture](performing-a-live-capture.md) — provides a summary of two methods that you can use to start  a Live Trace Session quickly, which includes using the **Start Local Trace** and **Favorites** features.  
  
    -   [Performing Data Retrieval](performing-data-retrieval.md) — describes additional options for retrieving input data for Message Analyzer, including loading data from text logs.  
  
    -   [Procedures: Quick Start](procedures-quick-start.md) — provides several examples of simple procedures that you can perform to see Message Analyzer in action, although some minor configuration is required in these scenarios.  
  
    -   [Saving Session Data](saving-session-data.md) — describes how to save Message Analyzer trace data, how session results are saved, and also specifies the default save location.  
  
-   **Advanced User Role** — if you are a **Network Administrator**, **Network Support Analyst**, or a **Developer**, and you intend to use Message Analyzer to create custom trace configurations, run live  traces, retrieve saved logs and trace file data, and perform analysis, review the following topics to get started quickly with these tasks.  
  
    -   [Quick Session Startup](quick-session-startup.md) — review this topic to familiarize yourself with various methods for starting a Message Analyzer session quickly.  
  
    -   [New Features and Updates](new-features-and-updates.md) — review this topic to obtain an overview of the new and updated features that exist in the current release of Message Analyzer, so that you can leverage them in your work.  
  
    -   [Starting a Message Analyzer Session](starting-a-message-analyzer-session.md) — review this topic to obtain the following:  
  
        -   An overview of the configuration options that are available when you are creating a Live Trace Session or Data Retrieval Session.  
  
        -   An overview of the workflow for creating new Message Analyzer sessions that capture live data or retrieve  saved data.  
  
        -   Links to topics that provide in-depth details about capturing and retrieving message data, configuring session scenarios, editing existing sessions, and running procedures that provide examples of how to use the network tracing and data retrieval features. Topics of particular interest might be the following:  
  
            -   [Targeting Live Data as an Input Source](targeting-live-data-as-an-input-source.md)  
  
            -   [Configuring a Live Trace Session](configuring-a-live-trace-session.md)  
  
            -   [Performing a Live Capture](performing-a-live-capture.md)  
  
            -   [Targeting Saved Data as an Input Source](targeting-saved-data-as-an-input-source.md)  
  
            -   [Configuring a Data Retrieval Session](configuring-a-data-retrieval-session.md)  
  
            -   [Performing Data Retrieval](performing-data-retrieval.md)  
  
    -   [Viewing Message Data](viewing-message-data.md) — review this topic to learn about a wide assortment of data viewing options that are available for live or saved data, including built-in data viewers, **Chart** viewer **Layouts**, **Tool Windows**, **Window Layouts**, **Profiles**, and other data manipulation tools. Also run procedures that provide examples of how to use data viewers and **Tool Windows**, and how to apply **Filters**, **Viewpoints**, and data **Grouping**. Topics of particular interest might be the following:  
  
        -   [Data Viewers](data-viewers.md)  
  
        -   [Using the Filtering Toolbar](using-the-filtering-toolbar.md)  
  
        -   [Tool Windows](tool-windows.md)  
  
        -   [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)  
  
    -   [Analyzing Message Data](analyzing-message-data.md) — review this topic for an overview of Message Analyzer analysis capabilities. Given that viewing message data and analyzing message data are closely related, this topic will give you a better idea of how to use the Message Analyzer viewing features as analysis tools.  
  
    -   [Saving Session Data](saving-session-data.md) — as described earlier.  
  
> [!NOTE]
>  If your tasks fall into the **Advanced User Role** category, you are also encouraged to review the [Message Analyzer Tutorial](message-analyzer-tutorial.md) to obtain a broad understanding of Message Analyzer features and functions.