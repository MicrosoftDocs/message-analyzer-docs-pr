---
title: "Field Chooser Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c834c65f-2e37-4400-81f6-82f8653fc03f
caps.latest.revision: 35
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Field Chooser Tool Window

The **Field Chooser** **Tool Window** is a single-instance and dockable window that enables you to specify message types, field types, methods, properties, annotations, and other general fields to enhance the functionality of various Message Analyzer data viewers, for example, as described in [Expanding the Analysis Grid Viewer Column Layout](field-chooser-tool-window.md#BKMK_ExpandAGLayout). The **Field Chooser** is a common dialog that presents expandable hierarchical nodes that contain the properties, fields, methods, and other entities, for the protocol/module messages that Message Analyzer parses. Note that **Field Chooser** is not an interactive window since it does not drive message or data selection, nor is it driven by such selections.  
  
 **Displaying the Field Chooser**   
You can access the **Field Chooser** window from any of the following locations in Message Analyzer to open and dock the window in its default location, if it is not already displayed. If the **Field Chooser** window is already displayed, the following actions  will simply place focus on it:  
  
-   **Analysis Grid** group — when an **Analysis Grid** viewer session tab has focus, click the **Add Columns** button on the **Analysis Grid** viewer toolbar.  
  
-   **Grouping** group — when the **Grouping** viewer has focus, click the **Add Groupings** button on the **Grouping** viewer toolbar.  
  
-   **Windows** submenu — click the global Message Analyzer **Tools** menu, click the **Windows** item, and then select the **Field Chooser** item from the **Windows** submenu.  
  
-   **Column context menu** — right-click an **Analysis Grid** viewer column header and select the **Add Columns…** item that displays in the context menu that appears.  
  
 **Redocking the Field Chooser**   
After you display the **Field Chooser** window, you can undock and reposition it by taking advantage of the docking navigation control that displays after you drag the **Field Chooser** window away from its default docking location. You might do this to configure a location for this window that better suits your analysis process.  
  
 **Performing Tasks with the Field Chooser**   
You can use **Field Chooser** to locate message fields when performing the following tasks:  
  
-   Expanding the default column **Layout** of the **Analysis Grid** viewer by adding fields as new data columns, as described in [Expanding the Analysis Grid Viewer Column Layout](field-chooser-tool-window.md#BKMK_ExpandAGLayout).  
  
-   Adding new groups to the **Grouping** viewer by specifying the fields that you want to become the new Groups, as described in [Expanding the Grouping Viewer Configuration](field-chooser-tool-window.md#BKMK_ExpandGroupConfig).  
  
-   Adding configuration settings to various data viewers and tools by specifying fields for **Chart** viewer **Layouts**, **Pattern** expressions,  **Unions**, and so on, as described in [Locating Message Fields for Configuring Settings](field-chooser-tool-window.md#BKMK_LocateMessageFields).  
  
<a name="BKMK_ExpandAGLayout"></a>   
## Expanding the Analysis Grid Viewer Column Layout  
 The **Field Chooser** window enables you to configure new data columns for the **Analysis Grid** viewer to display values for the fields of specified protocols and modules. The default column **Layout** of the **Analysis Grid** viewer provides a starting point for data analysis; however, the default **Layout** offers a limited cross section of more robust data sets that are available to you through use of the **Field Chooser** window. For example, your data analysis process might be focused on a particular protocol for which the **Analysis Grid** viewer default column **Layout** displays only a subset of the greater superset of field information that you need to examine. With the **Field Chooser** window, you can add the columns you need to display the values of any data field you want to view, which includes message types, properties, structures, methods, flags, events, or other fields that a protocol of interest defines.  
  
 When you open the **Field Chooser** window, it displays a tree view of nodes that represent protocols and modules for which Message Analyzer provides parsing based on OPN descriptions, in addition to various annotations, properties, global fields, and any **Unions** that you have created. To access the fields of a particular protocol or module in the **Field Chooser** window, you can expand its top-level node and subnodes as required to expose the message hierarchy containing the message types, properties, structures, methods, flags, and events that the protocol defines.  
  
 **Adding and Removing Analysis Grid Data Columns**   
The specific data columns that you will add to the **Analysis Grid** viewer during data analysis generally depends on the troubleshooting context in which you are engaged. For example, prior to running a trace, you might have clients who complain about an unresponsive or slowly responding web server. After you run a trace that targets the server traffic and Message Analyzer displays the data, you might notice that the default column layout of the **Analysis Grid** viewer provides some initial indications in the **Summary** column about HTTP requests and responses. However, you might want to add HTTP **StatusCode**, **ReasonPhrase**, **HTTPContentType**, and **Method** columns, in addition to the **ResponseTime** Global Annotation as a column, so you can **Group** these columns to better organize and expose the information for analytical purposes.  
  
 To add a new data column to the **Analysis Grid** viewer and expose the data values for a field of any protocol or module that Message Analyzer parses, you will need to navigate through the appropriate message hierarchy in the **Field Chooser** window until you find the required field name/s. You can also search for a field by name by entering it in the search textbox, at which time search results are highlighted for any matches that are found. At this point, you can simply select the field you want to add as a column to the **Analysis Grid** viewer and then click the **Add** button on the **Field Chooser** tool bar. You can also right-click the field you want to add and select the **Add as Column** context menu item. Note that you will be unable to use the **Add as Column** command unless an **Analysis Grid** viewer tab has focus; otherwise, this command will be disabled.  
  
> [!TIP]
>  You can remove any data column from the **Analysis Grid** by right-clicking the column you want to delete and then selecting the **Remove** item from the context menu that appears. From this context menu, you can also select the following commands to perform related operations after adding new fields to the **Analysis Grid** viewer with **Field Chooser**:  
>   
>  -   **Save as Default User View Layout** — enables you to save any column **Layout** configuration as the user default **Layout**.  
> -   **Load Default User View Layout** — enables you to load the column **Layout** configuration that you saved as the user default **Layout**.  
> -   **Save Current View Layout As…** — enables you to save the current column **Layout** configuration with a unique **Name**, **Description**, and **Category** specification from the **Edit Item** dialog.  
  
 **Working with Array Fields**   
You might notice that some fields in **Field Chooser** are denoted as arrays **[]**, which require you to specify an array element or **Key** value in order to see the data in a new column that you are adding to the **Analysis Grid** or **Grouping** viewer. For example, if you wanted to look at the data for a **Uri.Query**, first expand the **Uri** node in the **HTTP** message hierarchy in **Field Chooser** then expand the **Query** node. Immediately under the **Query** node, you will see an array [] designator. If you right-click this designator and select **Add as Column**, the **Collection Key Selector** dialog displays to enable you to specify a **Key** such as "ocid" or some other string (you can correlate these in the **Details** **Tool Window** for the selected message). After you click **OK** to exit the dialog, the data for the **Key** you specified will display in the **Analysis Grid** under a new column entitled **Uri.Query["ocid"]** in this example.  
  
 A simpler method for doing this would be to locate the array value for which you want to display data in the **Details** **Tool Window**, right-click it, and select the **Add as Column** command. However, note that the formerly specified method is most useful when **Details** for a particular field are unavailable for a particular message. An example might be that you want to look at SACK options for TCP messages, but it is difficult to find any TCP messages that expose them such that you could right-click a field in **Details** and add a new column in the **Analysis Grid** viewer. When this is the case, you would need to be very familiar with TCP **Options** and values so that you could specify the required **Key** value/s in order to view the data.  
  
---  
  
 **More Information**   
 **To learn more** about these commands in addition to saving, sharing, and updating view **Layouts**, see [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md).   

---  
  
<a name="BKMK_ExpandGroupConfig"></a>   
## Expanding the Grouping Viewer Configuration  
 While the **Grouping** viewer has focus, you can expand the Group configuration by adding one or more fields to the current **Grouping** viewer **Layout**.  To do this, click the **Add Groupings** button on the **Grouping** viewer toolbar to cause the **Field Chooser** window to open in focus or to set the focus if it is already open, enabling you to locate fields of choice to add to the nested Group configuration of the **Grouping** viewer for an enhanced analytical perspective. For example, after you navigate to a protocol node of interest in **Field Chooser**, you can add a new Group to the **Grouping** viewer by selecting the **Add as Grouping** context menu item that displays when you right-click a particular field that you select under the current message hierarchy. With this capability, you can extract additional information into the Group configuration to expose data that might be difficult to locate in a large data set, while also enhancing the interactive analysis context with other data viewers, as described in the [Grouping Viewer](grouping-viewer.md) topic.  
  
<a name="BKMK_LocateMessageFields"></a>   
## Locating Message Fields for Configuring Settings  
 You can use the **Field Chooser** when you are creating new **Pattern** expressions, new **Chart** viewer **Layouts**, new **Grouping** viewer **Layouts**, and **Unions**. The **Field Chooser** window enables you to specify the fields of protocols and modules as configuration settings when modifying viewer or other entity configurations. To do so, you can navigate through message hierarchies to find fields of interest in the same way that you do when adding columns to the **Analysis Grid** viewer.  
  
 In this context, you can display the **Field Chooser** window when using the following features in the indicated ways:  
  
-   **Pattern** expression configuration — while an **Analysis Grid** viewer tab has the focus, right-click the corresponding session in the **Session Explorer** **Tool Window**, select **New Viewer**, and then select the **Pattern Match** item from the context menu that displays. After the **Pattern Match** viewer displays, open the **Pattern Editor** by clicking the **Create Pattern** button on the **Pattern Match** viewer toolbar. You can then display the **Field Chooser** window by clicking the **Insert Message** button in the lower section of the **Quick** tab in the **Pattern Editor**.  
  
     At this point, the **Field Chooser** window enables you to specify a message type for the **Pattern** expression configuration. Thereafter, the **Pattern Editor** enables you to again display the **Field Chooser**, which opens to the fields, properties, methods, and so on that are associated with the previously specified message type. You can do this by first clicking the **Insert Criteria** link on the **Quick** tab and then by clicking the ellipsis (**…**) control under the message configuration toolbar.  
  
-   **Chart** viewer **Layout** configuration — after you have the **Chart** viewer with a particular **Layout** displayed, you can then create a new **Chart** or customize the current one. To begin, click the **Edit** item in the **Chart** menu that displays when you select **Chart** in the global Message Analyzer **Session** menu. The **Edit Chart Layout** dialog then displays from where you can specify a **Chart** visualizer component that you want to use, for example, a **Bar** chart or a **Table** grid that you select in the **Chart type** drop-down. Thereafter, you can specify data fields and create formulas for the rows and/or columns of the **Chart** visualizer component.  
  
     You can display the **Field Chooser** to specify the data fields by clicking the ellipsis (...) in the **Series** pane of the **Edit Chart Layout** dialog. You will also need to display **Field Chooser** when configuring a data formula by clicking the ellipsis in the **Values** pane of the **Edit Chart** dialog, and once again in the **Formula Editor** that displays immediately thereafter. See  [Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md) for further details.  
  
-   **Grouping** viewer **Layout** configuration — while the **Grouping** viewer has focus, click the **Add Groupings** button on the **Grouping** viewer toolbar to display the **Field Chooser** window,  as described earlier in [Expanding the Grouping Viewer Configuration](field-chooser-tool-window.md#BKMK_ExpandGroupConfig).  
  
-   **Union** configuration — after you click the **New Union** button on the global Message Analyzer toolbar, the **Edit Union** dialog displays. When you click the **Add** button in this dialog for fields to include in the **Union**, the **Field Chooser** window displays to enable you to locate and select the fields you want in the **Union** configuration.  
  
## Understanding Other Field Chooser Categories  

 The **Field Chooser** window contains a number of nodes that are not directly associated with a protocol or module; however, you can use the entities contained in these nodes in any of the tasks described in this section, among many others. These nodes are located in the uppermost categories of **Field Chooser** window and consist of the following:  
  
-   **General** category — contains common entities that you can add as new columns in the **Analysis Grid** viewer, use in a  **Filter**,  configure in a **Pattern Expression**, and so on. You can also use **Global Annotations** and **Global Properties** in these tasks and many others. Some entities in the **General** category consist of **Type**, **DiagnosisLevels**, and **DataSource**.  
  
-   **Global Annotations** category —  additional information that is not directly related to a message, such as user-provided comments, implementation data, or other information related to the network stack. To retrieve this information, for example in a Filter Expression, you must use the number symbol  operator (“#”). For example, if you wanted to locate a message displayed in the **Analysis Grid** viewer, you could use a Filter that is similar to the following:  
    `#MessageNumber == 5`  
  
-   **Global Properties** category — contains a group of properties that Message Analyzer provides to enhance functionality. Some of the properties are inherent to existing message types, while others  were created specifically for Message Analyzer to expand the data that is available to you for analysis. For example, the property  **IsOperation** can identify whether a message node in the **Analysis Grid** viewer is an Operation. This can enable you to return Operation messages only with the use of a Filter Expression such as the following:  
    `*IsOperation == true`  
  
     Please be aware that you must use an asterisk (\*) to return the data of a **Global Property**.  
  
 Note that the **Global Annotations** and **Global Properties** entities appear in the **Details** **Tool Window** when you click the **Show all properties for the selected message** button on the **Details** window toolbar. However, these entities will display a value in **Details**, only if such values can be read or otherwise derived from the currently selected message.  
  
---  
  
 **More Information**   
 **To learn more** about using the **Field Chooser** with various Message Analyzer features, see the following topics:   
[Using the Field Chooser](using-the-field-chooser.md)  
[Accessing Message Properties and Annotations](using-the-filtering-language.md#BKMK_AccessPropertiesAnnotations)  
[Using the Pattern Editor](using-the-pattern-editor.md)  
[Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md)  
[Grouping Viewer](grouping-viewer.md)  
[Creating Unions](creating-unions.md)  

---