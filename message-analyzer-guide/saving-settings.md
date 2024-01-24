---
title: "Saving Settings | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e02da890-8ae6-47ad-86cc-c38f0b977001
caps.latest.revision: 47
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Saving Settings

When assessing data in an Analysis Session, you will invariably use the many features that Message Analyzer provides for data manipulation, including the default asset collection Library items, such as view  **Filters**, **Aliases**, **Viewpoints**, **Charts**, **Color Rules**, viewer **Layouts**, **Pattern Expressions**, and so on, that ship with Message Analyzer. However, it is likely that you will want to create your own customized versions of these Library items or create completely new items of your own to facilitate data analysis. If you create new Library items in the previously described categories for data analysis purposes, Message Analyzer enables you to save your settings for future use and for sharing with others through the Message Analyzer Sharing Infrastructure. When you save an item, it becomes part of the particular asset collection Library with which you are working and such items are available to you from the UI whenever you run Message Analyzer. It is these local Library items that you can share with others by making use of the Message Analyzer Sharing Infrastructure.  
  
 There are also additional settings that you can save with session data that include default settings that will apply to all live sessions, and other settings that are the result of manipulating trace data following an Analysis Session, as described in [Saving Other Settings](saving-settings.md#BKMK_SavingOtherSettings).  
  
## Saving Settings of Library Items  

 Message Analyzer provides the facilities for saving the settings of your asset collection Library items from the same location where you apply them for data analysis purposes. You can save the settings of the following asset Library item types in the indicated manner:  
  
-   View **Filters** — to save the settings of a custom view  **Filter** and add it to your local Filter Expression **Library**, first create one by selecting the **New Filter** item from the **Library** drop-down list on the Filtering toolbar. When you make this selection, the **Edit Filter** dialog displays, from where you can create and save a new Filter Expression based on editing an existing filtering item, or you can create a totally new one by writing a new Filter Expression. You can also specify a filter **Name**, **Description**, and a **Category** to place it in. When you are done with filter configuration, you can save the filter in your local Filter Expression **Library** by clicking the **Save** button in the **Edit Filter** dialog.  
  
 > [!NOTE]
 >  As indicated in various locations of this operating guide, your local Filter Expression **Library** is a centralized repository that contains the same set of filters that you access when selecting a **Session Filter**, view **Filter**, or **Color Rule** filter. You can also create and save a new Filter Expression in the centralized asset collection **Library** from any of the indicated locations where you select such Filter Expressions.  
  
 In addition, if you create and save a Filter Expression that uses an **Alias**, that filter will appear in the centralized Filter Expression **Library** as well. For example, this enables you to use such a Filter Expression containing an **Alias** as a **Session Filter**, **Color Rule** filter, or view **Filter**.  
  
-   **Aliases** — to save the settings of a custom **Alias** that you create as a friendly-name substitute for a cryptic field value that might be difficult to work with, and to save it to your **Aliases** collection, first create an **Alias** by right-clicking a field value in the **Analysis Grid** viewer that supports aliasing, such as an IP address, and then select the **Create Alias for \<’columnName’>…** item. The **Alias Editor** dialog then displays to enable you to provide the input data required to create a new **Alias**, which consists of **Value**, **Alias** name, **Description**, and **Category** information. When you are done configuring the **Alias**, you can save it in your **Alias** collection by clicking the **Save** button in the **Alias Editor** dialog. After you create an **Alias**, you can manage it along with other **Alias** collection items from the **Aliases** drop-down list on the Message Analyzer global toolbar or from the **Aliases** submenu on the global Message Analyzer **Tools** menu.  
  
-   **Unions** — to save the settings of a custom **Union** that you create to correlate varying field names that have  similar values in different data sources, and save it to your **Union** collection, first create a **Union** by clicking the **New Union** button on the global Message Analyzer toolbar or by selecting the **New Union** item  from the **Unions** drop-down list in the Message Analyzer **Tools** menu. After you make this selection, the **Edit Union** dialog displays and enables you to provide the input data required to create a **Union**, which consists of **Name**, **Category**, and **Fields** information. You can specify the **Field** information from the **Field Chooser** dialog that displays when you click the **Add** button in the **Edit Union** dialog. When you are done configuring the **Union**, you can save it to your **Union** collection by clicking the **Save** button in the **Edit Union** dialog. After you create a **Union**, you can manage it along with other **Union** collection items from the previously indicated toolbar and locations.  
  
-   **Viewpoints** — in the current Message Analyzer release, you can apply **Viewpoints** and manage them, which includes setting **Favorites** along with importing **Viewpoints** that are stored on user-defined shares and creating an export configuration that you can expose to other users through the Message Analyzer Sharing Infrastructure. However, you cannot create any custom **Viewpoints** of your own at this time.  
  
-   **Chart Layouts** — to save a new **Layout** for the **Chart** viewer that customizes your data analysis environment, first create one by selecting the **Edit** item in the **Chart** drop-down list that is accessible from the global Message Analyzer **Session** menu. Note that the **Edit** command is available only if you have the **Chart** viewer displayed with a selected **Layout** and in focus. The **Edit** command displays the **Edit Chart Layout** dialog from where you can modify the existing **Chart** configuration as you wish. Thereafter, to save your changes, you must select the **Save Current Layout As** command in the **Layouts** drop-down list that displays after you click the **Layout** item in the **Chart** drop-down list in the **Session** menu. This action adds your new  **Layout** to the **Message Analyzer Chart View Layouts** asset collection, which displays in the user Library that appears in the **New Viewer** drop-down list on the global Message Analyzer toolbar, among other places. Note that your new **Layout** is automatically added to the top-level **My Items** category of this asset collection, which you can view and manage from the **Manage Chart Layout** dialog that is accessible from the **Session** menu while a **Chart** is being displayed.  
  
-   **Color Rules** — to save the settings of a custom **Color Rule**, the filtering criteria it contains, and to add it to your local **Color Rule** user **Library**, first create one by selecting the **New Color Rule** item from the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar. When you make this selection, the **Edit Color Rule** dialog displays, from where you can create and save a new **Color Rule**.  
  
-   **Layouts** — to save the settings of a custom view **Layout** for the **Analysis Grid** viewer and add it to the local **Layout** user Library, first use the **Field Chooser** **Tool Window** to add new data columns that will expose the values of message fields that are of critical importance to solving a specific problem. For an example of a built-in column arrangement that focuses on TCP analysis, see the **TCP Deep Packet Analysis with ABSOLUTE Sequence Number Flat** view **Layout**. When you arrive at a useful configuration, you can save it as a new **Layout** that becomes part of the **Message Analyzer View Layouts** asset collection that you can access from your local **Layout** Library on the **Analysis Grid** toolbar, thus enabling you to apply the new **Layout** to the **Analysis Grid** viewer at any time. You can save your new **Layout** by clicking the **Save Current Layout As...** item from the **Layout** drop-down list on the **Analysis Grid** viewer toolbar. This action displays the **Edit Item** dialog, from where you can specify a **Name** and **Description** for the new **Layout** and add it to the default **My Items** category, or you can specify a new **Category**.  
  
     You can also specify any **Layout** you choose to be the default column layout configuration for the **Analysis Grid** viewer, by selecting the **Save Current As Default User Layout** item in the **Manage Layouts** submenu. If you modify your default user **Layout** configuration and you need to restore it to the original version, you can do so by selecting the **Load Default User Layout** item in the same submenu. However, if you need to restore the default **Layout** that ships with Message Analyzer, you can do so by selecting the **Restore Application Default Layout** item, which is also a **Manage Layouts** submenu item.  
  
 > [!NOTE]
 >  You can also save the settings of **Layouts** that you create for the **Grouping** viewer.  
  
-   **Pattern Expressions** — to save the settings of a custom Pattern Expression, first build one by using the features of  the **Pattern Editor**, the user interface for which displays when you click the **Create Pattern** button on the **Pattern Match** viewer after you open this viewer from the **New Viewer** drop-down list. When you are done using the **Quick** or **Free Form** tab to create your Pattern Expression, click the **Save Pattern** button on the **Pattern Editor** dialog toolbar to add your new Pattern Expression to the **My Items** category of the **AVAILABLE PATTERNS** list that appears in the **Pattern Match** viewer. This action also adds your new Pattern Expression to the **Message Analyzer Sequence Expressions** asset collection, which comprises a user Library that appears as the indicated patterns list. You also have the option to manage and share Pattern Expressions by selecting the **Manage Patterns** command from the **Pattern Match** drop-down list in the global Message Analyzer **Session** menu.  
  
-   **Trace Scenarios** — to save the settings of a custom **Trace Scenario**, first configure one from the **New Session** dialog, which displays when you click the **New Session** button on the Message Analyzer **Start Page**. From the dialog, you can specify the message providers you want to use in addition to the target host/s, filtering, viewer, and parsing level you want to use. You can even customize one of the built-in **Trace Scenarios** to your own design before saving your settings by clicking the **Save Scenario** button on the **ETW Providers** toolbar in the **New Session** dialog. When you save a customized **Trace Scenario**, it is automatically added to the **Message Analyzer Trace Scenarios** asset collection, which appears as the user Library in the **Select Scenario** drop-down list in the **New Session** dialog. Your new **Trace Scenario** and all its settings are stored in the **My Items** category of this drop-down under a subcategory name that you specify. As with all other Message Analyzer asset collections, you can manage and share **Trace Scenario** assets from the **Manage Trace Scenario** dialog, which displays when you click the **Manage Trace Scenarios** command in the **Select Scenario** drop-down list.  
  
<a name="BKMK_SavingOtherSettings"></a>   
## Saving Other Settings  
 Other items that you can save for Analysis Sessions consist of the following. This includes default settings that you specify in the global **Options** dialog that is accessible from the global Message Analyzer **Tools** menu:  
  
-   **Comments** — you can add one or more comments to any message that you choose in the **Analysis Grid** viewer. To add comments, you will need to display the **Comments** **Tool Window**, which is accessible from the **Windows** submenu of the global Message Analyzer **Tools** menu. Thereafter, you can specify a **Title** for each comment, an **Author** name and date-time, and of course the comment text itself. After you configure a comment, you have the option to edit or delete it. When you want to view comments that you previously configured in a set of trace results, you can perform a forward or backward search by clicking the **Next** and **Previous** buttons on the **Comments** tool bar, respectively. As you do this, the messages for which you configured comments are highlighted in the **Analysis Grid** viewer, so you can quickly return to commented messages of interest. Any comments that you specify are saved with the **Analysis Grid** viewer trace results, provided that you save the trace as a native .matp file.  
  
-   **Bookmarks** — you can add bookmark settings to any message that you choose in the **Analysis Grid** viewer. You can also add bookmarks to messages in the **Pattern Match** viewer. To add bookmarks, you will need to display the **Bookmarks** **Tool Window**, which is accessible from the **Windows** submenu of the Message Analyzer **Tools** menu. Thereafter, you can specify a bookmark **Name**, add a **Category** for a bookmark, and configure a color-coded **Flag** that indicates a user-defined condition. By selecting a bookmark message row in the **Bookmarks**  window, you can highlight the corresponding messages in the **Analysis Grid** viewer to quickly return to one or more book-marked messages of interest. Any bookmark settings that you specify are saved with **Analysis Grid** viewer trace results, providing that you save the trace as a native .matp file and that you save all messages. If you save selected messages only or a filtered message set, bookmarks are not saved in the trace file.  
  
-   **Time Shifts** — you have the option to save any **Time Shift** settings that you applied to a set of trace results. However, you must save your trace results data in the .matp file format. A **Time Shift** enables you to adjust for machine skew or time zone changes so that you can sync up two or more data sources.  
  
-   **Time Display** — you have the option to set the **Time Zone** and **Date and time format** that Message Analyzer will use for all displayed messages in any session where **Timestamps** are used. Formats consist of date and time, or time only. You can specify the **Time Display** option that you want on the **Display** tab of the global **Options** dialog, which is accessible from the Message Analyzer **Tools** menu.  
  
-   **Live Trace Message Buffer** — includes options for saving the message buffer **Size** limit and the **Contiguous Drop Percentage** rate for the PEF Runtime, which together specify the rate at which packets are dropped when the live buffer size setting is exceeded. You can change these settings in the **Live Trace Message Buffer** pane on the **General** tab of the **Options** dialog, which is accessible from the Message Analyzer **Tools** menu. If you change the default values for these options, you will automatically save them when you click **OK** to exit the **Options** dialog. These options are global in that they apply to all Live Trace Sessions.  
  
-   **Session Viewer Defaults** — Message Analyzer enables you to set the default viewer in which your message data will display, whether you are capturing data in a Live Trace Session or if you are loading data into Message Analyzer through a Data Retrieval Session. The **Default Viewer** drop-down list on the **Profiles** tab of the **Options** dialog enables you to make a default selection from among all data viewers that are available to Message Analyzer. The **Default Viewer** drop-down list contains the same data viewers that exist in the **New Viewer** drop-down list on the global Message Analyzer toolbar and in the **Session Explorer** **Tool Window** context menu, with the exception of a default **Chart** item (without additional **Layouts**) that exists in the indicated **Default Viewer** drop-down list and the **Start With** drop-down list in the **New Session** dialog. The data viewer that you choose as the default is saved when you click **OK** to exit the **Options** dialog. The selected viewer will then be used by default for any session that you run, unless you specifically change it from the **Start With** drop-down menu of the **New Session** dialog, in which case, the selected viewer applies to the current session only.  
  
-   **Text Log Files** — if you select an item from the **Default text log configuration** drop-down list on the **Text Log Files** pane of the **General** tab in the **Options** dialog and save it by clicking **OK** to exit the dialog, it becomes the default configuration file for all text logs from which you load data into Message Analyzer. This setting is saved across Message Analyzer restarts.  
  
-   **Binary Values** — by selecting one of the following options on the **Display** tab of the **Options** dialog, you determine the default format in which Message Analyzer displays binary values, for example, in the **Payload** field of the **Details** **Tool Window**:  
  
    -   **Display as ASCII**  
  
    -   **Display as Hex**  
  
    -   **Display as Decimal**  
  
 > [!NOTE]
 >  This setting is persisted across Message Analyzer restarts, just as all settings that you specify in the **Options** dialog are persisted.  
  
-   **Decryption Options** — you can add one or more server certificates and passwords in the **Certificates** pane on the **Decryption** tab of the **Options** dialog, to enable Message Analyzer to decrypt traffic that is encrypted with the Transport Layer Security (TLS) or Secure Sockets Layer (SSL) security protocols. You automatically save these items in the Message Analyzer certificate store when you click the **OK** button to exit the **Options** dialog. Thereafter, you can load a saved trace file or start a Live Trace Session to retrieve the target encrypted traffic and Message Analyzer attempts to decrypt as many messages as possible. Server certificates are saved across Message Analyzer restarts; however, for security purposes, you must manually re-enter passwords after a Message Analyzer restart, prior to decrypting a trace.  
  
-   **Session results** — when you save the results of an **Analysis Session**, you have the option to save all session messages, subsets of a message collection that result from the application of various data manipulation items such as **Viewpoints** and view **Filters**. The **Save/Export Session** dialog that is accessible by clicking the **Save** item in the global Message Analyzer **File** menu provides options to save data in this manner, which includes the **All Messages**, **Filtered Messages**, or **Selected Messages** options. For example, a subset of a message collection might reflect the application of a **Time Filter** or view **Filter**, which you would save under the **Filtered Messages** option. You can also save specifically selected messages with the **Save Selected Messages** context menu command in the **Analysis Grid** viewer. You can save your session results in the .matp (parsed) or .cap file format only.  
  
 > [!NOTE]
 >  If you save your trace results as a .cap file, **Comments**, **Bookmarks**, and **Time Shift** settings are not saved.  
  
-   **Parsing Levels** — if you set a **Parsing Level** when configuring a **New Session** that you run, thereafter when you save the message set that displays in a data viewer such as the **Analysis Grid**, the applied **Parsing Level** and its effects will be reflected in the saved file. Note that you must use the **Open File** feature on the **Start Page** or the **Open** and **From File Explorer** commands on the **File** menu, rather than loading one or more files through a **New Session**, to retrieve the data with the original **Parsing Level** applied.  
  
## See Also  

[Applying and Managing Filters](applying-and-managing-filters.md)   
[Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md)   
[Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md)   
[Applying and Managing Viewpoints](applying-and-managing-viewpoints.md)   
[Using and Managing Color Rules](using-and-managing-color-rules.md)   
[Managing Chart Viewer Layouts](managing-chart-viewer-layouts.md)   
[Applying and Managing Analysis Grid Viewer Layouts](applying-and-managing-analysis-grid-viewer-layouts.md)   
[Using the Pattern Editor](using-the-pattern-editor.md)   
[Creating and Managing Custom Trace Scenarios](creating-and-managing-custom-trace-scenarios.md)   
[Setting the Session Parsing Level](setting-the-session-parsing-level.md)   
[Parsing Input Text Log Files](message-analyzer-tutorial.md#BKMK_ParsingLogFiles)   
[Using the Field Chooser](using-the-field-chooser.md)   
[Saving Message Data](saving-message-data.md)   
[Annotation Windows](annotation-windows.md)   
[Setting Time Shifts](setting-time-shifts.md)   
[Applying a Time Filter to Session Results](applying-a-time-filter-to-session-results.md)