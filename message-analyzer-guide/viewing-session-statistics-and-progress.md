---
title: "Viewing Session Statistics and Progress | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a11aaba-4760-4548-9cb3-8ee67a7e8b2d
caps.latest.revision: 26
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Viewing Session Statistics and Progress

Message Analyzer provides a robust set of monitoring facilities such as progress indicators and various types of session statistics that include hover-over tool tips. For example, Message Analyzer enables you to view the progress of various message retrieval operations such as the following:  
  
-   Data loaded through the **Open** feature on the Message Analyzer **Start Page**.  
  
-   Data loaded from the **Recent Files** feature from the Message Analyzer global **File** menu.  
  
-   Data loaded through a Data Retrieval Session.  
  
-   Data captured in a Live Trace Session.  
  
Message Analyzer also enables you to view progress indications for multiple concurrent sessions that load data at the same time. You can also observe the progress of message processing during data manipulation operations, which includes the application and removal of view **Filters**, **Groups**, **Viewpoints**, **Pattern Matches**, **Layouts**, and **Time Filters**. In addition, you can hover over any top-level session node in **Session Explorer** with your mouse and view the message count for the associated session in a tooltip. You can also hover over any session viewer node in **Session Explorer** **Tool Window** and display a tooltip that indicates the analytical assets that are applied to that viewer.  
  
## Indicating Progress and Statistics  

 Visual progress indications and statistics for the previously described Message Analyzer operations are displayed in the **Session Explorer** window. To provide these indications when loading data, capturing data, or manipulating data, **Session Explorer** utilizes the following progress and statistics indicator components:  
  
-   **Progress bar control** — provides the following types of progress indications:  
  
    -   **Relative** — displays a continuous solid bar that propagates from left to right when the number of messages in a message source is known, for example, when loading data from .cap, .pcap, .matu, and .log files.  
  
    -   **Ambiguous** — displays a short block that scrolls across the control in marquee fashion when the number of messages cannot be determined, for example, when capturing data live or when loading data from .etl, .matp, .evtx, .tsv, and .csv files.  
  
-   **Relative progress label** — to the right of each progress bar control in a **Session**, a parenthetical label can provide numerical percent-complete statistics for an operation. Percent-complete values display only when the total number of messages in a message source is known, which is therefore considered a *relative* type progress indication.  
  
-   **Session node label** — to the right of each **Session** node in **Session Explorer**, there is a parenthetical label that is populated with the total number of messages processed and available to the current **Session**. If you hover your mouse over a **Session** node, the following tool tip is displayed:   
    *“The value represents the number of messages currently available for this session”*.  
  
-   **Viewer node label** — to the right of the **Session Explorer** node that contains the data viewer that you specified when starting a Data Retrieval Session or Live Trace Session, there is a parenthetical label that indicates the number of parsed messages that are available to the session viewer that you specified, for example, the **Analysis Grid** or **Gantt** viewer. Note that when you load data through the **Open** feature, the **Analysis Grid** viewer displays by default, unless you have changed the default viewer in the **Default Viewer** pane on the **Profiles** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. Also, if you hover your mouse over a viewer node, the following tool tip is displayed:   
    *“The value represents the number of messages currently available for this view”*.  
  
-   **Hover-over tool tips** — as indicated earlier, tooltips that display when you mouse-hover over any top-level session node or any session viewer sub-node in **Session Explorer**, provide a quick indication of session message count and the analytical assets that you have applied to a viewer, respectively. Applied assets can include a **Viewpoint**, **Viewpoint Filter**, view **Filter**, and/or a **Message Range Filter**.  
  
 > [!NOTE]
 >  Session viewer tabs also display the same tool tip information when you hover over them with your mouse.  
  
-   **Session color coding** — each top-level session node and related session viewer subnodes in **Session Explorer** are color-coded for quick identification. Different sessions are identified with a different colored dot, which helps to automatically organize your session data viewers.  
  
 > [!TIP]
 >  Session viewer tabs also contain associated colored dots, to enable you to quickly correlate all viewers of the same session.  
  
> [!NOTE]
>  **Session Explorer** also contains different **Session** node icons that indicate the type of session to which progress statistics apply, for example, a Live Trace Session versus a Data Retrieval Session. In addition, icons are added to the right side of session viewer subnodes to indicate the application of an analytical asset. For example, a funnel shaped glyph indicates when a **Session Filter** or view **Filter** was applied to the messages in your Live Trace Session or Data Retrieval Session.  
  
## Observing Progress Indicator Behaviors  

 The behavior of **Session Explorer** progress indicators varies depending on the tasks you are performing, as follows:  
  
 **Loading parsed messages** — when you load data from a .matp file in a Data Retrieval Session, the progress bar might display an *ambiguous* progress indication for larger files, by scrolling a block across the control in marquee fashion, along with the following simultaneous indications:  
  
-   **Session** node indicator above the progress bar control — shows the total number of messages processed in the session.  
  
-   **Viewer** indicator below the progress bar control — shows the number of parsed messages available in the specified data viewer for further processing.  
  
> [!NOTE]
>  Because a .matp file is already parsed, it should load very fast, and in this case a progress indication might not display.  
  
 **Loading unparsed messages** — when you load data from a .matu file in a Data Retrieval Session or through the **Open** and **Recent Files** features on the **Start Page**, the progress bar control displays a continuous solid bar that propagates from left to right, while providing the identical indications described in the previous list, consisting of the total number of messages processed (above the control) and the number of parsed messages available in the viewer (below the control). It also provides progress as a percent-complete value, which indicates the number of messages processed/parsed out of the total message count in the .matu file.  
  
 **Capturing data live** — when you are capturing messages in a Live Trace Session, the progress bar control displays a scrolling block across the control (until such time that you stop the Live Trace Session) along with simultaneous indications of the number of captured messages (above the control) and the total number of parsed messages that are available in the specified viewer (below the control).  
  
> [!NOTE]
>  **Session Total** and **Available** message indicators are also provided in labels on the Status Bar of the Message Analyzer UI and reflect the identical values that display in the **Session** node and viewer node labels, respectively.  
  
## Manipulating data  

 Progress indications are also displayed whenever you apply or remove view **Filters**, **Groups**, **Viewpoints**, **Pattern Matching**, view **Layouts**, and **Time Filters** to or from a set of displayed messages, respectively, or when you toggle **Operations** from the **Viewpoints** drop-down list on the Message Analyzer Filtering toolbar. Progress indications are also provided when you sort columns. The progress indications that display for each of these data manipulation operations consists of:  
  
-   A continuous solid progress bar that propagates from left to right.  
  
-   A corresponding relative progress indication that displays a percent-complete value, along with an operation indicator such as *Filtering*, *Sorting*, *Applying Viewpoint*, and so on.  
  
-   The number of messages processed and available to the specified viewer based on the applied data manipulation criteria.  
  
> [!NOTE]
>  The **Diagnostics** **Tool Window** also contains its own progress indicator; however, it usually activates only when a large set of trace results is being scanned and diagnosis messages are being aggregated into summaries that thereafter will display in this tool.  
  
 You can also apply simultaneous data manipulation operations across multiple sessions and observe progress indications that apply to each session. However, if you apply multiple operations in the same session viewer, the order in which operation indicators display is determined by a preset order of precedence that Message Analyzer applies, regardless of the sequence in which you start data manipulation operations.  
  
## See Also  

[Session Explorer Tool Window](session-explorer-tool-window.md)