---
title: "Data Viewer Concepts | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 93560740-b3c7-4198-b722-4bd19f757176
caps.latest.revision: 28
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Data Viewer Concepts
Message Analyzer provides a  set of default and preview data viewers that enable you to display session results in different viewing formats, whether you are working with a Data Retrieval Session or a Live Trace Session, as described in [Starting a Message Analyzer Session](starting-a-message-analyzer-session.md). The ability to do so is made possible by the Message Analyzer data viewing infrastructure. The viewing infrastructure enables you to specify the data viewers that provide the unique analysis perspectives that are most advantageous for streamlining your data assessment tasks.  
  
## Data Viewing Infrastructure  
 The Message Analyzer data viewing infrastructure makes use of various data viewers and various types of  **Tool Windows** that are either message-specific, session-specific, or provide annotation capabilities. Many data viewers, including the **Analysis Grid** and **Gannt** viewer, are known as *multi-instance* viewers. Multi-instance viewers provide the capability to display message data in multiple instances of the same viewer type. Message-specific windows are typically driven by multi-instance viewers. They reflect data based on the selected messages or fields of an in-focus, multi-instance data viewer. Because message-specific windows can have only a single instance in display, they are considered *single-instance* windows. Multi-instance viewers typically interact with single-instance windows to provide additional data details and presentation enhancements.  
  
 For example, by selecting a row of message data in the **Analysis Grid** viewer, the message-specific **Details** and **Message Data** single-instance **Tool Windows** display message field data and hexadecimal field values, respectively, for the selected message. A session-specific window such as **Diagnostics** is driven by session selection. For example, if you have multiple Live Trace Session and Data Retrieval Session viewer tabs displayed, the **Diagnostics** window displays the associated diagnosis summary information for the particular session that corresponds to the viewer tab that you select.  
  
> [!NOTE]
>  The Message Analyzer viewing infrastructure also enables interaction between some **Tool Windows**. For example, selection of message fields in the single-instance **Details** **Tool Window** drives interaction with the single-instance **Message Data** and **Field Data** **Tool Windows**.  
  
## Data Presentation Configurations  
 The Message Analyzer viewing infrastructure represents message data in several presentation configurations, as follows:  
  
-   **Tree grid** format — provides a familiar grid view for displaying, filtering, grouping, and analyzing trace or log data, as shown in the [Analysis Grid Viewer](analysis-grid-viewer.md) topic.  
  
-   **Graphic visualizers** — consists of several types of graphic displays, as follows:  
  
    -   **Chart** viewer layouts — provides graphic data visualizers that are contained in **Layouts** for the **Chart** viewer, which includes built-in and user-configurable **Layouts** that employ **Bar** element, **Pie** slice, **Table** grid, and **Timeline** graphic visualizer components. A  built-in **Layout** for the **Chart** viewer that contains a **Bar** element visualizer component is shown in the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.  
  
    -   **Gantt** viewer format — this viewer provides an at-a-glance graphic view of message dispersion across a trace timeline that is presented as color-coded protocol module identifiers, with source/destination address message pairs shown in the y-axis and timestamps in the x-axis. You can see an example of the **Gantt** viewer data visualizer in the [Gantt Viewer](gantt-viewer.md) topic.  
  
    -   **Interaction** viewer formats — this viewer contains **Swimlane**, **Mapping**, **Diagram**, and **Chord** viewing formats in which you can view IP conversations between end points in a set of trace results. The **Interaction** viewer is shown with the **Swimlane** configuration in the [Interaction Viewer](interaction-viewer.md) topic.  
  
    -   **Message Summary Tiles** format — this viewer uses data tiles to provide a high-level overview of major trace statistics, data summaries, and other important values for any set of trace results. The **Message Summary Tiles** viewer is shown in the [Message Summary Tiles Viewer](message-summary-tiles-viewer.md) topic.  
  
    -   **Message Summary List** format — this viewer uses three data lists to summarize **Module**, **Endpoint**, and **Diagnostic** message count to provide basic information at-a-glance for a set of trace results. The **Message Summary Tiles** viewer is shown in the [Message Summary Lists Viewer](message-summary-lists-viewer.md) topic.  
  
-   **Other viewing formats** — other unique viewing formats consist of the following:  
  
    -   **Grouping** viewer format — organizes traffic into summary hierarchies based on **Grouping** viewer **Layouts** that contain predefined message field Groups in nested configurations. Enables  you to expose data at top-level that can  normally be difficult to find. The **Grouping** viewer with the **ProcessName and Conversations** view **Layout** is shown in the [Grouping Viewer](grouping-viewer.md) topic.  
  
    -   **Pattern Match** viewer format — organizes data into several results panes that display after you execute a built-in Pattern expression that locates a particular message pattern for which the Pattern expression is configured. To see an example of results from executing the **TCP Three-Way Handshake Pattern** expression, see the [Pattern Match Viewer](pattern-match-viewer.md) topic.  
  
-   **Tool data** — provided by message-specific and session-specific **Tool Windows** that serve as analysis tools by working interactively with a data viewer that is in-focus. Tool data provides additional message details and data presentation perspectives that are relative to data selection from an in-focus viewer. Some common **Tool Windows**  are shown together with the **Analysis Grid** viewer in the [Tool Windows](tool-windows.md) topic.  
  
## Data Viewing Infrastructure Implementation  
 The most common Message Analyzer viewing infrastructure components with which you will typically work the most  are described in this section. They display in the main analysis surface where all data viewers  appear and includes the **Analysis Grid** viewer, **Tool Windows**, and **Chart** viewer **Layouts**, among others. In Message Analyzer, these viewing components are interactive and integrated such that message selection in one viewing component drives the display of related data such as low-level details or high-level message summaries in one or more other viewing components, providing that  integrated components are currently displayed.  The following types of message data are implemented in these viewing components:  
  
-   **Message detail summaries** — displayed in the tree grid format of the **Analysis Grid** viewer, as described in the [Analysis Grid Viewer](analysis-grid-viewer.md) topic. This format contains session results data that is presented as expandable message nodes in a stacked configuration. Each parent node in the stacked configuration represents an Operation or top-level transaction, while child nodes represent the underlying modules (protocols or providers) that supported such Operations or transactions, including reassembled message fragments that arrived at varying times. In this documentation, these child nodes are also referred to as the *message origins* or the *origins tree*.  
  
-   **Message field and value details** — displayed in tabular format and reflect the names, values, types, bit offsets, and bit lengths of the fields of most messages that are selected in the **Analysis Grid** viewer. This information is contained in the message-specific and dockable **Details** **Tool Window** that displays by default beneath one or more session viewer tabs, as described in the [Message Details Tool Window](message-details-tool-window.md) topic.  
  
-   **Message field hexadecimal values** — displayed in a message-specific, configurable, and dockable **Message Data** **Tool Window** that shows the hexadecimal values of fields selected in the **Details** **Tool Window** or messages selected in the **Analysis Grid** viewer. See the [Message Data Tool Window](message-data-tool-window.md) topic for further details.  
  
-   **Message diagnostics data** — displayed in the session-specific and dockable **Diagnostics** **Tool Window** that enables quick location of embedded diagnosis message types, summarizes message group counts, and synchronizes diagnosis message selection with their parent messages in various data viewers of a selected session, as described in the [Diagnostics Tool Window](diagnostics-tool-window.md) topic. Note that diagnostic data also displays in the default  **DiagnosisTypes** column in the  **Analysis Grid** viewer.  
  
-   **Message layer data** — displayed in a message-specific and dockable **Message Stack** **Tool Window** that displays the full stack in several viewing formats for any message selected in the **Analysis Grid** viewer, as described in the [Message Stack Tool Window](message-stack-tool-window.md) topic. Enables quick exploration of the network architecture for a selected message without manually expanding message nodes in the **Analysis Grid** viewer.  
  
-   **Message top-level summary data** — displayed in built-in **Layouts** for the **Chart** viewer, for example, the [HTTP Content Type Volumes](http-content-type-volumes.md) layout, or in custom, user-designed **Layouts**. The **Layouts** consist of graphical and statistical summary visualizer components that can provide a high-level overview of network traffic, focus on lower-level message details, or display other message activity that occurs across a set of trace results, as described in the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.  
  
     **Layouts** for the **Chart** viewer condense and encapsulate large volumes of data into visual-graphic presentation formats that are easy to understand at a glance, enabling you to bypass the examination of thousands of messages to obtain a similar level of assessment. This helps to simplify the analysis of data trends, patterns, structures, relationships, and failures, so that you can more efficiently solve messaging problems.  
  
     Note that you can modify the configuration of any built-in **Layout** for the **Chart** viewer and that you can save it under a different name as a new user Library item that you can share with others, as described in [Managing User Libraries](managing-user-libraries.md).  
  
> [!NOTE]
>  Message Analyzer data viewers are available from the locations described in [Session Data Viewer Options](session-data-viewer-options.md).  
  
---  
  
 **More Information**   
 **To learn more** about the multi-instance data viewers, see the [Data Viewers](data-viewers.md) topic.  
**To learn more** about the message-specific and session-specific **Tool Windows**, see the [Tool Windows](tool-windows.md) topic.  
**To learn more** about creating and managing your own **Layouts** that contain data visualizer components for the **Chart** viewer, see [Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md).  
---