---
title: "New Features and Updates | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bef77e31-470f-4d24-82da-239541094e50
caps.latest.revision: 37
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# New Features and Updates

This section provides a brief description of the ongoing new and updated features that are introduced in each release of Microsoft Message Analyzer.

## New in Message Analyzer Version 1.4

 The new and updated features that are provided in the Microsoft Message Analyzer version 1.4 release, first made available in March 2016 as a [public download](http://www.microsoft.com/en-us/download/details.aspx?id=44226), are described in this section.

- **Filtering Toolbar** — consists of  a new Filtering Toolbar that consolidates the major filtering functions of Message Analyzer into a common user interface (UI) that is accessible to all data viewers, including the **Grouping** viewer. Integrates the following filtering capabilities into the new toolbar:

  - View Filters

  - Time Filters

  - Viewpoints, including Disable Operations

  - Viewpoint Filters

  - Flat Message List (simulates the Network Monitor view)

  For more details about these feature, see the [Using the Filtering Toolbar](using-the-filtering-toolbar.md) section.

- **Window Layouts** — organizes data viewers and **Tool Windows** into preset configurations for customizing your working analysis environment, with window layouts that range from simple to increasingly more complex configurations.

     For more details about this feature, see the [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md) topic.

- **Profiles** — enables you to utilize a set of built-in **Profiles** that contain specific data viewer and **Layout** presets that trigger whenever you are loading data from specific types of supported input files. Also enables you to create your own custom **Profiles**.

     For more details about this feature, see the [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md) topic.

- **Data Source Filter** dialog — originally part of the **Quick Filter** feature that was replaced by the **Time Filter** feature, which is now located on the Filtering toolbar that is accessible to every in-focus session viewer. You can display the **Data Source Filter** dialog by clicking the **Data Source Filter** item in the global Message Analyzer **Session** menu.

     For more details about this feature, see the [Filtering Data Sources](filtering-data-sources.md) topic.

- **Chart configuration improvements** — provides a new UI for creating **Chart** viewer **Layouts** that simplifies configuration and editing. Also streamlines the use of visualizer components by limiting them to one per **Layout**.

     For more details about this feature, see the [Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md) topic.

- **Trace Session configuration improvements** — provides a new UI for adding system ETW Providers when configuring a  Live Trace Session, along with a **Name** and **Guid** search capability that helps you find providers of interest. Also provided is the capability to specify GUIDs for custom providers that you can add to the **Available ETW Providers** list in the **New Session** dialog, while automatically registering them with the operating system. Also relocates access to ETW session configuration on the **ETW Providers** toolbar in the **New Session** dialog.

     For more details about these features, see [Adding a System ETW Provider](adding-a-system-etw-provider.md).

- **WPP setup simplified** — provides a simplified UI configuration in Message Analyzer **Options** to specify input TMF and PDB symbol files for parsing and viewing WPP-generated events.

     For more details about these features, see [Loading WPP-Generated Events](loading-wpp-generated-events.md).

- **OMS support** — provides a new input data source that imports data from logs in an Operations Management Suite (OMS) Workspace for analysis.

     For more details about these features, see [Loading OMS Log Data](loading-oms-log-data.md).

- **Pattern Match viewer improvements** — enables saving all **Pattern Match** messages as **Bookmarks**.

     For more details about this feature, see the [Viewing Matched Instance Message Data](using-the-pattern-match-viewer.md#BKMK_ViewMatchedInstanceData) and [Bookmarks Tool Window](bookmarks-tool-window.md) topics.

- **Saving data in binary format** — enables saving trace data in binary format from the **Message Data** **Tool Window** by using the **Save Selected Bytes As** command.

     For more details about this feature, see the [Message Data Tool Window](message-data-tool-window.md) topic.

- **Decoding URLs** — removes the special encoding characters in URLs and displays results in the **Decoded Value** section of the **Field Data** **Tool Window**.

     For more details about this feature, see the [Decoding URLs](field-data-tool-window.md#BKMK_DecodingURLs) topic.

- **Message time correlation improvements** — similar to **Time Offset** in Microsoft Network Monitor, a new **DeltaFromFirst** global property is provided for the **Analysis Grid** viewer to indicate the sequential running time of each message.

     For more details about this feature, see the **Tip** in the [Default View Layout](analysis-grid-viewer.md#BKMK_DefaultViewLayout) topic.

- **Display enhancements for data fields** — provides a new 8-bit field display for Flag type fields.

     For more details about this feature, see the [Viewing Message Details Inline](message-details-tool-window.md#BKMK_ViewMessageDetailsInline) topic.

- **OPN viewer performance enhancements** — provides a more light-weight and better performing viewer for displaying OPN definitions.

     For more details about this feature, see the [Viewing OPN Source Code](viewing-opn-source-code.md) topic.

- **Bookmarking improvements** — adds the capability to add bookmark messages to an existing **Bookmark**.

     For more details about this feature, see [Adding Bookmarks to an Existing Bookmark or Group](bookmarks-tool-window.md#BKMK_AddBookMarksToExisting).

- **IP Address resolution** — Message Analyzer now  resolves IP addresses to host names in the **Analysis Grid** viewer, in traces where this information exists.

     See the [Analysis Grid Viewer](analysis-grid-viewer.md) topic for more information.

- **Promiscuous Mode selection enhancement** — provides simple selection of adapters that support P-Mode in the **Advanced Settings - Windows-NDIS-Packet-Capture** dialog, during Live Trace Session configuration, to enable capturing message data in Promiscuous Mode.

     For more details about this feature, see [Capturing Data in P-Mode](microsoft-windows-ndis-packetcapture-provider.md#BKMK_CaptureInPMode).

- **Enhancement to Pattern Expression configuration** — now supports timestamp calculations when creating new **Pattern Expressions** with the **Pattern Match Editor**.

     For more information about creating Pattern Expressions, see [Using the Pattern Editor](using-the-pattern-editor.md).

- **Drag and Drop changes** — provides the capability to drag and drop multiple data files into Message Analyzer and aggregate all data into a single default data viewer.

     For more details about this feature, see [Performing Data Retrieval](performing-data-retrieval.md).

- **Process Name detection improvement** — enables display of process name data natively in Message Analyzer for any ETW provider.

     For more details about this feature, see [Viewing Process Name Data](viewing-process-name-data.md).

- **Assets** — provides additional assets that includes more **Layouts** for the **Analysis Grid** viewer, **Grouping** viewer, and **Chart** viewer. Also includes a simplified process for  **Chart** viewer **Layout** configuration.

For more details about these features, see the following topics:

---

[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)  

[Understanding the Built-In Grouping View Layouts](grouping-viewer.md#BKMK_UsingPredefinedLayouts)  

[Chart Viewer Layouts](chart-viewer-layouts.md)  

[Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md)  

---