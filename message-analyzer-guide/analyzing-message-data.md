---
title: "Analyzing Message Data | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b159b33b-983e-4e60-974e-fe114c5f721b
caps.latest.revision: 33
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Analyzing Message Data
Message Analyzer tools that are available for analyzing the results of a Live Trace Session or a Data Retrieval Session include data viewers, tool windows, and other features and functions that manipulate, locate, or otherwise interact with message data. These analysis tools are briefly summarized in this section.  
  
 **Using the Session Analysis Tools**   
Message Analyzer provides many tools that you can use to achieve unique perspectives on your data set during an Analysis Session. The fundamental tool upon which all further analysis usually proceeds is the data viewer. By default, Message Analyzer provides the **Message Analyzer Chart View Layouts** asset collection Library that contains a diverse collection of built-in **Layouts** for the **Chart** viewer that you can select in any Analysis Session. These **Layouts** enable you to display data in diverse formats to expose analysis perspectives that can accelerate problem solving. Other tools that can manipulate or interact with the primary data display known as the **Analysis Grid** viewer include view **Filters**, **Viewpoints**, **Grouping**, column **Layouts**, **Aliases**, **Color Rules**, various **Tool Windows** such as **Details**, and so on.  
  
 A brief summary of the tools that you can use to perform data analysis tasks include the following:  
  
-   **Analysis Grid** viewer — the **Analysis Grid** is the primary analysis surface that presents message data in a tree grid format with rows of expandable message nodes in a stacked configuration. This common data viewer is usually the starting point for most Analysis Sessions, as it enables you to review a core set of data for any trace, which includes default column data and message summaries. In addition, selection of messages in the **Analysis Grid** viewer interactively drives the display of related details that appear in the **Message Stack**, message **Details**,   **Message Data**, and **Field** value windows. The **Analysis Grid** viewer also provides access to various data manipulation features from a right-click context menu, such as **Filters**, **Pattern Expressions**, and **Time Shifts**, in addition to numerous toolbar functions.  
  
---  
  
     **More Information**   
     **To learn more** about the **Analysis Grid**, see the [Analysis Grid Viewer](analysis-grid-viewer.md) topic.   

---  
  
-   **Chart** viewer **Layouts** — enable you to display data in different graphical formats, such as **Bar** element, **Pie** chart, **Table** grid, or **Timeline** graph, to create unique analysis perspectives. The **Layouts** for the **Chart** viewer include graphic visualizer components that can provide high-level data summaries or low-level data that is focused on specific message types and values. These include **Layouts** such as the **IP/Ethernet Conversations by Message Count**, **Average Response Times for Operations**, **SMB Top Commands**, and so on, in addition to any custom **Layouts** that you create. All of the built-in **Layouts** for the **Chart** viewer are designed to provide a unique focus on your data in order to expose different values and details through graphic visualizer components, which can be critical when you need to expedite the data analysis process.  
  
---  
  
     **More Information**   
     **To learn more** about the built-in **Layouts** for the **Chart** viewer, see the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.   

---  
  
-   **Grouping** viewer — enables you to organize the traffic from a set of trace results into summary hierarchies that are based on built-in or user-customized **Grouping** viewer **Layouts**, which contain nested Groups that are defined by various fields, properties, annotations, methods, and so on. You can alter the nesting configuration of the Groups for different analysis perspectives and you can correlate message selection and filtering on an interactive basis with the **Analysis Grid** viewer.  
  
     For example, selection of groups in the **Grouping** viewer interactively drives the display of messages in other viewers of the same session, which enables you to create  analysis contexts that focus on specific groups of messages in different presentation formats. With the **Grouping** viewer, you can drill down into the data of lower-level Groups in the nested group configuration to isolate and expose discrete information based on the type of Group selected. The **Grouping** viewer is a primary analysis tool that can help you quickly achieve the following:  
  
    -   Organize data into unique hierarchies to expose targeted information from large data sets.  
  
    -   Identify Groups that reflect the highest traffic volumes.  
  
    -   Isolate all messages in a set of trace results to a specific top-level Group and drill down for data in nested Groups, to obtain a concise analytical focus at each Group level.  
  
    -   Correlate messages in the **Analysis Grid** and other viewers with the Groups in which they appear in the **Grouping** viewer.  
  
    -   Correlate messages across different data sources, such as a log and a saved trace file.  
  
---  
  
     **More Information**   
     **To learn more** about the **Grouping** viewer, see the [Grouping Viewer](grouping-viewer.md) topic.   
---  
  
-   **Pattern Match** viewer — enables you to select a **Pattern** expression from a Library of predefined **Patterns** from Microsoft, that can aggregate a collection of messages from a set of trace results that all contain a common pattern or sequence that matches the criteria of the applied **Pattern** expression. A pattern might consist of a sequence of fields, properties, values, annotations, or other relationships. This feature can help you expose the context or sequence in which certain events occurred across the timeline of a trace session, as opposed to filtering, where the impact is typically limited to the boundary of individual messages rather than to groups of messages. The **Pattern Match** viewer contains an **AVAILABLE PATTERNS** Library from where you can select predefined **Pattern** expressions that provide pattern locating functions that can be useful in most environments. The **Pattern Match** viewer also provides a **Create Pattern** button that opens the **Pattern Editor** dialog from where you can create your own **Pattern** expressions.  
  
     When you click the **Create Pattern** button in the **Pattern Match** viewer to open the **Pattern Editor** dialog, it opens to the **Quick** tab, which contains an **Insert Message** button that enables you to select message fields from the **Field Chooser** **Tool Window**, after which the **Quick** tab will be populated with initial data for a message type that you selected, along with other UI automation that you can access by clicking the **Insert Criteria** link. You will also notice a **Free Form** tab in the **Pattern Editor** that contains an editing surface where you can write a **Pattern** expression in Open Protocol Notation (OPN) code without the support of any UI automation, although you would need to be familiar with OPN to do so.  
  
     Note that you can also open the **Pattern Editor** dialog by right-clicking a message in the **Analysis Grid** viewer and then selecting the **Create Pattern** command in the context menu that appears. However, in this case, the **Pattern Editor** dialog opens to the **Quick** tab with UI automation controls provided and seed data already inserted, to help you develop a **Pattern** expression more quickly. Moreover, the **Quick** tab is pre-populated with initial information that is derived from the message/s you selected in the **Analysis Grid** viewer, the assumption being that you want to create a **Pattern** expression based on a sequence of fields, properties, or values (in some relationship to one another) from the selected message type, and which you will define in the expression you create.  
  
---  
  
     **More Information**   
     **To learn more** about using the **Pattern Match** viewer and creating your own **Pattern** expressions, see the [Pattern Match Viewer](pattern-match-viewer.md) section.  

---  
  
-   View **Filters** — enable you to apply a built-in or custom Filter Expression to a set of trace results to isolate specific messages that can expose errors, values, or other details, in order to pinpoint the cause of a particular problem that is occurring. Only the messages that pass the criteria of the applied filter are returned, while all others are temporarily removed from the results, so you can create a focused set of messages for analysis. A view **Filter** is a handy analysis tool because you can apply and remove them without impacting the original set of trace results, or you can specify a different view **Filter** to create a new set of results that present a different analysis perspective. You can select built-in view **Filters** from a centralized **Library** or configure custom Filter Expressions of your own on any Filter panel text box on the Filtering toolbar just above the data viewing surface.  
  
---  
  
     **More Information**   
     **To learn more** about view **Filters**, see [Applying and Managing Filters](applying-and-managing-filters.md).   

---  
  
-   **Viewpoints** — enable you examine network traffic from the perspective of a particular protocol or stack layer, with no messages above it. By applying a built-in  **Viewpoint**, you can remove messages above the **Viewpoint** to create a focused set of messages that can expose details that are normally hidden within the message stack. A **Viewpoint** can create a unique analysis perspective on your data, while at the same time streamlining the analysis process. For example, if you want to view and troubleshoot TCP messages only, you can select the **TCP** viewpoint to drive TCP messages, including fragments, to top-level in the **Analysis Grid** viewer, with all upper layer protocols or modules removed from view. Message Analyzer provides numerous built-in **Viewpoint** configurations that are contained in a Library that is accessible from the **Viewpoints** drop-down list on the Filtering toolbar just above the data viewing surface.  
  
     This drop-down list also has a **Viewpoint** called **Disable Operations** that enables you to break up all the request/response message pairs that are encapsulated in top-level Operation nodes in the **Analysis Grid** viewer, for protocols that make use of these pairs, such as HTTP, DNS, SMB, and LDAP. This reestablishes the  chronological context in which messages were originally captured, similar to the Network Monitor view, although this makes response messages  more difficult to locate and correlate with their associated request messages. In addition, you have the option to apply a **Viewpoint Filter** that is accessible from the centralized **Library** on the Filter panel that displays when you select the **Add Viewpoint Filter** command from the **Add Filter** drop-down list on the Filtering toolbar. This type of filter enables you to further refine the focus of messages by applying filtering *after* a **Viewpoint** is applied. However, note that you can configure and apply a **Viewpoint Filter** only  after a **Viewpoint** is applied to a set of trace results.  
  
---  
  
     **More Information**   
     **To learn more** about **Viewpoints**, see [Applying and Managing Viewpoints](applying-and-managing-viewpoints.md).   

---  
  
-   **Parsing** options — enable you to reparse trace results based on an alternate port specification that differs from the standard port typically used by a particular protocol. It is becoming a common practice to pass traffic to alternate ports to avoid exposing network traffic to exploitation. The **Parsing** options provide a range of protocols for which you can specify an alternate port to accommodate traffic that used such an alternate port. For example, you might specify alternate port 8080 instead of HTTP standard port 80, or alternate port 3268 for LDAP standard port 389.  
  
     The protocols for which you can specify alternate ports are contained in a drop-down list on the **Parsing** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. You can also launch this dialog by right-clicking a message in the **Analysis Grid** viewer and then selecting the **Parse As** command from the context menu that appears. When you specify one or more alternate port numbers for a particular protocol, the OPN parser for that protocol uses the port number/s that you specified when your trace is reparsed, so you can view the messages received on the specified ports.  
  
---  
  
     **More Information**   
     **To learn more** about **Parsing** options, see the **Parsing** section of [Setting Message Analyzer Global Options](setting-message-analyzer-global-options.md).   

---  
  
-   **Shift Time** dialog — enables you to change the **Timestamp** of captured messages that are displayed in an Analysis Session. The time shift capability enables you to compensate for skewed system clock values or time zone differences across different computers, so that you can chronologically align the messages from those computers and ensure accurate troubleshooting.  
  
---  
  
     **More Information**   
     **To learn more** about the **Shift Time** feature, see [Setting Time Shifts](setting-time-shifts.md).   

---  
  
-   **Aliases** — enables you to substitute more friendly names for several types of data field values in the **Analysis Grid** viewer, to facilitate easier recognition of values that can otherwise be cryptic and difficult to work with, for example IPv4 and particularly IPv6 addresses. This feature can improve your ability to discover and analyze specific message traffic through the use of simplified names that have meaning in your troubleshooting environment. By customizing your data analysis environment with **Aliases**, keeping track of traffic to and from host IP addresses, physical addresses, and ports becomes easier. By default, Message Analyzer provides two **Loopback** **Aliases** that you can select from the **Aliases** drop-down list on the Message Analyzer global toolbar.  
  
---  
  
     **More Information**   
     **To learn more** about the **Aliases** feature, see [Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md).   

---  
  
-   **Color Rules** — an important analysis feature for the **Analysis Grid** viewer that enables you to use color, text, and font styles to decorate and highlight messages that contain specific types of information that you can identify at-a-glance, which can preclude the need for additional analysis and diagnostics. **Color Rules** can provide an instant visual cue of messages that meet predefined criteria, to alert you that closer scrutiny and further investigation may be needed. By default, Message Analyzer provides a **Color Rule** Library that contains a host of built-in **Color Rules** that you can use immediately. You can also create your own **Color Rules** to meet the needs of your particular environment.  
  
---  
  
     **More Information**   
     **To learn more** about **Color Rules**, see [Using and Managing Color Rules](using-and-managing-color-rules.md).   

---  
  
-   **Go To Message** — an important analysis feature for the **Analysis Grid** viewer that enables you to quickly locate any message by number in a large collection of messages. If you are working with multiple data sources, the **Go To Message** dialog provides options to search across all data sources for a particular message number that you specify, or you can select a specific data source to search. By using this feature, you can accelerate your analysis process, especially in support scenarios where you are being directed to find particular messages very quickly.  
  
---  
  
     **More Information**   
     **To learn more** about the **Go To Message** features, see [Using the Go To Message Feature](using-the-go-to-message-feature.md).   

---  
  
-   **Layouts** — an essential analysis feature for the **Analysis Grid** viewer that enables you to select view **Layout** configurations that are tailored for different types of message analysis. View **Layouts** add new data columns to the **Analysis Grid** to expose typical field information of specific protocols that is related to issues that are commonly investigated for such protocols. For example, if you are troubleshooting TCP, you might select one of the **TCP Deep Packet Analysis** view **Layouts** to populate your **Analysis Grid** viewer with data that enhances this type of analysis.  
  
     Message Analyzer provides numerous view **Layouts** that are customized for common analysis scenarios. You can access these from the **Layout** drop-down list on the **Analysis Grid** toolbar. You can also create your own custom view **Layouts** by adding columns to the **Analysis Grid** viewer with the **Field Chooser** **Tool Window** and then saving your configuration with the **Save Current Layout As…** command from the **Layout** drop-down list.  
  
    > [!NOTE]
    >  Message Analyzer also provides the **Profiles** feature, which displays preset configurations of data viewers and **Layouts** that are specifically designed to create a unified and interactive analysis environment that is tailored for the type of data you are loading into Message Analyzer. For example, if you are loading data from .cap files, you can select a **Profile** such as the **Performance Top Down Profile**, that will display the **Performance Top Down** layout for the **Analysis Grid** viewer, the **Process Names and Conversations** layout for the **Grouping** viewer, and the **Top TCP/UDP Conversations by Message Count** layout for the **Chart** viewer, providing that you enable the **Performance Top Down Profile** prior to loading data from such an input file.  
    >   
    >  For further details about Message Analyzer **Profiles**, see [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md).  
  
---  
  
     **More Information**   
     **To learn more** about **Analysis Grid** viewer **Layouts**, see [Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md).   
    **To learn more** about **Grouping** viewer **Layouts**, see the [Grouping Viewer](grouping-viewer.md) topic.  
    **To learn more** about **Layouts** for the **Chart** viewer, see the [Chart Viewer Layouts](chart-viewer-layouts.md) topic.  

---  
  
-   **Unions** — an important analysis feature for the **Analysis Grid** viewer that enables you to correlate data from varying field names in multiple data sources, where the data is of the same type but the field names are different. This feature can streamline the analysis of logs and saved traces from a common environment, where the file formats of these message sources use different naming conventions to identify the same data fields. When this is the case, Message Analyzer can display this field data from multiple sources in a single **Analysis Grid** data column that is named by a **Union** that you create.  
  
     By default, Message Analyzer provides several common **Unions** that exist in the **Unions** node of the **Field Chooser** **Tool Window**. You can add one or more of these **Unions** as new columns in the **Analysis Grid**; however, it will be useful only if it is appropriate for the data you are analyzing. For example, if you are working with an SMB trace and a SambaSysLog, you might add   the **SMBCommand** union as a new column to merge the **SMB.Command** field of the trace and the **SambaSysLog.smb_command.command.smb_com** field of the log. You can add this new column to the **Analysis Grid** viewer by right-clicking the **Union** and selecting the **Add as Column** command in the context menu that appears.  
  
     You can assess the data fields that are merged with any of the built-in **Unions** by opening the **Manage Unions** dialog that is accessible from the **Unions** drop-down list in the global Message Analyzer **Tools** menu. In the **Manage Unions** dialog, right-click a **Union** in the list and select the **Create a Copy** command in the context menu that appears, which in turn displays the **Edit Union** dialog. The fields that are merged by the selected **Union** appear in the **Select fields to include** list box of the **Edit Union** dialog. Note that you can also manually configure your own **Unions** by creating a single field entity that correlates multiple disparate field names from different data sources with the use of the **Edit Union** dialog, which is accessible as specified immediately above, or by clicking the **Unions** button on the global Message Analyzer toolbar.  
  
---  
  
     **More Information**   
     **To learn more** about **Unions**, see [Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md).   

---  
  
-   **Diagnostics** — a feature that can be critical when attempting to assess the cause of errors and failures in a set of trace results. Message Analyzer provides two different tools that provide diagnostic information. These tools are similar but they present data in different ways. The first is the **DiagnosisTypes** column in the **Analysis Grid** viewer. If an error occurred for a particular message, one of four different icons appear in the **DiagnosisTypes** column for that message; however, the diagnostic information can be scattered across the trace or buried deep in the message stack, making it a little harder to analyze.  
  
     One technique you can use to gather the messages that have diagnostic information is to sort the **DiagnosisTypes** column. But this does not necessarily expose the actual messages that contain a diagnosis condition, since Message Analyzer bubbles up the icons to top-level as a cue that you have an embedded diagnosis message. In addition, by simply sorting, it might not be readily apparent as to what the diagnostic message descriptions indicate nor does it expose how many contain the same message description, without performing a laborious manual process of repetitive node expansions in the **Analysis Grid** viewer. To alleviate this problem, Message Analyzer provides a **Diagnostics** **Tool Window**, which contains tabular data that summarizes the diagnosis type, the module in which diagnosis messages occurred, the message descriptions, and the number of identical messages for each diagnosis type. In addition, selection of a diagnosis row in the **Diagnostics** **Tool Window** table interactively drives message selection in the **Analysis Grid** viewer for immediate data correlation. At a single glance, these summaries can provide an instant assessment of where problems exist in the context of an entire trace.  
  
---  
  
     **More Information**   
     **To learn more** about Message Analyzer diagnostics, see the [Diagnostics Tool Window](diagnostics-tool-window.md) and [Diagnosis Types](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topics.   

---  
  
-   **Message selection** — Message Analyzer provides some very useful enhancements to the message selection process, by enabling you to track the messages that you select in any particular part of an Analysis Session. This capability is provided by the **Selection** **Tool Window**, which is accessible from the **Windows** submenu of the Message Analyzer global **Tools** menu. By building a collection based on your message selections, Message Analyzer enables you to backtrack to specific messages that you selected earlier during analysis, to revisit them for further scrutiny. You can also forward track through the selection collection for the same purpose. This feature can be of benefit if you are analyzing multiple messages in a large set of data. It is also advantageous if you accidentally lose focus on a message, because you can return to any previous selection with a single click on the **Go  back** or **Go Forward** button on the **Selection** window toolbar.  
  
     You can also turn message **Selection** tracking on and off, at your discretion. Also note that message selection is interactive with other viewers and some **Tool Windows** for enhanced correlation capabilities. You can even navigate message selections that you made across different Message Analyzer sessions.  
  
---  
  
     **More Information**   
     **To learn more** about message selection capabilities, see the [Selection Tool Window](selection-tool-window.md) topic.   

---  
  
-   **Tool Windows** — the Message Analyzer **Tool Windows** provide a vast amount of functionality that enhances the data analysis process. Some **Tool Windows** interact with data viewers, for example, message selection in a **Tool Window** may drive message highlighting in a data viewer such as the **Analysis Grid**, and vice versa. Moreover, message selection in the **Analysis Grid** can also drive the display of various message details in **Tool Windows** such as the **Message Stack**, **Details**, and **Field** windows, which provide a core set of analysis tools that you will no doubt use on a consistent basis. Some **Tool Windows** are session-specific, for example the **Diagnostics** window, which means that they respond to session selection and are not driven by message selection in other tools or viewers. Some **Tool Windows** are message-specific, for example the **Details** window, which means that they do respond to message selection in other tools or viewers.  
  
---  
  
     **More Information**   
     **To learn more** about the **Tool Windows** that Message Analyzer provides, see the [Tool Windows](tool-windows.md) section.   

---  
  
-   **Field Chooser** — this **Tool Window** enables you to enhance the functionality of other analysis tools. It displays the message hierarchy for all modules and protocols for which Message Analyzer contains OPN parsers. The **Field Chooser** message hierarchy consists of message types, fields, and properties for all modules with expandable nodes in a tree format. It also contains various global fields, annotations, and properties that you can utilize in various ways. The following are a few examples of how you can use the **Field Chooser**:  
  
    -   Add message fields as columns to the **Analysis Grid** viewer and **Grouping** viewer, to enhance the scope of the data that these viewers present.  
  
    -   Select fields or properties that you want to use in a data formula for a new **Chart** viewer **Layout** you are creating.  
  
    -   Select fields or properties that you want to use in a **Pattern** expression you are creating.  
  
    -   Correlate disparate field names of the same type from different data sources into a single entity when creating a new **Union**.  
  
    -   Review message hierarchies to discover field and property names of various protocols, to use when you are creating Filter Expressions.  
  
---  
  
     **More Information**   
     **To learn more** about the **Field Chooser**, see the [Using the Field Chooser](using-the-field-chooser.md) and [Field Chooser Tool Window](field-chooser-tool-window.md) topics.   

---  
  
-   **Analysis Grid** **Group** command — a handy feature that enables you to organize trace data into groups based on the varying values of an **Analysis Grid** viewer data column, which is named by and displays the values of a field, property, annotation, or method across a set of trace results or log content. By organizing values into groups, you can quickly isolate messages of interest and make it easier to discover data for which you are searching. For example, if you right-click the **DiagnosisType** column in the **Analysis Grid** viewer and select the **Group** command, you can isolate your data into groups with expandable nodes where each group contains the same type of diagnosis message. In addition, you can perform subsequent **Group** commands in like manner to create a *nested* group configuration that enables you to correlate data among the groups. Lastly, you have the option to reorder the nesting configuration by dragging and dropping group labels into different positions of the initial group order. Reorganizing your trace data into groups or nested group configurations with the **Group** command enables you to create unique analysis perspectives that facilitate rapid identification of issues.  
  
---  
  
     **More Information**   
     **To learn more** about the **Analysis Grid** grouping feature, see [Using the Analysis Grid Group Feature](using-the-analysis-grid-group-feature.md).   

---  
  
-   **Analysis Grid column filtering** — a feature that enables you to conveniently isolate messages according to a specified search string that matches a value in a particular data column. You simply click the **Show Column Filter Row** icon on the left side of the column label row to display an amber-colored search box below each column label. Thereafter, you can enter a search string and Message Analyzer automatically reorganizes the data display to include only the messages that contain a column value that matches your search string, that is, if any such values are found.  
  
     For example, if you typed the name of a protocol in the amber text box below the **Module** column label, such as HTTP, then Message Analyzer will temporarily remove all other messages in the trace results except HTTP. When you remove the search string, Message Analyzer reinstates the original message set. You also have the option to specify another search string as a column filter to further narrow down your results. For instance, after specifying a column filter such as HTTP in the previous example, you might also specify a search string for the **Summary** column with the text “GET”, to filter out all messages from the display, except HTTP requests that use the GET method. This feature can help you quickly locate specific messages with specific field values in a large data set and reduce your analysis time.  
  
---  
  
     **More Information**   
     **To learn more** about the column filtering feature, see the [Filtering Column Data](filtering-column-data.md) topic.  

---  
  
-   **View**  
     **Field and Property values** — a core analysis feature that enables you to view the values of any field or property in messages that were parsed by Message Analyzer. These values will display in the **Details** **Tool Window**, which appear when you select a message in the **Analysis Grid** viewer. The **Details** window typically shows the field or property **Name**, **Value**, **Bit Offset**, **Bit Length**, and **Type**. It is likely that you will use this **Tool Window** extensively in analysis, because it immediately exposes the values of any message field.  
  
---  
  
     **More Information**   
     **To learn more** about viewing message field and property values, see the [Message Details Tool Window](message-details-tool-window.md) topic.   

---  
  
-   **Track Field and Property values** — this feature adds a new dimension to field and property analysis, by enabling you to select specific fields or properties for which you want to track values across a message set. You will find this capability on the toolbar of the **Details** **Tool Window**, which displays the following icons. You can identify these icons by their hover-over tool tips:  
  
    -   **Show all fields for the selected message** — click this icon to show all fields for a message that you selected.  
  
    -   **Show all properties for the selected message** — click this icon to show all properties that apply to a message that you selected.  
  
    -   **Show tracked fields and properties for the selected message** — displays a list of fields and/or properties that you have set for tracking.  
  
     You can set a field or property for tracking by right-clicking it in the **Details** window and then selecting the **Track ‘field/propertyName’** command, where  'field/propertyName' is a placeholder for an actual field or property name. Thereafter, you can display the tracking list and then either scroll through or arbitrarily select **Analysis Grid** messages to view tracked values. You might also select messages in the **Grouping** viewer and monitor tracked fields or properties in **Details**. Moreover, if the **Selection** **Tool Window** is enabled for selection tracking, you can forward- and back-navigate through your selections to assist your analysis process.  
  
---  
  
     **More Information**   
     **To learn more** about tracking message field and property values in the **Details** window, see the [Using the Details Tool Window Features](message-details-tool-window.md#BKMK_UsingDetailsTracking) topic.   

---