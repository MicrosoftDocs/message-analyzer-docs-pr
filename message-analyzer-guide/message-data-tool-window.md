---
title: "Message Data Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a872dbe-615a-4bfa-a25c-a5baf33adeb2
caps.latest.revision: 43
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Message Data Tool Window

The **Analysis Grid** viewer works in tandem with the message **Details**, **Message Data**, and **Field Data** **Tool Windows**. If you select any message row in the **Analysis Grid** viewer, message data can be displayed in the following ways:  
  
-   The hexadecimal value of a message field may be highlighted in the **Message Data** window.  
  
-   The name of a message field may be selected in the **Details** window grid; the grid also contains the value, type, bit offset, and bit length of each field in a message.  
  
-   The decimal or parenthetical hexadecimal value of any selected message field in **Details** can display in the **Field Data** window.  
  
## Tool Window Interaction  

 If you select a particular field in the **Details** window, Message Analyzer highlights the hexadecimal value of that field in the **Message Data** window. The **Details** window also works interactively with **Field Data** window. For example, if you select a field in the **Details** window, the **Field Data** tab displays the decimal and hexadecimal values of the selected field. These capabilities enable you to quickly assess the value of any field contained in any message.  
  
## Using the Controls and Commands  

 The **Message Data** window is accessible as a selectable tab below the **Analysis Grid** viewer, as is the **Field Data** window. The **Message Data** window has several right-click context menu commands that provide options for copying, displaying, and saving hexadecimal, ASCII, and binary data, as described below.  
  
-   **Copy** — enables you to copy several forms of data in the **Message Data** window, as follows:  
  
    -   **Hex** — a command that enables you to copy any selected Hex value in the **Message Data** window.  
  
    -   **ASCII** — a command that enables you to copy the ASCII values of selected hexadecimal values in the **Message Data** window.  
  
    -   **Hex & ASCII** — a command that enables you to copy ASCII and hexadecimal values for a selected block of hexadecimal values in the **Message Data** window.  
  
-   **Save Selected Bytes As...** — enables you to save selected trace data in binary format (\*.bin), whether the Message Data window is configured to display data in Hex, ASCII, or Binary format. This feature can work together with the **Select All** command in this context menu so that you can save all the data in binary.  
  
-   **Display Options** — allows you to display any combination of hexadecimal, ASCII, and binary values in the **Message Data** window, as follows. Note that one value is always selected:  
  
    -   **Hex** — selection and slider controls that enable you to display hexadecimal data values of a message or message field in variable font sizes.  
  
    -   **ASCII** — selection and slider controls that enable you to display ASCII data values of a message or message field in variable font sizes.  
  
    -   **Binary** — selection and slider controls that enable you to display binary data values of a message or message field in variable font sizes.  
  
    -   **Column** — a drop-down control that enables you to specify the column width of the **Message Data** window in terms of the number of bytes displayed. The default setting is 16 bytes.  
  
-   **Select All** — click this command to highlight all the data displayed in the **Message Data** window. This feature is designed to work with the **Save Selected Bytes As...** command to save all selected data in binary format.  
  
> [!NOTE]
>  The **Field Data** window also has several right-click menu commands that are described in the [Field Data Tool Window](field-data-tool-window.md) topic.  
  
 The **Message Data** window has several labels in the tray area of the window that display the following information:  
  
-   **Byte Count** — provides an indication of the number of bytes of data that are currently selected.  
  
-   **Message Offset** — indicates how far the starting point of field data or a highlighted block of hexadecimal values is offset, in bytes, from the beginning of a message.  
  
-   **Protocol Offset** — indicates how far the starting point of field data or a highlighted block of hexadecimal values is offset, in bytes, from the beginning of a protocol message, which starts at the point where the stripped header (un-highlighted values) of a previous lower layer ends.  
  
## Viewing Field and Message Data  

 You can view the fields and values of any top-level parent message node that you select in the **Analysis Grid** viewer, and you can also view the fields and values of any selected child message node that is part of the origins tree under its parent node. To expose this data, expand the parent message node and each child message node in succession to display the underlying stack layers that make up the origins tree. For example, you might have a TCP message as a parent node in a **Local Network Interfaces** trace, with subsequent child nodes for the **IPv4**, **Ethernet**, **NdisProvider**, and **Etw** messages that make up the origins tree. If you select a message row in the **Analysis Grid** viewer for any one of these messages and you have not yet selected a field in the **Details** window, all the data contained in the selected message is highlighted in the **Message Data** window. Moreover, if you select a particular field of the message in the **Details** window, Message Analyzer highlights the hexadecimal value of the field in the **Message Data** window. At the same time, the value of the field displays in the **Field Data** window.  
  
 You can also examine the headers and payloads of any particular message layer and you can even observe how the process of de-encapsulation is represented, as you upwardly traverse the message stack. For instance, using the previously indicated TCP example, perform the following steps to visualize how de-encapsulation took place:  
  
#### To visualize message layer de-encapsulation  
  
1. Perform a **Local Network Interfaces** trace and let Message Analyzer run long enough to capture some top-level TCP messages.  
  
2. Expand a parent TCP operation node and then expand the message nodes in the origins tree to expose the message stack.  
  
3. Select the **Etw** node in the **Analysis Grid** viewer and then select the **Payload** field in the **Details** window.  
  
    The hexadecimal values for the **Payload** field are highlighted in the **Message Data** window.  
  
4. Select the **NdisProvider** node in the **Analysis Grid** viewer and then select the **FrameData** field in the **Details** window.  
  
    The hexadecimal values for the **FrameData** field are highlighted in the **Message Data** window.  
  
5. Select the **Ethernet** node and then select the **MacClientData** field in the **Details** window.  
  
    The hexadecimal values for the **MacClientData** field are highlighted in the **Message Data** window.  
  
6. Select the **IPv4** node and then select the **Payload** field in the **Details** window.  
  
    The hexadecimal values for the **Payload** field are highlighted in the **Message Data** window.  
  
7. Select the **TCP** node and then select the **Payload** field in the **Details** window.  
  
    Only the TCP header data (the IPv4 payload) remains, with no hexadecimal data highlighted, while the **Payload** field is selected. To see this more clearly, go back and select the **Etw** message in the **Analysis Grid** viewer, and then in succession, select the **NdisProvider**, **Ethernet**, **IPv4**, and **TCP** messages. As you do, you can observe the header data being stripped out at each layer, which reflects the PEF Runtime decoding process that de-encapsulates captured messages, as illustrated in the figure that follows.  
  
   ![Message Analyzer Layer De&#45;encapsulation example](media/fig66-message-analyzer-layer-de-encapsulation-example.gif "Fig66-Message Analyzer Layer De-encapsulation example")  
  
   **Figure 66:  Message Analyzer Layer De-encapsulation example**  
  
## Displaying the Message Data Tool Window  

 If the **Message Data** window is no longer displaying in an Analysis Session, you can redisplay it by selecting the **Message Data** item from the **Windows** submenu, which is accessible from the global Message Analyzer **Tools** menu. You can also undock and reposition the **Message Data** window by taking advantage of the docking navigation control that displays after you drag the **Message Data** window away from its default docking location by its tab. You might do this to move the **Message Data** window adjacent to another **Tool Window** or data viewer with which you are working, to enhance your data analysis perspectives.  
  
## Analyzing Data with Multiple Message Data Tool Window Instances  

 The **Message Data** window provides a multi-instance capability that enables you to display up to a maximum of four numerically numbered windows of this type. This feature supports your data analysis process because it enables you to compare the hexadecimal data of different messages across multiple instances of this window type.  
  
 For example, selecting a message in the **Message Stack 1** window, **Analysis Grid** viewer, **Grouping** viewer, or other data viewer, can drive the display of hexadecimal values in the **Message Data 1** window, if it is currently open. Before selecting another related message of interest in a particular viewer, you can pin or *freeze* the data in the **Message Data 1** window by clicking the pinning icon on its toolbar and then open the **Message Data 2** window from the **Windows** submenu that is accessible from the global **Tools** menu. You can then select another related message in a particular viewer. Thereafter, the hexadecimal values of any message that is automatically selected in the **Message Stack** window or of any field that is automatically selected in the **Details** window are displayed in the **Message Data 2** window. You can now easily compare data between the two **Message Data** window instances. You can display up to four **Message Data** windows to compare the values of four messages that you select in a particular viewer.  
  
## See Also  

[Message Details Tool Window](message-details-tool-window.md)