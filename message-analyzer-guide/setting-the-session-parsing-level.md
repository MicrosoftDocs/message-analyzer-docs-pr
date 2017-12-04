---
title: "Setting the Session Parsing Level | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 126ee1dd-a697-4e73-8171-fa559e810bf2
caps.latest.revision: 40
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Setting the Session Parsing Level
Message Analyzer provides a collection of built-in **Parsing Level** scenarios that are available for selection in the **New Session** or **Edit Session** dialog. You can specify a single **Parsing Level** for any one particular session only. By carefully choosing a **Parsing Level** that is appropriate for the **Trace Scenario** you are using, as described in [Choosing Parsing Levels](setting-the-session-parsing-level.md#BKMK_ChooseParsLevel), you can dramatically improve your Message Analyzer experience because you will be able to do the following:  
  
-   **Realize performance improvements when loading large traces** — by limiting the level to which Message Analyzer parses, you can quicken processing time, consume less memory, and reduce the overall costs of problem solving.  
  
-   **Target specific messages for analytical focus** — by removing messages above a specified stack layer or module, you can more easily focus on messages at a layer of interest.  
  
## Understanding Parsing Levels  
 To facilitate the previously mentioned improvements, each **Parsing Level** scenario applies preconfigured Runtime filtering functionality that defines the layer or module to which Message Analyzer parses, and specifies other messages that are explicitly passed in each scenario. For example, a typical predefined filter has a StopAtModule function that tells the Runtime to stop at a particular module such as TCP; it can also have an ExcludeFilter that enables certain other message types to pass that were predetermined to make specific **Parsing Level** scenarios more useful for diagnostic analysis at the particular layer where they apply.  
  
 The following table describes the **Parsing Levels** that you can select from the **Parsing Level** drop-down menu in the **New Session** or **Edit Session** dialog. Note that the **Definition** column specifies a representation of the filtering functionality that is preconfigured in each **Parsing Level** scenario.  
  
### Table 8.  Message Analyzer Parsing Levels  
  
||||  
|-|-|-|  
|**Name**|**Description**|**Definition**|  
|**Full**|Enables the Message Analyzer default **Parsing Level**.|No **Parsing Level** is applied; note however, that parsing results can be impacted by the PEF **Trace Scenario** or other message provider in use.|  
|**Network Analysis**|Focuses on diagnosing Transport and Network layers, but includes UDP/TCP traffic along with DNS, DHCP, ARP, and ICMP messages.|-   Exclude Filter: TCP.Port==53 or TCP.Port==42<br />     StopAtModule: TCP<br />-   Exclude Filter: UDP.Port==53 or UDP.Port==546 or UDP.Port==67 or UDP.Port==137 or UDP.Port==1512<br />     StopAtModule: UDP **Note:**  ARP and ICMP are included in this scenario because they are not explicitly excluded, therefore, they parse to the top level in this scenario.|  
|**File Sharing**|Focuses on diagnosing file sharing scenarios, but is limited to SMB and some simple name resolution protocols such as WINS, DNS, and NetBIOS.|-   Exclude Filter: TCP.Port==445 or TCP.Port==135<br />     StopAtModule: TCP<br />-   Exclude Filter:<br />     StopAtModule: SMB<br />-   Exclude Filter:<br />     StopAtModule: SMB2<br />-   Exclude Filter: UDP.Port == 53 or UDP.Port==546 or UDP.Port==67 or UDP.Port==137 or UDP.Port==1512<br />     StopAtModule: UDP|  
|**High Performance Capture without Parsing**|Displays events at the ETW level only, for the highest possible performance.|-   Exclude Filter:<br />     StopAtModule: ETW<br />-   Exclude Filter:<br />     StopAtModule: CapFile<br />-   Exclude Filter:<br />     StopAtModule: PcapFile|  
|**HTTP**|Focuses on HTTP traffic.|-   Exclude Filter: IPv4.Protocol==6<br />     StopAtModule: IPv4<br />-   Exclude Filter: IPv6.NextHeader==6<br />     StopAtModule: IPv6<br />-   Exclude Filter: WFPCapture.Protocol==6<br />     StopAtModule: WFPCapture<br />-   Exclude Filter: TCP.Port==80<br />     StopAtModule: TCP<br />-   Exclude Filter:<br />     StopAtModule: HTTP|  
|**Identity and Active Directory**|Focuses on LDAP traffic.|-   Exclude Filter: IPv4.Protocol==6<br />     StopAtModule: IPv4<br />-   Exclude Filter: IPv6.NextHeader==6<br />     StopAtModule: IPv6<br />-   Exclude Filter: TCP.Port==389 or TCP.Port==3268<br />     StopAtModule: TCP|  
  
> [!NOTE]
>  Because upper message layers are removed by the application of these **Parsing Level** scenarios, which subsequently reduces the number of messages that Message Analyzer parses, you should notice incremental but very striking performance gains.  
  
<a name="BKMK_ChooseParsLevel"></a>   
## Choosing Parsing Levels  
 Because Message Analyzer PEF providers focus on different inspection points into the message stack, you should carefully consider the **Parsing Level** that you choose; otherwise, you might obtain unexpected results. For example, you might choose a **Loopback and Unencrypted IPSEC** **Trace Scenario** for your Live Trace Session to reduce lower-level noise and to focus on Transport layer messages, but you are also interested in looking at messages from a particular application along with their transports. If you also choose the **Network Analysis** **Parsing Level**, Message Analyzer will parse up to and including the Network Layer only, which means that you will not see the Application layer traffic that the **Loopback and Unencrypted IPSEC** scenario would normally pass.  
  
 On the other hand, if you were to choose the **Pre-Encryption for HTTPS** **Trace Scenario** and **Network Analysis** **Parsing Level** scenario to work together in a trace, you would retrieve no messages at all because the **Pre-Encryption for HTTPS** scenario focuses on HTTP messages only and the **Network Analysis** **Parsing Level** stops when parsing of the Network Layer is complete, with the exception of certain other traffic on specified ports.  
  
 However, if you are interested in diagnosing the Network Layer, along with certain Transport Layer messages, and Application Layer traffic is of no consequence, then either a **Loopback and Unencrypted IPSEC** or **Local Network Interfaces** **Trace Scenario** working together with the **Network Analysis** **Parsing Level** should produce a desirable result while reducing the overhead associated with capturing and parsing Application Layer protocols.  
  
## Parsing Level Impact on Analysis Perspectives  
 After you choose a **Parsing Level**, start a Live Trace Session, and then observe data displaying in the default **Analysis Grid** viewer, you will see a **Parsing Level** indicator on the Message Analyzer Status Bar below the grid. If you are loading saved data through the **Open** feature (on the Message Analyzer **File** menu or the global Message Analyzer toolbar) from a trace file that reflects a **Parsing Level** set by another user, you can quickly ascertain what that **Parsing Level** is by looking at the Status Bar setting after the data is loaded. This information can be important to your analysis perspective, because it can alter the message set from what you might ordinarily expect in a particular **Trace Scenario**. In addition, you should also note that the **Message Stack** **Tool Window** and the inline origins display (click the green cubes icon on any top-level message in the **Analysis Grid** viewer) will reflect the **Parsing Level** by not showing messages above the top-most parsed level. Note that the resulting simplified view of the message stack can also improve your analysis processes.  
  
## Working with Viewpoints  
 By setting a **Parsing Level**, you can achieve dramatic performance gains, while at the same time you change the way message content displays. By setting a **Viewpoint**, messages are reorganized to show data from the viewpoint of a particular protocol, which also changes the way message content displays. When working with **Viewpoints** and **Parsing Levels**, you should consider the **Parsing Level** of the data when applying a **Viewpoint**. For example, if you configured the **Network Analysis** **Parsing Level** for a particular set of messages displaying in the **Analysis Grid** viewer and you then set the Application Layer **HTTP** or **SMB/SMB2** viewpoint from the **Viewpoints** drop-down list on the Message Analyzer Filtering toolbar, no results will display in the **Analysis Grid** viewer. This is because the Network Layer is the top-most level to which Message Analyzer parses in the **Network Analysis** scenario, which is well below the indicated Application Layer viewpoints. On the other hand, if you select a **Viewpoint** such as the **TCP Layer**, Message Analyzer will provide a precisely focused view of TCP messages only. Therefore, you might consider the following factors to maximize the effectiveness of using these features together:  
  
-   Prior to starting a Live Trace Session, choose a **Parsing Level** that will work with the **Viewpoint** that you have in mind.  
  
-   Set the **Parsing Level** up-front to maximize performance gains.  
  
-   Set **Viewpoints** to obtain focused analysis in the resulting message set.  
  
## Interacting with the Truncated Parsing Mode  
 If you are loading files that contain truncated messages, such as .cap, .pcap, .pcapng, or .matp files; or if the **Truncated Parsing** option is set when loading data into Message Analyzer, you might encounter some issues in your trace results, depending on the **Parsing Level** that you set.  If Message Analyzer detects truncated messages in a file containing data that you want to load, or if you specifically set the **Truncated Parsing** option on the **Files** tab of the **New Session** or **Edit Session** dialog for a Data Retrieval Session, Message Analyzer automatically switches to a limited OPN parser set consisting of parsers for the Ethernet, GRE, IPv4, IPv6, ESP, AH, IKE, AIPS, TCP, UDP, and HTTP protocols. Truncated parsing can improve performance by reducing the number of messages that Message Analyzer parses and displays; however, you will need to consider the resulting limited message set if you also configure a **Parsing Level**. For example, when the **Truncated Parsing** mode is active and a **Parsing Level** such as **File Sharing** or **Identity and Active Directory** is also set, you will be unable to see SMB or LDAP messages, respectively, in the trace results displayed by a viewer such as the **Analysis Grid**. This is because the limited OPN parser set that is used in the **Truncated Parsing** mode does not include parsers for these protocols.  
  
 Therefore, depending on the analysis perspective that you require, it might be best to limit the use of the **Truncated Parsing** and **Parsing Level** features together. Both features provide performance gains, which in either case is a positive outcome, but regarding the impact on focused analysis, you should consider that the advantages of one may outweigh that of the other, depending on the **Parsing Level** that you specify.  
  
## Saving and Viewing Trace Data with Set Parsing Levels  
 If you run a Live Trace Session with a particular **Parsing Level** set, the level displays in the **Parsing Level** label on the Message Analyzer Status Bar below the **Analysis Grid** viewer. You can save your trace results as you normally do in a \*.matp file and the saved message set will reflect the applied **Parsing Level**. However, although you can load and view the data from such a file through a Data Retrieval Session, you can view the original **Parsing Level** results that exist in the retrieved data only if you load the file into Message Analyzer through the **Open** feature that is accessible from the Message Analyzer **File** menu or from the global Message Analyzer toolbar. If you load the data from the saved file in a Data Retrieval Session with the **New Session** dialog, by default, Message Analyzer reparses the data with the **Parsing Level** set to **Full**, in which case, the original **Parsing Level** in the saved message set is not reflected in the resulting display of messages.  
  
## Obtaining Parser Level Updates  
 The **Parsing Level** scenarios that you select from the **Parsing Level** drop-down list in the **New Session** or **Edit Session** dialog are Message Analyzer assets. Similar to **Viewpoints** and other asset libraries, you can either download the **Message Analyzer Parsing Level** asset collection once, or auto-sync the collection to receive periodic collection updates that Microsoft provides through a web service. This service integrates with Message Analyzer through the Sharing Infrastructure. You can interact with this infrastructure from the **Asset Manager** dialog, which is accessible from the Message Analyzer **Tools** menu.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the Truncated Parsing mode, see [Detecting and Supporting Message Truncation](detecting-and-supporting-message-truncation.md).   
**To learn more** about **Viewpoints**, see [Applying and Managing Viewpoints](applying-and-managing-viewpoints.md).   
**To learn more** about downloading **Parsing Level** asset collections or auto-syncing to periodic collection updates as part of the Message Analyzer Sharing Infrastructure, see [Downloading Assets and Auto-Syncing Updates](downloading-assets-and-auto-syncing-updates.md).   
___________________\_  
  
## See Also  
 [Specifying a Parsing Level](specifying-a-parsing-level.md)