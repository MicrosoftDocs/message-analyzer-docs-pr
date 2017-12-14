---
title: "Selection Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f017d67f-0fb3-4c96-86e0-bd61a157e878
caps.latest.revision: 23
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Selection Tool Window
The **Selection** **Tool Window** is an interactive and dockable window that enables you to readily expose message selection in several Message Analyzer data viewers, which is especially advantageous in cases where message selection could be ambiguous. For example, in a data viewer such as the **Gantt** chart, message selection is not as obvious as other viewers such as the **Analysis Grid** or **Interaction** chart. The **Selection** window makes your selection more obvious because it exposes message selection in its window as a table of information that appears separate from the viewers in which you make selections. Integral to this capability and equally as important is the ability of the **Selection** window to maintain the context of multiple message selection in the following ways:  
  
-   Within a specific viewer, such as the **Analysis Grid**.  
  
-   Across multiple viewers or multiple instances of the same viewer type, in the same session.  
  
-   Across multiple viewers in different sessions.  
  
 The **Selection** window provides a separate space that independently monitors and displays the selection of messages in multiple viewers and keeps track of such selections, so that you can thereafter back- and forward-navigate among messages as necessary, while maintaining the context of previously selected messages. This enables you to undo any message selection that you made accidentally, without affecting other messages that you selected. The **Selection** window also provides various **Column Layouts** that can expose different message fields. All of these features enable you to improve message correlation and analysis capabilities.  
  
## Modes of Operation  
 The **Selection** window provides the following modes of operation that diversify the scope of message selection:  
  
-   **Single viewer selection mode** — this mode is the default state in which the **Selection** window initially displays. In this mode, both the **Activate Session Viewer** and **Navigate Across Sessions** buttons are disabled, as indicated by a subtle blue background color that displays when you hover over them with your mouse. The name of each button also displays in a popup when you hover over them. In this mode, you can only navigate among previously selected messages in the currently active data viewer. For example, as you select multiple messages in a single data viewer such as the **Analysis Grid**, the **Selection** window builds a collection of the selected messages. Thereafter, you can use the **Go back** and **Go forward** arrow-buttons on the **Selection** window toolbar to navigate through the messages that you selected in the *currently active data viewer* only.  
  
-   **Activate session viewers selection mode** — this mode is enabled by clicking the **Activate Session Viewer** button on the toolbar of the **Selection** window. When this mode is active, the **Activate Session Viewer** button displays with an amber background color. In this mode, the **Selection** window tracks all messages that you select in a single session by building an associated message collection, where the data is displayed in one or more data viewers — for example, one or more **Analysis Grid** and **Gantt** viewer instances in the same session. After you select a number of messages, you can use the **Go back** and **Go forward** arrow-buttons on the **Selection** window toolbar to navigate through the message collection that is displayed in *current session viewers only*. To disable this mode, click **Activate Session Viewer** button again to remove the amber background color.  
  
     As a usage example for this mode, you might have multiple book marked messages that you have selected in the **Bookmarks** **Tool Window**, where such selection in turn drives message selection in the **Analysis Grid** viewer. Furthermore, because the **Selection** window interacts with the **Analysis Grid**, it responds to messages that are selected in the grid—and also to the manner in which they are selected, as in single or multiple message selection—by adding those messages to the **Selection** window. While reviewing a group of book marked and selected messages in the **Analysis Grid** viewer that are distributed throughout a trace, you can lose the multiple selection context in the grid if you select any single message in the group for further inspection. With the **Selection** window, you can select individual messages without resetting the selection context in the **Analysis Grid** viewer. Moreover, as you select messages in the **Selection** window, it drives message selection in the **Analysis Grid** viewer by placing the selection arrow to the left of each selected message; however, the original multiple message selection context in the grid is not lost as you do this.  
  
-   **Navigate across session viewers selection mode** — this mode is enabled by clicking both the **Navigate Across Sessions** and the **Activate Session Viewer** buttons on the toolbar of the **Selection** window. When this mode is active, both of these buttons display with an amber background color. In this mode, the **Selection** window tracks all messages that you select in multiple sessions by building an associated message selection collection, where the data is displayed in one or more viewers in each session. After you select a number of messages in different viewers from different sessions, you can use the **Go back** and **Go forward** arrow-buttons on the **Selection** window toolbar to navigate through the message collection that spans across *all session viewers* in which you selected messages. To disable this mode, click these same buttons again to remove the amber background color.  
  
## Example Use Cases  
 As a simple usage example when navigating across sessions, you might have multiple log files or other saved traces that contain related data in separate **Analysis Grid** viewer session tabs that you need to analyze. You can then use the **Go To Message** function on the **Analysis Grid** toolbar to jump to specific messages in each session tab that you know have related data. Each time you jump to a message, it is displayed in the **Selection** window, which in turn keeps track of all your selections, as described earlier. You can then use the **Go back** and **Go forward** arrow-buttons on the toolbar of the **Selection** window to navigate back and forth between the messages with related data for a comparative analysis. For each selected message that you navigate to, you can view the associated data in the **Message Stack**, **Details**, and **Message Data**  **Tool Windows** to correlate the details you need to analyze. To further facilitate this scenario, you can drag the **Selection** window tab away from its default docking location in the lower right corner of the Message Analyzer UI so you can more easily expose the **Message Data** window in its default docking location.  
  
 Another usage example that applies to any mode is if you click a message in the **Analysis Grid** viewer, possibly to bring it into focus, and you inadvertently undo a previous selection that is important to the analysis in which you are engaged. With the **Go back** or **Go forward** feature, you can resume navigation among previous message selections, regardless of whether the context of the previous message selection was lost.  
  
## Changing Column Layouts in the Selection Tool Window  
 The **Selection** window also provides a **Default** column layout that has some similarities with the default column layout of the **Analysis Grid** viewer. However, you can change the column layout within the **Selection** window for analysis purposes. To do this, right-click anywhere within the **Selection** window to display the **Column Layout** context menu, which contains all the column layouts that are available from the **Layout** drop-down list on the **Analysis Grid** toolbar; an **Example View Layout** is also provided. By selecting a layout item from the **Column Layout** submenu, the specified layout replaces the current column configuration of the **Selection** window.  
  
 This feature enables you to conveniently maintain the context of the current **Analysis Grid** column **Layout**, while simultaneously and independently displaying a different layout in the **Selection** window that is tailored for a more detailed and on-the-spot analysis of specifically selected messages. For example, you could select a TCP message in the **Analysis Grid** viewer and display it in the **Selection** window. Thereafter, you can right-click the message in the **Selection** window and select the **TCP** item from the **Column Layout** context menu to display fields that are important for TCP analysis, such as the following:  
  
-   **DiagnosisTypes**  
  
-   **Timestamp**  
  
-   **TimeDelta**  
  
-   **Source address**  
  
-   **Destination address**  
  
-   **SourcePort**  
  
-   **DestinationPort**  
  
-   **PayloadLength**  
  
-   **SequenceNumber**  
  
-   **AcknowledgementNumber**  
  
-   **Window**  
  
-   **Summary**  
  
> [!TIP]
>  If you want to create your own view **Layouts** that you can select from the **Selection** window **Column Layout** menu, you will need to create a new **Layout** in the **Analysis Grid** viewer and save it from the **Layout** drop-down list on the **Analysis Grid** toolbar. For more information, see [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md).  
  
## Displaying and Re-docking the Selection Tool Window  
 If the **Selection** window is not already displayed, you can display it by clicking the **Selection** item in the **Windows** submenu, which is accessible from the global Message Analyzer **Tools** menu. Note that you can redock the **Selection** window by using the docking navigator control that displays after you undock the window from its default location. Undock the **Selection** window by dragging it by its tab away from the default location.  
  
 You can use this feature to facilitate a convenient location for your analysis processes. For example, you might undock this window from its default location and reposition it alongside another **Tool Window** or data viewer, or you can allow the window to float in a chosen location outside the Message Analyzer user interface. This is also possible for any other **Tool Window** or data viewer.