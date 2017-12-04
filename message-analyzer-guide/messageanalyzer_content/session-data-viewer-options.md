---
title: "Session Data Viewer Options | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 182fd61e-020b-4fe8-afb1-8c2d398aca05
caps.latest.revision: 36
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Session Data Viewer Options
After you use the **New Session** dialog to configure either a Data Retrieval Session that points to the input files that contain the data you want to work with, or a Live Trace Session that you are ready to run, you can choose one of the data viewers previously described in the [Data Viewers](../messageanalyzer_content/data-viewers.md) section to display your data. You can also simply allow Message Analyzer to present your session results in the default **Analysis Grid** viewer, unless you have already set another type of data viewer as the default in the **Options** dialog, as described in [Setting the Default Session Viewer](../messageanalyzer_content/session-data-viewer-options.md#BKMK_SetDefaultViewer). If you want to choose a data viewer for a session, select one from the common **Start With** drop-down list in the **New Session** dialog prior to starting the session. After you click the **Start** button in the **New Session** dialog, Message Analyzer immediately begins to retrieve or capture data and display it in the chosen viewer.  
  
## Using the Data Viewing Options  
 The data viewer that appears in the text box portion of the **Start With** combo box when you open the **New Session** dialog, is the default viewer that is set in the global **Options** dialog; this dialog is accessible from the global Message Analyzer **Tools** menu. At any time, you can specify the default data viewer of your choice for all sessions, as described in [Setting the Default Session Viewer](../messageanalyzer_content/session-data-viewer-options.md#BKMK_SetDefaultViewer), although you still have the option to choose a different one prior to starting a new session. However, the default data viewer setting will persist in each subsequent reopening of the **New Session** dialog, which provides you with the same option again to use the default viewer or choose another one. In addition, after session results display in the viewer you specified in session configuration, you have the option to display data in any of the other available data viewers to enhance data analysis by selecting them from the **New Viewer** drop-down list, as described in [Locating Data Viewers for Selection](../messageanalyzer_content/session-data-viewer-options.md#BKMK_DataViewerSelectionLocations). The data viewers that are available in Message Analyzer are described in the [Data Viewers](../messageanalyzer_content/data-viewers.md) section.  
  
> [!NOTE]
>  If you specify additional data viewers for the results of a particular Data Retrieval Session or Live Trace Session, Message Analyzer will automatically repopulate the original data set to the additional viewers in the same session.  
  
<a name="BKMK_DataViewerSelectionLocations"></a>   
## Locating Data Viewers for Selection  
 You can specify any of the available Message Analyzer data viewers from the common data viewer Library that is accessible in each of the following locations:  
  
-   **Data Retrieval Session** configuration — provides data viewer selections from the common **Start With** drop-down list in the **New Session** dialog during session configuration.  
  
-   **Live Trace Session** configuration — provides data viewer selections from the common **Start With** drop-down list in the **New Session** dialog during session configuration.  
  
-   **New Viewer** — a drop-down list that is accessible from the following locations during an Analysis Session:  
  
    -   Global Message Analyzer **Session** menu, but only when a **Chart** is currently being displayed.  
  
    -   Global Message Analyzer toolbar.  
  
    -   The **Session Explorer** **Tool Window** context menu that is accessible by right-clicking any session node or viewer node in the **Session Explorer** window. The context menu provides access to the **New Viewer** drop-down list, from where you can choose either a data viewer or a **Chart** viewer **Layout**.  
  
     The **New Viewer** drop-down list provides the same data viewer selections that are accessible from all the previously described locations. The different data viewers that you specify from the **New Viewer** drop-down list work with Live Trace Session or Data Retrieval Session *results* only, as previously indicated.  
  
 Specifying a different data viewer typically adds a separate viewer tab that contains an alternate data presentation format for the specific session that you choose, while retaining all other data viewers already in place for the chosen session. Note that the different data viewers that you specify for the *results* of a Live Trace Session or Data Retrieval Session create various data presentations, but do not modify the original contents of the trace or loaded message collection.  
  
<a name="BKMK_SetDefaultViewer"></a>   
## Setting the Default Session Viewer  
 You have the option to set a default data viewer for all sessions by selecting one from the **Default Viewer** drop-down list in the **Default Profile** pane on the **Profiles** tab of the global **Options** dialog. You can access this dialog from the global Message Analyzer **Tools** menu. Message Analyzer ships with the **Analysis Grid** as the default viewer for all sessions, but you can change to another viewer to customize your data analysis environment, as follows:  
  
-   **Global mode** — you can change the default data viewer that will be used by all sessions, from the **Analysis Grid** factory setting to any viewer that you choose in the **Default Viewer** drop-down menu in the **Default Profile** pane, as previously described.  
  
-   **Session specific mode** — you have the option to use a data viewer of choice whenever you start a session, regardless of what the default setting is, by clicking the **Start With** drop-down list in the **New Session** dialog and selecting a viewer.  
  
> [!NOTE]
>  Because the **Details**, **Field Data**, **Message Data**, **Message Stack**, **Decryption**, **Diagnostics**, and other tool windows — accessible from the **Windows** submenu of the global Message Analyzer **Tools** menu — are either message-specific windows (respond to message selection) or session-specific (snap-to data viewer selection) windows, they depend upon and interact with the data viewers. As a result, you cannot specify one of these windows to start a Live Trace Session or Data Retrieval Session.  
  
> [!TIP]
>  When you have session results data for which you have specified multiple data viewers, for example, the **Grouping** and the **Analysis Grid** viewers, you can bring the message data contained in a particular viewer into focus by clicking its associated node in the **Session Explorer** window, or by selecting its associated viewer tab.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about Message Analyzer data windows that interact with data viewers, see the [Tool Windows](../messageanalyzer_content/tool-windows.md) topic.  
**To learn more** about how to configure and save custom  **Chart** viewer **Layouts**, see [Configuring Chart Viewer Layouts](../messageanalyzer_content/configuring-chart-viewer-layouts.md).   
___________________\_