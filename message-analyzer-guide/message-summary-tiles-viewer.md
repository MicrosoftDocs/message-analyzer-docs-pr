---
title: "Message Summary Tiles Viewer | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8c0cd05-4e91-457a-a841-1c3c12be11ff
caps.latest.revision: 20
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Message Summary Tiles Viewer
Message Analyzer provides the **Message Summary Tiles** viewer, which is currently a preview feature. If you wish to use the **Message Summary Tiles** viewer, you will need to select its check box on the **Features** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu, and then restart Message Analyzer. It will then be available for selection in the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
## Message Summary Tiles Viewer Overview  
 The **Message Summary Tiles** data viewer summarizes important data for any set of trace results. It provides a high-level overview of major trace statistics and important values that you can examine at-a-glance to obtain a quick top-level analysis of results. The default configuration of this viewer contains six tiles of summary information, however, you can configure your own summary tiles by selecting from the preset tile types. Some of the preset tile types require custom configuration; for example, the **Field** type, for which you specify fields, properties, annotations, or other values that you select from the **Field Chooser** **Tool Window**. Other preset tile types that you must custom configure are the **Filter** and **Sequence** types, which require you to select a predefined asset type or create your own to add them to the tile configuration. The default configuration of the **Message Summary Tiles** viewer is shown in the figure that follows.  
  
 ![Message Summary Tiles viewer](../messageanalyzer_content/media/fig48-message-summary-tiles-viewer.png "Fig48-Message Summary Tiles viewer")  
  
 **Figure 48:  Message Summary Tiles viewer**  
  
 **Isolating Messages for Analysis**   
Each of the default tiles contain lines of data that are labeled according to predefined fields and you can drill down into the messages that are associated with the details that display on several tiles. You can do this by double-clicking any line of data to display the associated messages in a separate **Analysis Grid** viewer instance that contains only those messages, for further inspection. For example, you might double-click the **Validation** label in the **Diagnostics** tile to view messages for which validation errors occurred, as these can indicate that the messages of a particular protocol had field values that were out of tolerance or did not meet other specifications when evaluated during the Message Analyzer Runtime parsing process. The only exceptions to double-clicking tile labels to drill down is the **Stats** tile, which always displays all messages whenever you click anywhere in this tile, and the **ResponseTime** tile, which does not currently respond to double-clicking.  
  
## Understanding the Default Summary Tiles  
 The functions of the default summary tiles are described as follows:  
  
-   **Stats** — provides an indication below the tile name, of the overall number of messages that were evaluated according to predefined criteria; below that is an overview of the following general data for the current set of trace results:  
  
    -   **First->Last** — indicates the duration in milliseconds (ms) of the current trace.  
  
    -   **Last Time** — provides the timestamp of the last message in the current trace.  
  
    -   **Last Module** — provides the name of the last module in the last message of the current trace.  
  
    -   **Last Source** — specifies the source IP address associated with the last message in the current trace.  
  
    -   **Last Destination** — specifies the destination IP address associated with the last message in the current trace.  
  
    > [!NOTE]
    >  Double-clicking anywhere on this tile displays all trace messages in a new **Analysis Grid** viewer instance.  
  
-   **Diagnostics** — provides an indication below the tile name, of the overall number of messages that were evaluated according to predefined criteria; below that is an overview of the following diagnostic message data for the current set of trace results:  
  
    -   **Application** — specifies the number of messages in the current trace that contain **Application** type diagnostic errors.  
  
    -   **Custom** — an alternate type of diagnostic message. Currently a placeholder.  
  
    -   **Insufficient Data** — specifies the number of messages in the current trace that contain **Insufficient Data** type diagnostic errors.  
  
    -   **Parsing** — specifies the number of messages in the current trace that contain **Parsing** type diagnostic errors.  
  
    -   **Validation** — specifies the number of messages in the current trace that contain **Validation** type diagnostic errors.  
  
     ___________________\_  
  
     **More Information**   
     **To learn more** about the meaning of diagnostic messages, see the [Diagnosis Category](../messageanalyzer_content/filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.   
    ___________________\_  
  
-   **Source** — provides an indication below the tile name, of the total number of values that were evaluated in the top 5 according to predefined criteria; below that is the message count of the specific sender IP addresses with the top 5 highest message volumes for the current set of trace results.  
  
-   **Destination** — provides an indication below the tile name, of the overall number of values that were evaluated in the top 5 according to predefined criteria; below that is the message count of the specific recipient IP addresses with the top 5 highest message volumes for the current set of trace results.  
  
-   **Module** — provides an indication below the tile name, of the overall number of values that were evaluated in the top 5 according to predefined criteria; below that is the message count for the specific protocols or modules with the top 5 highest message volumes for the current set of trace results.  
  
-   **ResponseTime** — provides an indication below the tile name, of the overall value count for the evaluations performed according to predefined criteria. Below that are the following **ResponseTime** statistics for operations in the current set of trace results that specify the difference in milliseconds between the time a client request message is sent to a server and the time at which the first server response message is received by the client:  
  
    -   **First Value** — specifies the **ResponseTime** for the *first* operation that was detected in the current set of trace results.  
  
    -   **Last Value** — specifies the **ResponseTime** for the *last* operation that was detected in the current set of trace results.  
  
    -   **Minimum Value** — specifies the minimum **ResponseTime** value that was detected in the current set of trace results.  
  
    -   **Maximum Value** — specifies the maximum **ResponseTime** value detected in the current set of trace results.  
  
     **Note** These statistics can quickly alert you when there is a problem with poorly performing servers, in terms of responses to client requests.  
  
> [!TIP]
>  For additional summary information about any of the default summary tiles, hover over the number just below the tile name with your mouse to display a popup window that specifies related evaluation data.  
  
## Modifying the Message Summary Tiles Display  
 You have the option to modify any of the default summary tiles or you can create new tiles by using the **Tile Config** editor to create your own data summary configurations. You can also **Save** your modifications as a Message Summary Viewer Configuration (\*.msvcfg) file, that you can **Load** back into Message Analyzer any time thereafter for analysis purposes. You can access the **Tile Config** editor (and the **Load** and **Save** commands) in the Message Analyzer global **Session** menu whenever the **Message Summary Tiles** viewer is displayed. The editor enables you to specify settings such as the level to which **Top Values** will be evaluated; the fields, annotations, or properties you want to use for a data summary through access to the **Field Chooser** window; the tile position in the display, tile **Foreground** and **Background** colors, a textual **Description**, and so on.  
  
 **Preset Tile Types**   
The **Tile Config** editor provides a number of preset tile types, which include the following:  
  
-   **Stats** — select this preset type if you want to display predefined general statistics in your summary tile. Note that this tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
-   **Diagnostics** — select this preset type if you want to display predefined diagnostics information in your summary tile. This tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
-   **Source** — select this preset type if you want to add predefined **Source** computer information to your summary tile. Note that this tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
-   **Destination** — select this preset type if you want to add predefined **Destination** computer information to your summary tile. This tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
-   **Module** — select this preset type if you want to add other **Module** information to your summary tile. Note that this tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
-   **ResponseTime** — select this preset type if you want to add predefined **ResponseTime** information to your summary tile. This tile is included in the default configuration of the **Message Summary Tiles** viewer.  
  
> [!NOTE]
>  If you want to add other information based on a specific message field, click the **+** button to display a **(Field)** placeholder item in the **Field Tiles** list, the name for which will change when you select a particular field that you want from the **Field Chooser** **Tool Window**. You can open **Field Chooser** by first selecting the **(Field)** item and then clicking the **Click to Set** button.  
  
 ______________\_  
  
## See Also  
 [Field Chooser Tool Window](../messageanalyzer_content/field-chooser-tool-window.md)