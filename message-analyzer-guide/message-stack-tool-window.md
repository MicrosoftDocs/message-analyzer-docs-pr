---
title: "Message Stack Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24b3de7a-b818-4069-af5c-a0f6d2c6554e
caps.latest.revision: 28
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Message Stack Tool Window
The **Message Stack** **Tool Window** is an interactive, message-specific, and dockable window where the display of details is driven by message selection in a viewer such as the **Analysis Grid**, **Grouping**, or other viewer. The result is an independent display of the full stack for any message selected in a particular viewer. This enables you to quickly observe and explore the network architecture of any message, without having to manually open different parts of the stack (origins messages) in the **Analysis Grid** viewer. The **Message Stack** window contains a toolbar that provides different buttons for changing the format of the message stack view, as follows:  
  
-   **Visual stack** — the default view which provides data that is organized into a simple visual stack display along with summary information.  
  
-   **Table** — provides a table with data in three columns consisting of the top-level **Message** number, **Module** name, and a **Summary** description for the selected message.  
  
-   **Tree with field information** — provides similar data with a different organization of summary information.  
  
-   **Origins** — the toolbar in the **Message Stack** window also provides a label that indicates the **Origins** count, which is a measure of the number of origins trees under a top-level message node.  
  
     For example, there are typically two origins trees under an operation, one that represents a request stack and one that represents the response stack. Under other top-level messages, there is typically one origins tree. However, if there are message fragments, the **Origins** count can be higher.  
  
## Analyzing Stack Data  
 The **Message Stack** window can act as a central hub from where you can quickly correlate additional message details and contexts. This capability enables you to enhance your data analysis perspectives because you can do the following:  
  
-   Drive the data displayed in the **Details** **Tool Window**. For example, by selecting a network/message node in the **Message Stack** window, the **Details** window is automatically populated with the field data of the selected message.  
  
-   Drive selection of top-level messages in the **Analysis Grid** viewer, which can show the context of the surrounding message configuration in the **Analysis Grid** viewer.  
  
-   Drive message selection in the **Analysis Grid** viewer of any origins message under a top-level parent message node, providing that the origins tree is in the expanded state for the particular top-level message. Otherwise, no messages will be highlighted when you select any origins message in the **Message Stack** window.  
  
-   Compare **Message Stack** information for one message in the **Analysis Grid** viewer with the message stack of a second message in the **Analysis Grid**, by clicking the cubed icon of the second message and comparing the data on the **Stack** tab of the inline message details in the **Analysis Grid** viewer with the data displaying in the **Message Stack** window.  
  
## Using the Message Stack Window Interactive Features  
 After you select a top-level message row in the **Analysis Grid** viewer, the entire message stack for the selected message displays in the **Message Stack** window. If you expand all the message nodes underneath the top-level message in the **Analysis Grid** viewer and then select any of its child messages (origins tree messages), the **Message Stack** window highlights those child messages within the stack in light blue. Likewise, if you select any message in the **Message Stack** window, the corresponding message rows in the **Analysis Grid** viewer are automatically highlighted, provided that the nodes for those messages are in the expanded state in the **Analysis Grid** viewer; otherwise, no messages will be highlighted. The selection in the **Message Stack** window also displays field data in the **Details** window grid for the selected node in the stack, even if the node of the associated top-level message in the **Analysis Grid** viewer is unexpanded.  
  
## Using the Message Stack Window Context Menu Commands  
 The **Message Stack** window has several context menu commands that display only when you right-click a message row in the Table view. These commands and the actions they invoke are described as follows:  
  
-   **Show Toolbar** — alternately displays and hides the **Message Stack** window toolbar.  
  
-   **Copy Selected Rows** — enables you to copy the data for one or more selected message rows in the **Message Stack** window. You can also use the keyboard shortcut `Ctrl+C` to execute this command.  
  
-   **Copy ‘\<columnName>’** — enables you to copy the data in any column that you right-click in the **Message Stack** window. You can also use the keyboard shortcut `Ctrl+Alt+C` to execute this command.  
  
## Displaying the Message Stack Tool Window  
 If the **Message Stack** window is no longer displaying in an Analysis Session, you can redisplay it by selecting the **Message Stack** item in the **Windows** submenu, which is accessible from the global Message Analyzer **Tools** menu. You can also undock and reposition the **Message Stack** window by taking advantage of the docking navigation control that displays after you drag the **Message Stack** window by its tab away from its default docking location. You might do this to move the **Message Stack** window adjacent to another viewer or **Tool Window** with which you are working, to enhance your data analysis perspective.  
  
## Analyzing Data with Multiple Message Stack Tool Window Instances  
 The **Message Stack** window provides a multi-instance capability that enables you to display up to a maximum of four windows of this type. This feature supports your data analysis process because it enables you to compare the top-level and origins data of different messages across multiple instances of this window type.  
  
 For example, selecting a message in the **Analysis Grid** viewer drives the selection of the corresponding message in the **Message Stack 1** window, if it is currently open. Before selecting another related message of interest in the **Analysis Grid** viewer, you can pin or *freeze* the data in the **Message Stack 1** window and then open the **Message Stack 2** window from the **Windows** submenu in the global **Tools** menu. You can then select another related message in the **Analysis Grid** viewer and the newly selected message is automatically selected in **Message Stack 2** window. You can now easily compare data between the two **Message Stack** window instances.