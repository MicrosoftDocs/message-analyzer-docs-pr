---
title: "Using the Field Chooser | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: def815f4-9ea6-4379-8b6c-a35c232a3f23
caps.latest.revision: 46
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Using the Field Chooser
The Message Analyzer **Analysis Grid** viewer has a default view **Layout** that contains several columns in which basic message data is displayed; however, the default layout displays only a limited cross-section of the available data. Additional information is also available for many other message fields that you can access by using the **Field Chooser** **Tool Window**. By adding specific columns, you can expose hidden but important field information that you can examine for greater troubleshooting capabilities with Message Analyzer.  
  
> [!NOTE]
>  The column configuration for the default **Analysis Grid**  view **Layout** is described in the [Analysis Grid Viewer](analysis-grid-viewer.md) topic. Also, you can find all the individual columns that are contained in the default layout of the **Analysis Grid** viewer in the **Field Chooser** by using its search facility.  
  
## Accessing the Field Chooser  
 Although the column configuration of the default **Analysis Grid** view **Layout** provides some basic information for any message that you view, there are many more data columns that you can add to the **Analysis Grid** viewer that enable you to focus on specific data fields that contain values for the message types, properties, structures, methods, flags, events, metadata, and so on, of your captured messages. Each of the nodes in the message hierarchies of the **Field Chooser** window use common icons to represent fields, methods, properties, and so on. You can access the **Field Chooser** from the **Analysis Grid** viewer in any of the following ways:  
  
-   Click the **Add Columns** icon on the **Analysis Grid** viewer toolbar. This action opens and docks the **Field Chooser** window in its default location. If the **Field Chooser** is already displayed when you click the **Add Columns** icon, then **Field Chooser** simply becomes the active window.  
  
-   Click the **Add Columns** command from the **Analysis Grid** submenu in the Message Analyzer global **Session** menu, when the **Analysis Grid** has focus.  
  
-   Right-click any **Analysis Grid** column label and then select the **Add Columns…** command in the context menu that appears, which likewise opens and docks the **Field Chooser**, if it is not already open. If **Field Chooser** is already open, the previously indicated action occurs.  
  
> [!NOTE]
>  You can also access the **Field Chooser** from other locations, by doing any of the following:  
  
-   Click the **Add Groupings** icon on the **Grouping** viewer toolbar.  
  
-   Select the **Field Chooser** item from the **Windows** submenu, which is accessible from the Message Analyzer global **Tools** menu.  
  
-   Click the **Field** ellipsis (**…**) in the **Series Fields** pane of the **Edit Chart Layout** dialog or click the **Value** ellipsis in the **Values** pane of the **Edit Chart Layout** dialog, which is accessible by clicking the **Edit** command from the **Chart** drop-down list in the global Message Analyzer **Session** menu whenever a **Chart** has focus.  
  
-   Click the **Add** button in the **Edit Union** dialog when you are creating a new **Union** (click the **New Union** button on the Message Analyzer global toolbar; this command is also accessible from the Message Analyzer global **Tools** menu).  
  
-   Click the **Insert Message** button on the **Quick** tab of the **Pattern Editor** dialog, which displays when you click the **Create Pattern** button in the **Pattern Match** viewer. You can also display **Field Chooser** by clicking any ellipsis in the **Criteria** section of the **Quick** tab (click **Insert Criteria**), after you launch the **Pattern Editor** by selecting the **Create Pattern** command from the context menu that displays when you right-click any message in the **Analysis Grid** viewer.  
  
## Adding Data Columns to the Analysis Grid with Field Chooser  
 The **Field Chooser** window contains a top-level tree view of all the message modules and protocols for which Message Analyzer provides parsing based on OPN descriptions. If you expand the nodes of any particular module, you will see the message hierarchy containing the message types, properties, structures, methods, flags, events, or other data fields that are defined for that module or protocol. If you want to view the data for other fields that are relevant to the trace data you captured, you can add a data column for specified fields to the **Analysis Grid** viewer column layout by locating the appropriate module or protocol and the required field names in the **Field Chooser** window, and then doing any of the following while the **Analysis Grid** viewer is in focus:  
  
-   Double-click the field name.  
  
-   Select the field or other entity that you want to add as a column and then click the **Add** icon in the upper-left corner of the **Field Chooser** window.  
  
-   Right-click a field name and select the **Add as Column** item in the context menu.  
  
    > [!TIP]
    >  You can also select the **Go to Definition** item in this context menu to open the OPN viewer and highlight the definition of the field you chose.  
  
 For example, if you wanted to view the ID of processes for which Message Analyzer captured events, you could add  **ProcessId** as a column — found under the **Etw** node or under the **Global Properties** node in the **Field Chooser** — to the **Analysis Grid** viewer. Note that you also have the capability to display a **ProcessName** column from **Global Properties** as well. You are advised that viewing process ID and process names works best when you are displaying data from a *.etl file.  
  
## Adding Groups to the Grouping Viewer with Field Chooser  
 You can also use the **Field Chooser** window to add one or more new Groups to one of the default Grouping **Layouts**, or you can do this when you are creating your own Grouping **Layout**. To add a new Group, you will need to locate one or more fields for a particular message type that you want to add to your **Layout** as a Group. When you locate a field, right-click it and then select the **Add as Grouping** command from the context menu that appears. Note that to add the selected field as a Group, the **Grouping** viewer must be in focus. Otherwise, if the **Analysis Grid** viewer is in focus, selecting the **Add as Grouping** command reorganizes the **Analysis Grid** message display into groups that each contain a set of identical values, where such values are aggregated from all messages that contain those particular values for the field that you added with the **Add as Grouping** command.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about adding new Groups to the **Grouping** viewer, see the [Grouping Viewer](grouping-viewer.md) topic.  
**To learn more** about creating groups to enhance your analysis perspectives with the **Analysis Grid** viewer, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).   
___________________\_  
  
## Searching for Fields  
 If you want to search for a particular field by name, you can type the name, or a portion thereof, in the search text box at the top of the **Field Chooser** window and search results will display with yellow highlighting, similar to the way Windows Explorer displays search results. After you locate the correct field, you can then add it as a data column to the **Analysis Grid** viewer or as a Group in the **Grouping** viewer, in the previously specified manner. If there is data associated with any field you chose, it will automatically display after you add the field as a new column in the **Analysis Grid** viewer, or as a Group in the **Grouping** viewer.  
  
> [!NOTE]
>  You can remove any **Analysis Grid** column by right-clicking the column label and selecting the **Remove** command in the context menu that displays. You can remove a Group in the **Grouping** viewer by clicking the **x** in the Group label below the **Grouping** viewer toolbar.  
  
> [!TIP]
>  Because the **Field Chooser**  window provides a tree-level view of the message hierarchy for each module type that is parsed by the PEF Runtime, it can help you understand how to traverse the message hierarchy to some extent. However, Message Analyzer also provides the Filter IntelliSense service that helps you to discover how to traverse the message hierarchy in a more interactive way; this feature streamlines the task of writing Filter Expressions. Filter IntelliSense is an interactive and intelligent statement completion service that responds to text that you enter in any Filter Expression text box by displaying various elements of the message hierarchies, such as message types, structures, properties, flags, and other fields. The message hierarchies that you traverse with Filter IntelliSense are the same that display in **Field Chooser** window.  
>   
>  Note that you can invoke Filter IntelliSense when configuring Filter Expressions in the **Session Filter** text box in the **New Session** dialog, or in the **Filter** and **Viewpoint Filter** text boxes on the Filtering toolbar that is located just below any session viewer tab.  
  
## Adding Analysis Grid Columns from the Details Tool Window  
 In addition to using the **Field Chooser** window to add more data columns to the current column configuration of the **Analysis Grid** viewer, you can also quickly add a new data column to the **Analysis Grid** viewer based on field names in the **Details** **Tool Window**, which displays beneath the **Analysis Grid** viewer by default. To do this, right-click any row of field data in the **Details** window and select the **Add 'fieldName' as Column** menu item, where *fieldName* is a placeholder for the actual field, property, or other name in the **Name** column of the **Details** window. Message Analyzer then automatically populates the new named column with values based on parsed data from the currently displayed message collection.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the **Field Chooser**, see the [Field Chooser Tool Window](field-chooser-tool-window.md) topic.  
**To learn more** about Filter IntelliSense, see the [Filter IntelliSense Service](filter-intellisense-service.md).  
**To learn more** about Filter Expressions, see [Writing Filter Expressions](writing-filter-expressions.md).  
**To learn more** about the **Grouping** viewer, see the [Grouping Viewer](grouping-viewer.md) topic.   
___________________\_  
  
## See Also  
 [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)