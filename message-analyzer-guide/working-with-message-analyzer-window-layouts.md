---
title: "Working with Message Analyzer Window Layouts | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 07ceada1-6558-4710-965e-9a71834de3d3
caps.latest.revision: 53
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Working with Message Analyzer Window Layouts
By default, Message Analyzer provides several built-in **Window Layouts** that organize the **Analysis Grid** viewer with different **Tool Windows** as preset configurations that enable you to customize your working environment for the type of troubleshooting and analysis in which you are engaged. The window layouts that you can choose range from simple to increasingly more complex selections in the **Window Layout** drop-down list, and are intended to accommodate a cross-section of typical Message Analyzer users. You can access this drop-down list from the global Message Analyzer toolbar. The typical layout configuration consists of a single/default data viewer and an arrangement of one or more **Tool Windows**. By default, Message Analyzer uses the **Analysis Grid** viewer in all the built-in **Window Layouts**; however, you can set a different **Default Viewer** from the **Profiles** tab of the **Options** dialog that is accessible from the global Message Analyzer **Tools** menu. You can also add other **Tool Windows** to any of the built-in **Windows Layouts**, as needed.  
  
 You also have the option to further customize your analysis environment by redocking any data viewer or **Tool Window** in use to a location that facilitates easier viewing and analysis, or better correlation of related message data that is held in different views, as described in [Using the Redocking Features](working-with-message-analyzer-window-layouts.md#BKMK_UsingRedockingFeatures). If you do not select one of the built-in **Window Layouts**, Message Analyzer still provides a default window layout that contains the **Analysis Grid** viewer and several **Tool Windows** that provide a basic configuration for analysis, as described in [Using the Message Analyzer Default Window Layout](working-with-message-analyzer-window-layouts.md#BKMK_UsingDefaultLayout). You will see this default layout configuration at first Message Analyzer startup and upon all subsequent startups unless you change the layout by any of the following actions:  
  
-   Manually open other **Tool Windows** from the **Windows** submenu in the global Message Analyzer **Tools** menu.  
  
-   Remove one or more **Tool Windows** from the default layout.  
  
-   Select one of the built-in **Window Layouts** on the global Message Analyzer toolbar.  
  
-   Redock viewers and/or **Tool Windows** to other locations to create a custom configuration for your environment.  
  
-   Manually change the **Default Viewer** on the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu.  
  
-   Load data from a file type for which a viewer configuration is defined by a default or custom **Profile**, as described in topic [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md).  
  
 The following topics in this section describe how to work with **Window Layouts**.  
  
---  
  
 [Using the Message Analyzer Default Window Layout](working-with-message-analyzer-window-layouts.md#BKMK_UsingDefaultLayout)   
 [Using the Built-In Window Layouts](working-with-message-analyzer-window-layouts.md#BKMK_UsingWindowLayouts)   
 [Redocking Data Viewers and Tool Windows](working-with-message-analyzer-window-layouts.md#BKMK_RedockViewersToolWindows)   
 [Performing Docking Operations](working-with-message-analyzer-window-layouts.md#BKMK_PerformDockingOps)   
 [Using the Redocking Features](working-with-message-analyzer-window-layouts.md#BKMK_UsingRedockingFeatures)   
 [Saving Window Layouts](working-with-message-analyzer-window-layouts.md#BKMK_SaveWindowLayouts)   
---  
  
<a name="BKMK_UsingDefaultLayout"></a>   
## Using the Message Analyzer Default Window Layout  
 The default viewer and **Tool Window** layout configuration  that displays on the first Message Analyzer startup is briefly described in the list below. You can continue to use the default layout as is, or you can add other  **Tool Windows** from the **Windows** submenu of the global Message Analyzer **Tools** menu as needed. The **Tool Window** configuration that you specify is recorded and persisted through subsequent Message Analyzer startups, until you change it to a new configuration, which in turn is persisted  until you change it again. You can also redock the **Analysis Grid** viewer or any **Tool Window** to another location by making use of the Docking Navigation Control that displays when you undock a window and hover over certain user interface (UI) locations. However, the **Analysis Grid** viewer, or whatever viewer is set as the default on the **Profiles** tab of the **Options** dialog, will persist in its default location on Message Analyzer restarts. The  default viewer and **Tool Window** configuration that is provided by Message Analyzer consists of the following:  
  
-   **Analysis Grid** — a redockable and interactive tree grid configuration display with expandable message nodes that is the default  Message Analyzer viewer for data analysis. It includes  inline stack,  details, and diagnosis information that is   accessible from each top-level message; encapsulation of network stack messages; related Operation messages condensed into a common node; along with sorting, grouping, filtering, and so on. Includes a  default column **Layout** for common  analysis  of trace results.  
  
     See the [Analysis Grid Viewer](analysis-grid-viewer.md) topic for further details on analyzing data with this viewer.  
  
-   **Message Stack 1** — a redockable and interactive **Tool Window** that enables you to view the network stack layers (origins tree) for any selected message that contains a message stack configuration in a Data Retrieval Session or Live Trace Session.  
  
     See the [Message Stack Tool Window](message-stack-tool-window.md) topic for further details on how to use this feature.  
  
-   **Details 1** — a redockable **Tool Window** containing message field names, values, types, bit offset, and bit length specifications, that is interactively driven by message selection in the **Analysis Grid** viewer and other viewers.  
  
     See the [Message Details Tool Window](message-details-tool-window.md) topic for further details on how to use this feature.  
  
-   **Message Data 1** — a redockable **Tool Window** that contains hexadecimal values by default for fields that you select in the **Details** **Tool Window**.  
  
     See the [Message Data Tool Window](message-data-tool-window.md) topic for further details on how to use this feature.  
  
-   **Field Data** — a redockable **Tool Window** that displays a string or other value for fields that you select in the **Details** **Tool Window**.  
  
     See the [Field Data Tool Window](field-data-tool-window.md) topic for further details on how to use this feature.  
  
-   **Session Explorer** — a redockable and interactive **Tool Window** that enables you to open new data viewers or explore and select open sessions and the viewers in each session for data captured or loaded into Message Analyzer.  
  
     See the [Session Explorer Tool Window](session-explorer-tool-window.md) topic for further details on how to use this feature.  
  
-   **Field Chooser** — a redockable **Tool Window** that enables you to view all of the fields that Message Analyzer can parse. From the **Field Chooser**, you can use the **Add as Column** and **Add as Grouping** context menu commands to add new columns of data or groups to either the **Analysis Grid** viewer or **Grouping** viewer, depending on which viewer has focus when the chosen command is executed. You can also display the OPN definition for a field by executing the **Go To Definition** context menu command from the **Field Chooser**.  
  
     See the [Field Chooser Tool Window](field-chooser-tool-window.md) topic for further details on how to use this feature.  
  
 Other redockable **Tool Windows** that you can manually select for display in any Message Analyzer session are available as items in the **Windows** submenu which is accessible from the global Message Analyzer **Tools** menu. This includes the **Bookmarks**, **Comments**, **Diagnostics**, **Decryption**, **Selection**, and **Output** **Tool Windows**.  
  
<a name="BKMK_UsingWindowLayouts"></a>   
## Using the Built-in Window Layouts  
 The built-in **Window Layouts** that are provided by Message Analyzer are described in the list that follows. You can select these layouts from  **Window Layout** drop-down list on the global Message Analyzer toolbar.  
  
-   **Simple** — this layout is the simplest configuration that is available from the **Window Layout** drop-down list. It contains the **Analysis Grid** viewer and the **Details** **Tool Window** for a basic analysis of messages and message field data. After you select a message in the **Analysis Grid**, the message field names, values, types, and so on, display in the **Details** window. The context menus are still available for both the **Analysis Grid** viewer and **Details** window, so you can continue to use the right-click method to create Filters, Groupings, and so on.  
  
     You might use this layout to perform simple analysis of messages and field data, when analysis of the network layers is of less importance.  
  
-   **Simple with Field Data** — this layout is also a basic configuration similar to the **Simple** layout, only it adds the **Field Data** **Tool Window** to the layout. The **Field Data** window displays field values when you select field names in the **Details** window.  
  
     Similar to the **Simple** layout, you might use this layout to perform simple analysis of messages and field data, although this layout also enables you to quickly assess the alphanumeric values of fields that you select in the **Details** window.  
  
-   **Network** — this layout adds the **Message Stack** **Tool Window** to the **Simple with Field Data** layout configuration to facilitate quick analysis of the network message stack, while retaining all the capabilities of the previously described layouts.  
  
     You might use this layout when troubleshooting the Network stack protocols that support top-level operations or other transactions of a particular application.  
  
-   **Multiple Sessions** — this layout adds the **Session Explorer** **Tool Window** to the **Network** layout configuration to enable you to quickly select the data that is presented in any viewer in one or more sessions. This layout also adds the hexadecimal **Message Data** **Tool Window** to facilitate an additional view of the hexadecimal values of message fields as they exist in the context of an entire message stream. It also provides the **Output** window, which displays text from the Message Analyzer log file that indicates errors and other statistical information.  
  
     You might use this layout when you have multiple sessions and one or more data viewers in each session, to instantly display the data in any data viewer with a single click. This provides the capability to quickly correlate and assess your data in multiple presentation formats for an enhanced analytical perspective.  
  
-   **Protocol Development** — this layout adds the  **Compare Fields** **Tool Window** to the **Multiple Sessions** layout, which can be advantageous when using Message Analyzer to validate protocol field values, states, and behaviors in protocol development and testing scenarios. In addition, the **Message Data** **Tool Window** can be useful for analyzing hexadecimal data and determining whether some message fields are not being parsed. This layout also removes the **Session Explorer** **Tool Window**, which is typically not required in these scenarios.  
  
     You might use this layout when troubleshooting the client- or server-side communications of a new protocol in development.  
  
-   **Advanced** — this layout adds the **Selection**, **Bookmarks**, **Comments**, and **Session Explorer** **Tool Windows** to the previous **Protocol Development** layout and relocates some **Tool Windows** such as the **Field Data** and **Output** windows.  
  
     You might use this layout when it is important to annotate messages for follow-up data reviews by others, when you need to see Message Analyzer errors and other statistics provided in the **Output** window, and/or to take advantage of the Message Analyzer advanced message **Selection** and tracking capabilities.  
  
> [!NOTE]
>  You have the option to add other **Tool Windows** to any built-in **Window Layout**, as required, and they will be saved and persisted across subsequent Message Analyzer restarts until you modify the configuration again.  
  
<a name="BKMK_RedockViewersToolWindows"></a>   
## Redocking Data Viewers and Tool Windows  
 Message Analyzer provides you with the flexibility to reposition the different data viewers and **Tool Windows** that contain your trace results information, by undocking them from their default locations and redocking them in another sector of the UI. After you undock a data viewer or **Tool Window**, you have the option to float, resize, redock, or remove it, as described in [Performing Docking Operations](working-with-message-analyzer-window-layouts.md#BKMK_PerformDockingOps). You can also restore any **Tool Window** that you previously removed (closed). Message Analyzer provides the capability to reposition any data viewer or **Tool Window** mainly for the enhancement of your analysis perspective, as described in [Using the Redocking Features](working-with-message-analyzer-window-layouts.md#BKMK_UsingRedockingFeatures).  
  
 **Utilizing the Docking Navigation Controls**   
To facilitate window relocation, Message Analyzer provides the Docking Navigation Control, which is a simple mechanism that enables you to redock any data viewer or **Tool Window** in a new location after you have initially undocked it. This control is built into the UI as part of the window docking infrastructure and  displays immediately after you drag any data viewer tab or **Tool Window** tab away from its current docking location. The Docking Navigation Control displays in various UI locations to facilitate the window relocation capabilities; however, the size of the control varies depending on the section of the UI where you drag a window. The  Docking Navigation Control contains a central tab and four directional arrow tabs that enable you to preview a drop location whenever you hover over one of these elements while dragging an undocked window with your mouse. As previously indicated, you can use the Docking Navigation Control to configure a new location for a data viewer or **Tool Window** that is more convenient or better suited to your analysis environment.  
  
<a name="BKMK_PerformDockingOps"></a>   
### Performing Docking Operations  
 There are several operations that you can perform when working with data viewer and **Tool Window** locations. To move a data viewer or **Tool Window** from its default or current docking location, click a data viewer or **Tool Window** tab and drag it away from the docking location. The operations that you can perform when relocating **Tool Windows** and data viewers consist of the following:  
  
-   **Float** — you can float a data viewer or **Tool Window** by dragging it from its default docking location, as previously indicated. After you float a data viewer or **Tool Window**, you can redock it, or leave it in the undocked state, either within or outside the Message Analyzer UI, and it will continue to interact appropriately with other data viewers or **Tool Windows**, just as it did from its previous docking location. For example, you can continue to drive the population of data into a floating **Message Data** **Tool Window** through message selection in a floating **Analysis Grid** viewer.  
  
     If you choose to redock a floating data viewer or **Tool Window** to its default or other preferred location, you can do so by dropping the window on an appropriate directional arrow of the Docking Navigation Control.  
  
-   **Resize** — you can resize any **Tool Window** or data viewer, floating or otherwise, in the same way that you resize any window, which is by hovering over any window edge with your mouse and using the expansion/contraction arrow to select and guide the direction of the resize.  
  
-   **Redock** — you can redock any window, floating or otherwise, by dragging it with the mouse and positioning it over one of the directional arrows of the Docking Navigation Control that previews the location you want. When you have selected the new location, release the mouse button.  
  
-   **Remove** — to remove (close) a data viewer or **Tool Window** in its current display location in a Message Analyzer session, click the **X** mark on the viewer session tab or on the title bar of the **Tool Window**. If a data viewer or **Tool Window** is floating, you can remove it the same way.  
  
<a name="BKMK_UsingRedockingFeatures"></a>   
### Using the Redocking Features  
 When using Message Analyzer to analyze data, a typical scenario might be to display the results of several different sessions in different data viewer formats. It is also common to display the results of a single session in multiple data viewer formats. However, Message Analyzer data viewers such as the **Analysis Grid** are by default positioned in a row of session tabs, one for each viewer instance, where only the data of the in-focus tab is visible. To view the data in another session viewer tab, you must select that tab. But at times, it may be advantageous to expose the data of multiple viewers simultaneously, to achieve an interactive context for comparative purposes when you are correlating data.  
  
 **Driving Interactive Display of Data**   
Taking the previous scenario as an example, you might want to interactively drive message displays in the **Analysis Grid** viewer by choosing certain **Matched Instance** messages from the **Pattern Match** viewer that met the filtering criteria of a particular **Pattern** expression and display them in the **Analysis Grid** viewer. In this configuration, or by interactively driving the **Analysis Grid** viewer display from message selection in another viewer instance such as the  **Gannt** viewer, you can immediately assess the context of the points in time where the associated messages occurred in a trace.  
  
 To position the viewers in this configuration so you can simultaneously and interactively view the data in these different formats, you can undock the **Pattern Match** viewer (or **Gannt** viewer) and redock it to display next to the **Analysis Grid** viewer, so that the data in both viewers is visible at the same time, but in separate session tabs. Note that you  have the option to float the viewer you are undocking while you assess where your new docking location will be. While dragging the window you are relocating over the Docking Navigation Control tab or arrows, release your mouse button when the control previews the docking location you want.  
  
 After the redock is complete, you can select any **Matched Instance** in the **Pattern Match** viewer and the messages of the **Matched Instance** immediately display in the **Analysis Grid** viewer. A similar type of interaction will occur if you select a color-coded message bar in the **Gannt** viewer. The advantage of seeing these messages in the **Analysis Grid** viewer, is that you can quickly examine the details, field values, and stack configuration of  messages in this view.  
  
 Another useful docking configuration that Message Analyzer provides  is the default location of the **Grouping** viewer and the **Analysis Grid** viewer.  In the default locations of these viewers, you can easily correlate data in any filtered group that you select in the **Grouping** viewer with corresponding message data that displays in the **Analysis Grid** viewer, that is, when the **Grouping** viewer is in the **Selection** mode. However, you can still move the **Grouping** viewer to a new docking location in accordance with your preferences.  
  
 **Correlating Trace and Log Data**   
At other times, you might need to compare different traces and related log file data, perhaps from different time zones, or you might want to review historical versus current trace results. When this is the case, you can follow the processes outlined earlier in this section to relocate your data viewers in appropriate positions.  
  
> [!TIP]
>  When you are comparing trace results, you can take advantage of the **Compare Fields Tool Window**. This feature enables a quick comparison of the field values of any two messages, as described in the [Compare Fields Tool Window](compare-fields-tool-window.md) topic.  
  
> [!NOTE]
>  If you have many data viewers displaying in multiple sessions, the session tabs that contain viewer data can exceed the width of the available space in the Message Analyzer UI. When this is the case, you can scroll to the hidden session tabs by clicking the direction arrows (**\< >**) in the upper-right corner of the session tab row. In addition, if the position of a viewer appears to be locked in place when you try to drag an edge to reposition it, you can use the direction arrows to move the viewer window position while the particular viewer is in focus.  
  
<a name="BKMK_SaveWindowLayouts"></a>   
### Saving Window Layouts  
 Message Analyzer automatically saves the current window layout when you shut the application down, which can be one of the built-in **Window Layouts** that are accessible from the global Message Analyzer toolbar or a custom window layout that you configured for your environment. In either case, the window layout that existed at the time of shutdown is then loaded back in at the next Message Analyzer startup.  
  
 Message Analyzer keeps track of the windows that you display and the positions where you dock them in a configuration file that exists in the following location:   
`%LocalAppData%\Microsoft\MessageAnalyzer\app.WindowLayoutAsset.cfg`  
When you close the Message Analyzer application, the configuration file is updated so that you can resume your latest window layout on the next Message Analyzer restart. Note that this file as well as other configuration files in this location are now versioned in newer Message Analyzer releases.  
  
## See Also  
 [Working With Message Analyzer Profiles](working-with-message-analyzer-profiles.md)