---
title: "Message Details Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c855b078-2ca1-455a-8bb2-a421f2d1ee87
caps.latest.revision: 57
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Message Details Tool Window

The message **Details** **Tool Window** is one of the primary windows that is driven by message selection in viewers such as the **Analysis Grid**, **Pattern Match**, **Gantt**, and others. For example, whenever you select a message row in the **Analysis Grid** viewer or in the **Matched Instances** section of the **Pattern Match** viewer, the grid configuration of the **Details** window below the **Analysis Grid** viewer is populated  with field names, values, types, and other data associated with the particular message that you selected. In addition, **Summary** information for the selected message displays in the tray of the **Details** window for convenience and improved visibility. You can also hover over the tray to display a tooltip with the **Summary** information, which is handy when the **Summary** line is long.  
  
<a name="BKMK_ViewMessageDetailsInline"></a>   
## Viewing Message Details Inline  
 You can also view message details inline by clicking the stacked-cube icons to the left of any **MessageNumber** designator in the **Analysis Grid** viewer. This can be useful if you want to compare two sets of details. For example, while the details of a selected message row display in the **Details** window, you can click the stacked-cube icon of any other message in the **Analysis Grid** viewer to display its details inline.  
  
> [!NOTE]
>  A *green* stacked-cube icon next to the **MessageNumber** designator in the **Analysis Grid** viewer represents a top-level message, while a *blue* stacked-cube icon represents an Operation, as defined in OPN, which typically represents a grouping of request and response message pairs.  
  
 When you click one of the stacked-cube icons, a drop-down displays that has up to four tabs, with each tab containing different information as follows:  
  
-   **Fields** — reproduces the grid configuration of field data that appears in the **Details** window below the **Analysis Grid** viewer, as later described.  
  
-   **Stack** — displays the origins tree that contains the protocol/module stack, with the messages and fragments that were part of a top-level message or operation. This tab makes it simple to quickly obtain a discrete view of the network layers for any selected top-level transaction.  
  
-   **Diagnosis** — displays parsing diagnostic information that includes a diagnosis **Type**, diagnosis **Level**, and a descriptive **Message** for any parsing errors that occurred in a set of trace results. Note that you can also find this information in the **Message Stack** **Tool Window**.  
  
-   **Embedded** — displays when a module definition reflects that a module is embedded; for example, SOAP headers are embedded.  
  
 The grid configuration for inline message details that are displayed in the **Fields** tab consist of the following columns of information:  
  
-   **Name** — describes the names of the fields contained in the message you selected in the **Analysis Grid** viewer.  
  
-   **Value** — specifies the value of each field name that is contained in the message you selected in the **Analysis Grid** viewer.  
  
> [!NOTE]
>  The inline **Details** now include a  Bit Field display for **Flag** fields. For example, if you expand the **Flags** field in a TCP message, you will see a visual representation of each flag value in an 8-bit field that appears in parentheses in the **Value** field, for example:  (. . .0. . . .) for ACK and (. . . . . .1.) for SYN. Note that the same visual representation appears in the **Details** **Tool Window**.  
  
-   **Type** — specifies the data type for the fields contained in the selected message.  
  
-   **Bit Offset** — specifies the offset value in bits for each data field, as measured from the beginning of message data to the beginning of a particular data field.  
  
-   **Bit Length** — specifies the value in bits for the length of each data field.  
  
> [!NOTE]
>  The *inline* message details do not interact with the **Message Data** **Tool Window**. Only if you select a particular field in the **Details** window will you see a corresponding hexadecimal value highlighted in the **Message Data** window.  
  
<a name="BKMK_UsingDetailsTracking"></a>   
## Using the Details Tool Window Features  
 For any message row that you select in the **Analysis Grid** viewer, in the **Grouping** viewer when in **Selection Mode**, in the **Matched Instances** section of the **Pattern Match** viewer, or in most other data viewers where you select messages, the message **Details** window displays the grid configuration of data fields that were parsed for that message. In some cases, message selection represents multiple messages. When this occurs, Message Analyzer shows the main details data for the in-focus message. If you previously selected a field in the **Details** window for a particular message type, Message Analyzer will reselect the same field whenever you select another message of the same type.  In addition, whenever a field in the **Details** window is selected, the hexadecimal value (**Bit Length**) of that field is highlighted in the **Message Data** window; the resulting display also provides an indication of the relative location (**Bit Offset**) of the field within the packet. As you manually select other data fields in the **Details** window, the hexadecimal value for each selected field is highlighted within the **Message Data** window. These features enable you to obtain a quick view of message details and hexadecimal data as you scroll through a message collection.  
  
 You can also filter any column of data in the **Details** window to isolate specific values by applying a **Column Filter**, similar to the way you do this in the **Analysis Grid** viewer, as described in [Filtering Column Data](filtering-column-data.md). To apply a **Column Filter**, you must click the **Show Column Filter Row** icon just below the **Details** window toolbar and then enter text in one of the columns to filter the data. Thereafter, only the fields that contain the text value that you specified in a particular column will display data. However, in some cases, a search result value for a field will display only if the tree containing the field is open. The column filtering feature provides a convenient way to group data based on field names, values, types, and so on.  
  
 **Using the Context Menu Commands**   
You can also create Filter Expressions, add **Analysis Grid** viewer columns, and perform **Group** operations based on data fields in the **Details** window. In addition, you can display the OPN definition for most data fields that you select. Commands for these operations and others are located on a context menu that displays when you right-click any row of field data in the **Details** window. These commands and the actions that result when you select them are described in the list that follows. In this list, the single-quoted *fieldname* values are placeholders for the actual field names that display in the **Name** column of the **Details** window:  
  
-   **Add ‘\<fieldName>’ to  Filter** — captures the name of the selected field within the associated message hierarchy, together with any value that applies, and constructs a Filter Expression that displays in a **Filter** panel text box on the Filtering Toolbar. This action does not apply the filter, as you must manually do that by clicking the **Apply** button, on a **Filter** panel of the Filtering Toolbar. This action filters the data displayed in any session viewer tab that has focus, for example, an **Analysis Grid** or **Gantt** viewer instance.  
  
-   **Add ‘\<fieldName>’ as Column** — captures the name of the selected field within the associated message hierarchy and adds a new named column to the current **Analysis Grid** viewer column layout, based on the selected field name. Message Analyzer populates that new data column with information that derives from the current message collection.  
  
> [!NOTE]
>  An **Analysis Grid** viewer session tab must have the active focus for this command to appear in the **Details** window context menu.  
  
-   **Add ‘\<fieldName>’ as Grouping** — captures the name of the selected field within the associated message hierarchy and performs a data grouping operation based on the selected field name.  
  
> [!NOTE]
>  When an **Analysis Grid** viewer session tab is in focus, this command creates a Grouped view of data based on the selected field name. If a Grouped view already exists in the **Analysis Grid** viewer, the new Group that you add will be configured at the lowest level of the nested group configuration. If the single-instance **Grouping** viewer has focus, this command causes a new Group to be added to the current **Grouping** viewer **Layout** at the lowest level of the nested group configuration.  
  
-   **Go To ‘\<fieldName>’ Definition** — captures the name of the selected field within the associated message hierarchy and causes Message Analyzer to display the **OPN Viewer**. The selected field is highlighted in yellow within the OPN definition code that displays.  
  
-   **Include Hex for Numerical Values** — when selected, this option displays hexadecimal values in parentheses next to the numerical values in the **Value** column of the **Details** window. Unselecting this option removes the hexadecimal values.  
  
-   **Display Binary Values as** — provides three options that determine the default format in which Message Analyzer displays binary values, for example, in the **Details** window and the **Analysis Grid** viewer. Options include **ASCII**, **Hex**, and **Decimal**.  
  
     You can set one of these as the default value in the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu; however, you can also override the default setting from the **Display Binary Values as** context menu. Message Analyzer installs with **ASCII** as the default setting, which can be useful in exposing additional information, for example, in **Payload** fields that otherwise display values as array elements only when the **Hex** or **Decimal** option is active.  
  
-   **Track ‘\<entityName>’** — enables you to track the value of a particular field or property in the **Details** window, depending on which of the following **Details** toolbar buttons is selected. Note that you can hover over the **Details** toolbar buttons with your mouse to display a tooltip that identifies them:  
  
    -   **Show all fields for the selected message** — displays all message field **Names** and **Values** in the **Details** window. From here, you can right-click any field and select the **Track ‘<entityName’** context menu command to cause Message Analyzer to track the field value across multiple message selections.  
  
    -   **Show all properties for the selected message**— displays all message property **Names** and **Values** in the **Details** window. From here, you can right-click any property and select the **Track ‘\<entityName’** context menu command to cause Message Analyzer to track the property value across multiple message selections. The properties that appear after you click the properties button on the **Details** window toolbar exist in two categories:  
  
        -   **Global** — this category contains annotations and properties that exist under the **Global Annotations** and **Global Properties** nodes in the **Field Chooser**  **Tool Window**. These properties apply to all messages.  
  
        -   **Message** — this category is named according to a selected message type, for example, SMB, TCP, HTTP, and so on. It contains properties that are specific to the currently selected message only.  
  
     Note that the **Global** properties are additional resources that you can use when creating filters, column configurations, and grouping configurations through the  context menu that displays when you right-click a property.  
  
     **Comparing Field Values**   
    Any fields and properties that you have set for tracking values appear in the **Details** window when you click the **Show tracked fields and properties for the selected message** button. You can set a field or property for tracking in the previously specified manner. Once Message Analyzer is tracking a field or property, click the **Details** toolbar button with the footprint icon to display the value/s. Thereafter, you can select different messages in the **Analysis Grid** viewer and observe how values vary across your trace results, for enhanced analysis.  
  
> [!TIP]
>  If you have the [Selection Tool Window](selection-tool-window.md) set for tracking messages, you can conveniently backtrack to previous message selections to view tracked field and property values.  
  
-   **Copy Selected Rows** — enables you to copy one or more selected rows of data in the **Details** window to the clipboard.  
  
-   **Copy ‘\<fieldname>’** — enables you to copy a specific field name to the clipboard.  
  
> [!TIP]
>  You can also use the keyboard shortcuts **Ctrl+C** and **Ctrl+Alt+C** to initiate the **Copy Selected Rows** and **Copy ‘\<fieldname>’** commands, respectively.  
  
## Using the Details Toolbar Functions  
 The toolbar in the upper part of the **Details** window has several functions that provide interactive capabilities, as follows:  
  
-   **Pin selection icon** — until this function is activated by clicking its icon, the **Details** window will snap to **Analysis Grid** viewer message selections. This is the default state, as indicated by the hover-over text that reads “**Selection changes are actively tracked**”. Otherwise, after clicking the pin selection icon, the current **Details** window is frozen to the values of the currently selected message, as indicated by the hover-over text “**Selection is pinned, selection changes are ignored**”. Also, the background of the pin selection icon turns to an amber color in the pinned state.  
  
     In the pinned state, additional message selection in the **Analysis Grid** viewer no longer drives the display of message field data in the **Details** window. This enables you to compare field values with other instances of the **Details 1** window for selected messages, for example, **Details 2**, **Details 3**, and so on.  
  
-   **Show all fields for the selected message** — click this icon to show all fields for a message that you selected.  
  
-   **Show all properties for the selected message** — click this icon to show all properties for a message that you selected.  
  
-   **Show tracked fields and properties for the selected message** — displays a list of fields and/or properties that you have set for tracking, as previously described.  
  
-   **Filter funnel icon** — after selecting a **Details** window field, click this icon to create simple view **Filter** code based on the selected field and place it in the Filter Expression text box on the default Filter panel of the Filtering toolbar.  Note that the filtering will apply to the in-focus viewer only, for example the **Grouping** viewer or the **Analysis Grid** viewer.  
  
-   **Add selected item to Analysis Grid column** — after selecting a **Details** window field, enables you to add a column to the **Analysis Grid** viewer to reflect the values of the selected field for the messages displayed in the grid. Applies to the **Analysis Grid** only, which must be in focus for this command to be enabled on the toolbar.  
  
-   **Add selected item as Grouping** — after selecting a **Details** window field or property, enables you to add a new Group to the current **Grouping** viewer **Layout** based on the selected field, providing that the **Grouping** viewer tab has the active focus. Otherwise, if an **Analysis Grid** viewer session tab is in focus, this command creates a grouped configuration of messages in the **Analysis Grid** viewer, based on the selected **Details** window field or property.  
  
-   **Search window** — enables you to search for information in the **Details** window based on a field or property name, value, or other text. Filters all data from display except data in the **Details** window grid that matches the search criteria.  
  
## Changing Analysis Perspectives with Details Operations  
 As described earlier, when a particular viewer is in focus, you can right-click any **Details** window field or property and select an appropriate context menu command (see [Using the Details Tool Window Features](message-details-tool-window.md#BKMK_UsingDetailsTracking)), to change your analysis perspective. You can also use corresponding toolbar buttons to achieve the same result in the following scenarios:  
  
 **Grouping Viewer in Focus**   
If this viewer is in focus, you can use the following context menu commands to achieve the indicated results, based on a selected field or property:  
  
-   **Add ‘\<fieldName>’ to Filter** — enables you to create and add simple view **Filter** code to the Filter Expression text box of the currently displayed **Filter** panel on the Filtering toolbar. You can then apply filtering to the messages that are displayed in the **Grouping** viewer. This is not only a quick way to create a filter, but a convenient method for applying a filter that targets specific data in a set of trace results, to produce a focused message set in a grouped configuration that can expose the cause of a problem.  
  
-   **Add ‘\<fieldName>’ as Grouping** — enables you to add a new Group to the **Grouping** viewer to enhance the grouped data configuration for better analysis capabilities.  
  
 **Analysis Grid Viewer in Focus**   
If this viewer is in focus, you can use the following context menu commands to achieve the indicated results, based on a selected field or property:  
  
-   **Add ‘\<fieldName>’ to  Filter** — enables you to create and add view **Filter** code to the Filter Expression text box on the default Filter panel of the Filtering toolbar. You can then apply filtering to messages that are displayed in the **Analysis Grid** viewer to achieve a focused set of messages that makes it easier to identify problems, by removing messages that do not pass the filtering criteria.  
  
-   **Add ‘\<fieldName>’ as Column** — enables you to add a new column to the **Analysis Grid** viewer to expose the data for a selected field or property across a set of trace results. You might then perform a **Group** command for the new data column to further enhance your analysis perspective.  
  
-   **Add ‘\<fieldName>’ as Grouping** — enables you to configure nested Group configurations in the **Analysis Grid** viewer to achieve an organized and hierarchical message display that exposes different but related data in the nested groups.  
  
## Displaying and Re-docking the Details Tool Window  

 If the **Details** window is no longer displaying in an Analysis Session, you can redisplay it by selecting the **Details** item from the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu. Note that you can also undock and reposition the **Details** window by taking advantage of the docking navigation control that displays after you drag the **Details** window by its tab away from its default docking location. You might do this to place the **Details** window adjacent to a particular **Tool Window** or data viewer with which you are working, to create an enhanced view of your data.  
  
## Analyzing Data with Multiple Details Tool Window Instances  

 The **Details** window provides a multi-instance capability that enables you to display up to a maximum of four numerically numbered windows of this type. This feature supports your data analysis process because it enables you to compare different message details data across multiple instances of this window type.  
  
 For example, selecting a message in the **Analysis Grid** viewer or **Message Stack** **Tool Window** can drive the display of details in the **Details 1** window, if it is currently open. Before selecting another related message of interest in the **Analysis Grid** viewer, you can pin or *freeze* the data in the **Details 1** window with the previously described pin selection icon and then open the **Details 2** window from the **Windows** submenu of the global **Tools** menu. You can then select another related message in the **Analysis Grid** viewer or **Message Stack** **Tool Window** and the message details of this newly selected message can display in the **Details 2** window. You can now easily compare data between the two **Details** window instances, given that the latter **Details 2** window displays immediately to the right of the former **Details 1** instance in this example. You can display up to four **Details** windows to compare the values of four messages that you select in the **Analysis Grid** viewer.  
  
 **Example Usage Scenario**   
As a usage example, consider that you have two traces, one from a computer that is performing well and another that is not. You might also have a common message that you sent to both, such as an SMB FileCreate message. In the case of the poorly performing computer, you notice that the FileCreate message seems to be the point where the traffic diverges into slower performance. You could pin the **Details** for this message and then compare them to the computer that is performing well. For example, you might notice that the server response message on the well performing computer has the OpLocks flag set while the poorly performing computer does not. This might mean that the server did not grant an opportunistic lock (OpLock) to the poorly performing computer, which in turn, could result in poor performance.  
  
## See Also  

[Filtering Live Trace Session Results](filtering-live-trace-session-results.md)   
[Writing Filter Expressions](writing-filter-expressions.md)   
[Using the Field Chooser](using-the-field-chooser.md)   
[Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md)   
[Message Data Tool Window](message-data-tool-window.md)