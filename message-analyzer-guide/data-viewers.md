---
title: "Data Viewers | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 289bec9d-1cbe-413c-922b-7f0ede64904d
caps.latest.revision: 65
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Data Viewers
In any Analysis Session, Message Analyzer enables you to use data viewers to present message data in various formats to create unique analysis perspectives. You can choose data viewers during session configuration in the **New Session** dialog prior to starting a session, or afterwards in an Analysis Session where you have displayed session results. Some of these are default viewers, while others are preview feature viewers that you can enable,  try out, and provide feedback to Microsoft to initiate possible improvements. Several viewers can utilize numerous **Layouts** that change the  default view of data and provide advantages such as the following:  
  
-   Display different message field data to target   a specific analysis environment.  
  
-   Change the presentation format to summarize important data at a high-level and provide immediate insights into possible issues.  
  
-   Drive important information to top-level for easy viewing or create a window into hidden but significant data that otherwise might be difficult or laborious to achieve through manual methods in a large data set, if even possible at all.  
  
-   Perform calculations that expose interesting statistics, extract key information, or enhance the analysis process by utilizing custom    global property and annotation values.  
  
 The data viewers, the **Layouts** that apply to specific data viewers, and the graphic visualizer **Layouts** for the **Chart** viewer are all described in this section, along with related functional descriptions, how to launch these data viewers, how to display different viewer **Layouts** in those viewers that employ them, and how to use these components to solve diagnostic problems.  
  
 The table that follows describes the default data viewers and the preview feature viewers that Message Analyzer provides and also identifies the viewers that employ **Layouts** along with the asset collection Libraries in which they exist.  
  
### Table 11. Message Analyzer Data Viewers and Layouts  
  
||||||  
|-|-|-|-|-|  
|**Viewer Name**|**Description**|**Layouts**|**Viewer Type***|**Asset Collection**|  
|[Analysis Grid](analysis-grid-viewer.md)|The primary analysis surface that consists of a default tree grid display containing a default column layout with expandable parent and child message nodes that expose top-level transactions/Operations and message origins, respectively, along with message details, in a tree-view structure.|Yes — **Layouts** drop-down list above Filter text box.|**Default**|**Message Analyzer View Layouts**|  
|[Grouping](grouping-viewer.md)|Enables you to organize your traffic into summary hierarchies based on **Grouping** viewer **Layouts** that contain predefined message field groups. These groups exist in nested configurations that create focus on specific data by extracting it from a set of trace results and exposing it at different levels in the group hierarchy.<br /><br /> Enables you to drill down into important data while at the same time interactively correlate  the group data with the **Analysis Grid** viewer display through group selection.|Yes — **Layouts** drop-down list on the **Grouping** viewer toolbar.|**Default**|**Message Analyzer Grouping View Layouts**|  
|[Pattern Match](pattern-match-viewer.md)|Enables you to detect message behaviors, patterns, or repeating value sequences within a message collection, based on execution of  a predefined or custom-designed OPN **Pattern** expression. Also provides a summary analysis of **Matches**, **Matched Instances** details, and the correlated **Messages**.|None|**Default**|**Message Analyzer Sequence Expressions**|  
|[Gannt](gantt-viewer.md)|Consists of a graphic visualizer presentation that provides a quick  view of message dispersion across a trace timeline that is presented as color-coded protocol module identifiers, with source/destination address message pairs in the y-axis orientation and timestamps in the x-axis orientation.|None|**Preview**|N/A|  
|[Chart](chart-viewer-layouts.md)|Defines a generic category of data viewer that uses different built-in **Layouts** that each present data with a single visualizer component such as a grid, bar element, pie-chart, or timeline component with chart formulas applied to create a targeted analysis context. **Layouts** typically consist of top-level message summaries that provide a high-level overview of the data in a set of trace results.|Yes — **Layouts** drop-down enabled in the **Session** menu, only while a **Chart** is displayed. Also accessible from the **New Viewer** drop-down list.|**Default**|**Message Analyzer Chart View Layouts**|  
|[Interaction](interaction-viewer.md)|A swim lane diagram along with several other viewing formats that provide different graphic presentations of the computer nodes and endpoints that exchanged messages within the time boundaries of a trace.<br /><br /> Also correlates the IP conversations that took place for the protocols or modules that participated in message exchanges and provides message summary details in hover-over pop-ups.|None|**Preview**|N/A|  
|[Message Summary Tiles](message-summary-tiles-viewer.md)|Provides a high-level overview of major trace statistics and important values for quick top-level analysis of results.|None|**Preview**|N/A|  
|[Message Summary Lists](message-summary-lists-viewer.md)|Provides a high-level overview of major trace statistics and key data points for quick top-level analysis of results.|None|**Preview**|N/A|  
|[PerfMon](perfmon-viewer.md)|Enables you to view data from Microsoft Performance Monitor logs in the *.blg file format. You can view this data in Message Analyzer similarly to the way it appears in Performance Monitor while taking advantage of Message Analyzer's data selection, organization, and analysis capabilities.|None|**Preview**|N/A|  
|[Charts (Deprecated)](charts-deprecated.md)|Contains the old Charts that existed prior to Message Analyzer v1.4. For example, you can still display the **Protocol Dashboard** viewer and others in their original configuration of visualizer components.|None|**Preview**|**Message Analyzer Charts**|  
  
 *A Default viewer is coded into the Message Analyzer UI and cannot be disabled the way a preview feature can be disabled or enabled.  
  
> [!IMPORTANT]
>  To use any preview feature, you must enable it on the **Features** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. To enable a feature, place a check mark in the check box next to the feature name and then restart Message Analyzer. To disable a feature, remove the check mark so that it will no longer be accessible after the next Message Analyzer restart, that is, until you re-enable it once again.  
  
> [!TIP]
>  You can  specify any data viewer as the default for all sessions by choosing one in the **Default Profile** pane on the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu.  
  
<a name="BKMK_CommonDataViewers"></a>   
## Chart Viewer Layouts Library  
 The **Chart** viewer **Layouts** Library exists in the **Message Analyzer Chart View Layout** asset collection and is accessible from the **Chart** drop-down list that displays in the **New Viewer** drop-down list; this list is accessible from the locations specified in [Session Data Viewer Options](session-data-viewer-options.md).  Each **Chart** viewer **Layout** that exists in the specified Library contains a single data visualizer component that typically provides a top-level data summary that you can view for a quick high-level assessment of data. The data visualizers consist of grid, bar element, pie-chart, and timeline components and can display most types of data that you need to present. The **Layouts** exist in the following categories, which are accessible from the **Manage Chart Layout** dialog only while a **Chart** viewer is displayed. You can locate this dialog from the global Message Analyzer **Session** menu by highlighting **Chart**,  **Layout**, and then clicking the **Manage** item in the **Manage Layouts** drop-down list.  
  
-   **HTTP**  
  
-   **General**  
  
-   **Network**  
  
-   **Netlogon**  
  
-   **Common**  
  
-   **File Sharing**  
  
 The **Chart** viewer **Layouts** that exist in these categories are described in the [Chart Viewer Layouts](chart-viewer-layouts.md) topic. Note that you can also create your own **Layouts** to contain a data visualizer that you choose and  data formulas that you configure, and you can create your own categories in which to place them under the default **My Items** top-level category in the **Layouts** Library.  
  
---  
  
 **More Information**   
 **To learn more** about how to create **Chart** viewer **Layouts**, see [Extending Message Analyzer Data Viewing Capabilities](extending-message-analyzer-data-viewing-capabilities.md).  
**To learn more** about Message Analyzer assets, see [Managing Message Analyzer Assets](managing-message-analyzer-assets.md).  
---  
  
## See Also  
 [Chart Viewer Layouts](chart-viewer-layouts.md)