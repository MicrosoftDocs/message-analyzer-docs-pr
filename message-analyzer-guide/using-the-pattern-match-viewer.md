---
title: "Using the Pattern Match Viewer | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 2d18fdda-b5b2-40fd-a5fb-3d438b3544e0
caps.latest.revision: 26
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Using the Pattern Match Viewer
This topic describes how to execute built-in **Pattern** expressions, how to view **Pattern** match data, and how to view messages that are associated with **Pattern** match data. To get started, you can launch the **Pattern Match** viewer against an existing set of trace results that are displayed in an **Analysis Grid** viewer instance. To do so, click the **New Viewer** drop-down list on the global Message Analyzer toolbar and select the **Pattern Match** item.  
  
## Executing Built-In Pattern Expressions  
 After you launch the **Pattern Match** viewer, you can execute a **Pattern** expression to view the results of pattern matching. You can do so by clicking one of the built-in **Pattern** expressions in the **AVAILABLE PATTERNS** pane of the **Pattern Match** viewer to execute that **Pattern** expression and return any pattern matches it finds.  
  
> [!NOTE]
>  You can create one or more **Pattern** expressions of your own by clicking the **Create Pattern** button in the **Pattern Match** viewer toolbar. After you create a new **Pattern** expression, Message Analyzer adds it to the **My Items** category of the **AVAILABLE PATTERNS** list, from where you can select the expression to execute it against a set of trace results.  
  
 Currently, the built-in **Pattern** expressions that are available by default in every Message Analyzer installation are contained in the following category:  
  
-   **Network** category — the built-in **Pattern** expressions that are available in this category consist of the following:  
  
    -   **FTP Port Negotiate Failure** — locates negotiated FTP ports that are blocked with a Reset or fail to respond to a TCP SYN.  
  
    -   **FTP Port Negotiate Success** — searches for occurrences of FTP ports that are negotiated and then successfully set up as a TCP session.  
  
    -   **RPC Endpoint Mapper Failure** — searches for RPC ports that are negotiated through the RPC endpoint mapper, but blocked by the firewall or are ignored.  
  
    -   **RPC Endpoint Mapper Success** — locates occurrences of RPC port negotiation and of subsequent successful negotiation of a TCP session.  
  
    -   **Sack Detection** — searches for all selective acknowledgement (SACK) messages, which indirectly indicate the same network issues that cause TCP retransmits to occur, providing that SACK is enabled.  
  
    -   **TCP Connect Scan** — returns TCP sessions that are actively reset by the destination. Can be useful to find malware scans on the network.  
  
    -   **TCP FIN Stealth Scan** — searches for matches to TCP three-way handshakes that have no response, as an indication that a port is blocked or not listening. A significant number of matches could indicate network scanning is taking place.  
  
    -   **TCP Inactive Session Scan** — searches for TCP sessions where connection attempts have no response from an inactive port, which could be an indication of a security attack.  
  
    -   **TCP Retransmit Pairs** — enables you to identify pairs of retransmitted TCP messages with the same sequence and acknowledgement numbers and an identical payload size, that occurred in the current set of messages.  
  
    -   **TCP Syn Half Open Connections** — searches for TCP Syn/half open connections, such as a session that had a response where a port was opened but then Reset. Could indicate a port attack, for example, a denial of service (DoS) attack.  
  
    -   **Three-Way Handshake** — enables you to isolate all three-way handshakes that occurred when setting up TCP connections, for both IPv4 and IPv6 transports, in the current set of messages. Also displays the approximate round trip time as the time delta between Syn messages and Syn Acknowledgement messages.  
  
    > [!NOTE]
    >  In the latest Message Analyzer build on the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=44226), all of the TCP Pattern expressions are enabled to work  with the **Microsoft-PEF-WFP-MessageProvider**, which has no IP/Network Layer.  
  
-   **TLS** category — the built-in **Pattern** expressions that are available in this category are described below.  
  
    -   **TLS Negotiation** — detects TLS sessions in which connection requests were initiated by a TLS client where the Session ID = 0, in other words, a cached Session ID was not used.  
  
         The server then issues a Session ID to the client, which the client may or may not cache for use in subsequent connection requests. By caching the Session ID, the client can reuse the existing ID as a shortcut to facilitate subsequent connection requests, as required.  
  
    -   **TLS Renegotiate** —           detects TLS sessions in which connection requests were initiated by a TLS client and the Session ID > 0, in other words, a cached Session ID was used.  
  
         When a connection request for a TLS session is initiated by a TLS client and it reuses an existing Session ID, the client request is renegotiated to the TLS server with the use of a cached Session ID. However, during renegotiation, not all the TLS session information is represented on the wire.  When this occurs, Message Analyzer’s decryption expert is unable to decrypt these renegotiated          sessions.  
  
     Therefore, the primary scenario in which you might execute these TLS **Pattern** expressions is when you run decryption against a set of trace results and you discover that decryption did not successfully occur, or a  connection in which you were interested was not decrypted. By executing these **Pattern** expressions, you might  learn that one or more connections in question were renegotiated. For example, you could determine this by examining which session connection requests were negotiated with an existing/cached Session ID and which ones were not.  
  
## Viewing Pattern Match Data  
 When you execute a **Pattern** expression, the results first display in the **MATCHES** pane of the **Pattern Match** viewer in a Matched pattern selector. To display the matched instances in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer for the results of an executed **Pattern** expression, you can simply click the corresponding Matched pattern selector check box. This selector also has labels and controls that provide the following information or functions, respectively:  
  
-   **Matched instance count** — a label that indicates the number of matched instances that were returned by an executed **Pattern** expression.  
  
-   **Message count** — a label that indicates the total number of messages associated with all matched instances that were returned by an executed **Pattern** expression.  
  
-   **Information icon** — can link to a site that contains support information for the type of **Pattern** expression that Message Analyzer executed. For example, the Information icon in the Matched pattern selector for the built-in **TCP Three-Way Handshake** pattern takes you to a site that provides more information about three-way handshake patterns. Note that you can specify a custom site to link to with the use of the **Remediation** feature when you are configuring a **Pattern** expression of your own.  
  
-   **Pattern expression name** — a label that indicates the name of the executed **Pattern** expression. Hover over this label with your mouse to display a tooltip with summary information for a particular results set, which can include a **Description** of the **Pattern** expression.  
  
-   **Check to include matches in the Instance list** check box — by placing a check mark in this check box or by removing it, you can alternately show or hide the results of an executed **Pattern** expression in the **MATCHED INSTANCES** list, respectively. This is useful when you are displaying multiple Matched pattern selectors that result from executing multiple **Pattern** expressions that returned data. By selecting and deselecting different Matched pattern selectors in the **MATCHES** pane, you can alternately display or hide the matched instances of any results set.  
  
    > [!NOTE]
    >  If you are already displaying matched instances in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer that result from executing a particular **Pattern** expression, you should unselect the corresponding Matched pattern selector for such  **Pattern** expression results before you attempt to display the results of another **Pattern** expression execution by clicking a different Matched pattern selector. Otherwise, it could be more difficult to locate the latter data in the **MATCHED INSTANCES** pane, given that it is chronologically ordered and could be buried amidst other data.  
  
-   **Additional Options** drop-down menu — by clicking the black drop-down arrow on any Matched pattern selector, a menu appears with the following commands:  
  
    -   **Open Messages in Analysis Grid** — enables you to display the messages associated with a particular Matched pattern selector in the **Analysis Grid** viewer, for example, to examine message details or the message stack.  
  
    -   **Open Pattern Messages in Gantt** — enables you to display the messages associated with a particular Matched pattern selector in the **Gantt** viewer, for example, to examine the time window in which the matched instance messages occurred, along with source and destination IP address information.  
  
## Removing Pattern Match Data  
 To remove the results of an executed **Pattern** expression, simply click the check box for the executed **Pattern** expression in the **AVAILABLE PATTERNS** pane of the **Pattern Match** viewer to remove its check mark. This results in simultaneously removing the Matched pattern selector and any match instances data that are displaying in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer for the particular **Pattern** expression that you deselected. You also have the option to simply unselect any Matched pattern selector to hide its associated matched instances data, until you select it again.  
  
<a name="BKMK_ViewMatchedInstanceData"></a>   
## Viewing Matched Instance Message Data  
 The **MATCHED INSTANCES** pane displays all the instances that matched the **Pattern** expression that you executed, providing that you enable the  corresponding Matched pattern selector. The **MATCHED INSTANCES** pane consists of the following elements:  
  
-   A down arrow that opens a drop-down list that contains the following commands:  
  
    -   **Create Bookmark** — this command enables you to create a bookmark for one or more selected matched instances in the **MATCHED INSTANCES** pane. All messages associated with each selected matched instance will receive a bookmark.  
  
         For example, if you have the **Bookmarks** **Tool Window** displayed when you select two matched instances in the **MATCHED INSTANCES** pane and you execute the **Create Bookmark** command, all the messages that are associated with the selection will receive a bookmark  and will appear in the **Bookmarks** **Tool Window** as a **Pattern Group**. Thereafter, if you click the book icon for the **Pattern Group** in the **Bookmarks** **Tool Window**, you will see all the messages that received a bookmark. If you then place the **Analysis Grid** viewer in focus (or dock it next to the **Pattern Match** viewer), you will be able to highlight each bookmarked **Pattern Group** message in the **Analysis Grid** viewer as you select them in the **Pattern Group** message list of the **Bookmarks** **Tool Window**.  
  
    -   **Bookmark All Matches** — this command enables you to configure a bookmark for all matched instances currently displayed in the **MATCHED INSTANCE** pane. This results in creating  bookmarks for all messages in each  matched instance. If you have more than one Matched pattern selector enabled, the pattern groups in the **Bookmarks** **Tool Window** will have the same name as the executed **Pattern** expression, rather than being named a **Pattern Group**.  
  
    -   **Open Messages in Analysis Grid** — this command enables you to display all messages in one or more selected matched instances from the **MATCHED INSTANCE** pane in a new instance of the **Analysis Grid** viewer for further assessment.  
  
    -   **Open Pattern Messages in Gantt** — this command enables you to display all messages in any one selected matched instance from the **MATCHED INSTANCE** pane in a new instance of the **Gantt** viewer for further assessment.  
  
    -   **Open Pattern Instances in Gantt** — this command enables you to display all messages in one or more selected matched instances from the **MATCHED INSTANCE** pane in a new instance of the **Gantt** viewer for further assessment.  
  
-   A search text box that enables you to locate a specified string in all rows of matched instance data where a match is found.  
  
-   Numerous columns of data that are relevant to the Pattern expression that you executed and for which you received results.  
  
 The **MESSAGES** pane exists below the **MATCHED INSTANCES** pane of the **Pattern Match** viewer. Each time you select a matched instance in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer, the **MESSAGES** pane is populated with the messages that are associated with the matched instance that you selected. You can change the format in which these messages display by selecting any of the following format options in the **MESSAGES** drop-down list:  
  
-   **Show messages in a list** — the default selection that displays the messages associated with a matched instance in a simple list.  
  
-   **Show messages grouped by pattern** — select this option to display messages in the **MESSAGES** pane as an expandable node that is identified by an executed **Pattern** expression name. By clicking the expandable node, you can display all the messages associated with the executed **Pattern** expression. By default, the node is in the collapsed state.  
  
-   **Show messages grouped by sequential pattern match instance** — select this option to display messages in the **MESSAGES** pane as an expandable node that is identified by an executed **Pattern** expression name and the particular matched instance number that is selected in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer. By clicking the expandable node, you can display all the messages associated with the executed **Pattern** expression. By default, the node is in the collapsed state.  
  
 Regardless of the message display format that you choose, whenever messages for a matched instance are displaying in the **MESSAGES** pane of the **Pattern Match** viewer, you can right-click the matched instance messages and select one of the following context menu commands to display the messages:  
  
-   **Open All Messages** — opens all messages from a matched instance message group in a new instance of the **Analysis Grid** viewer, for example, to examine message details and stack information.  
  
-   **Open Selected Messages** — opens only the selected messages from a matched instance message group in a new instance of the **Analysis Grid** viewer, for further analysis.  
  
 Note that the **MESSAGES** pane also provides **MessageNumber**, **Timestamp**, and **Summary** data columns, and in some cases, other fields will be included as data columns for specific data that was detected by an executed **Pattern** expression. For example, the **TCP Three-Way Handshake** **Pattern** expression contains many additional data fields that can be useful for analyzing problems with the setup of TCP connections.  
  
 Also note that the drop-down list on the **MESSAGES** pane contains all the commands specified in the previous two lists.  
  
## See Also  
 [Understanding Message Pattern Matching](understanding-message-pattern-matching.md)   
 [Using the Pattern Editor](using-the-pattern-editor.md)