---
title: "Diagnostics Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e62b917-03c5-4c23-8c04-c7accedf6059
caps.latest.revision: 26
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Diagnostics Tool Window
In troubleshooting scenarios, quick access to diagnostic message information can help you to rapidly identify the root cause of an issue. However, diagnosis messages are typically embedded within individual captured messages, which can make them very difficult to find. Moreover, there can be multiple diagnosis messages within individual captured messages and the same diagnosis message might appear in multiple captured messages. When a diagnosis message is associated with either a top-level parent message or a child (origins tree) message in the **Analysis Grid** viewer, Message Analyzer provides an initial indication of the diagnosis message at the top-level. This means that even when a diagnosis message is associated with a child message, the diagnosis message *indication* is bubbled up to a top-level parent message, which is beneficial to analysis. However, this display configuration still requires you to go through some manual expansion of message nodes to get at the diagnosis message/s of interest.  
  
## Exposing Diagnosis Messages  
 Message Analyzer has several data manipulation features that you can use to expose diagnosis messages, which include **Grouping** and sorting the **DiagnosisTypes** column in the **Analysis Grid** viewer, but there are some disadvantages in using these techniques. When you sort the **DiagnosisTypes** column to bubble up diagnostic messages that occurred in a trace, or **Group** the column to organize diagnosis messages according to their **DiagnosisType**, you can lose the context of the original surrounding messages, which can often call attention to where or why certain issues occurred. As an alternative to these techniques, you can utilize the **Diagnostics** **Tool Window**, which flips the relationship of captured-to-diagnosis messages by making diagnosis messages the focus. This enables you to view diagnosis messages independent of the **Analysis Grid** viewer without having to expand message nodes to find them, while at the same time driving selection of parent messages in the **Analysis Grid** viewer that contain the diagnosis messages. You can also drive and synchronize the display of parent message details in other **Tool Windows** through selection of diagnosis messages in the **Diagnostics** window, as described ahead.  
  
> [!IMPORTANT]
>  The **Diagnostics** window is a preview feature. If you want to use it, you will need to select it on the **Features** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu. You will then need to restart Message Analyzer. Thereafter, the **Diagnostics (Preview)** window will appear in the **Windows** submenu that is accessible from the global **Tools** menu.  
  
## Enhancing Diagnostic Capabilities  
 The **Diagnostics** window is a session-specific and dockable window that simplifies the means of locating and analyzing embedded diagnosis messages that might normally be hard to find. It summarizes the different types of diagnosis messages in a selected session, which includes **Application**, **Validation**, **InsufficientData**, and **Parsing** errors. It also provides other information such as **Module**, **Count**, and diagnosis **Message** text, to assist your analysis process. By making this information quickly accessible and enabling you to associate other message details, the **Diagnostics** window enhances your troubleshooting experience because you can:  
  
-   Focus on diagnosis messages only.  
  
-   View a summary of diagnosis message group counts.  
  
-   Synchronize diagnosis message selection with the top-level parent messages in the **Analysis Grid** viewer.  
  
-   Drive the display of data in the following **Tool Windows**:  
  
    -   Message details in the **Details** **Tool Window**.  
  
    -   Hexadecimal field or message data in the **Message Data** **Tool Window**.  
  
    -   Message selection in the **Message Stack** **Tool Window**.  
  
> [!NOTE]
>  The **Diagnostics** window drives message selection in the **Analysis Grid** viewer, but the **Analysis Grid** does not drive diagnosis message selection in the **Diagnostics** window.  
  
## Viewing Diagnostic Data  
 The **Diagnostics** window contains four sortable columns that display diagnosis message information as follows:  
  
-   **Type** — specifies the type of diagnosis message, such as **Application**, **Validation**, **InsufficientData**, or **Parsing**.  
  
-   **Module** — specifies the name of the module or protocol for the parent message that contains the diagnosis message.  
  
-   **Message** — specifies the descriptive text of the diagnosis message.  
  
-   **Count** — specifies the number of parent messages in the **Analysis Grid** viewer that contain the selected diagnosis message.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the meaning of diagnosis messages, see the [Diagnosis Category](../messageanalyzer_content/filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.  
___________________\_  
  
## Using the Context Menu Commands  
 The **Diagnostics** window also contains a context menu that enables you to execute the following commands to accomplish the indicated tasks:  
  
-   **Ignore Selected Modules** — removes all diagnosis messages from the **Diagnostics** window display that match the module of the selected diagnosis message, so you can focus on the diagnosis messages of other modules.  
  
-   **Ignore Selected Messages** — removes all selected diagnosis messages from the **Diagnostics** window display so you can focus on specific diagnosis messages.  
  
    > [!NOTE]
    >  The toolbar of the **Diagnostics** window has an **Ignore** drop-down list that also contains the two previously described command functions. In addition, you can click the **Reset** button on the toolbar to restore all ignored items, as described next.  
  
-   **Reset Ignored Messages** — restores all messages or modules that were previously ignored.  
  
-   **Open Selected Messages** — displays the top-level parent messages (including origins) for all selected diagnosis messages in a separate **Analysis Grid** viewer tab.  
  
    > [!NOTE]
    >  The toolbar of the **Diagnostics** window contains an **Open** button that enables you perform the same function as **Open Selected Messages**.  
  
-   **Copy Selected Rows** — copies the data for the selected rows to the Clipboard.  
  
-   **Copy \<columnName>** — copies the data in a selected column for a selected diagnosis message to the Clipboard.  
  
## Displaying the Diagnostics Tool Window  
 You can open the **Diagnostics** **Tool Window** by selecting the **Diagnostics (Preview)** item from the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu. As indicated earlier, because the **Diagnostics** window is a preview feature, make sure that you first select it on the **Features** tab of the **Options** dialog and then restart Message Analyzer to make it available.  
  
> [!NOTE]
>  After you open the **Diagnostics** window for analyzing trace results, you might notice that a scrolling, marquee-style progress indicator displays for larger message sets while Message Analyzer iterates through the current session data, retrieves the diagnosis messages, and configures a display of summary data.  
  
## Repositioning the Diagnostics Tool Window  
 As with other **Tool Windows**, you have the option to undock and reposition the **Diagnostics** window by taking advantage of the docking navigation control that displays after you drag the **Diagnostics** window away from its default docking location by its tab. You might do this to configure a location for the window that better suits your purposes, for example, to obtain context by correlating message selection in the **Diagnostics** window with message selection in the **Analysis Grid** viewer, as the former drives the latter.