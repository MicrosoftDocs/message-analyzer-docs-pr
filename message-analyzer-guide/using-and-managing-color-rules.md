---
title: "Using and Managing Color Rules | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 023d7c53-c97b-454e-9ab2-41d6bf956b6b
caps.latest.revision: 47
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Using and Managing Color Rules

Message Analyzer provides an important analysis feature known as  **Color Rules**, to enable you to define special filters that use color, text, and font styles to decorate and highlight messages that contain specific information in a trace. With this feature, you can apply visual indicators on top of individual message rows in a set of trace results or log data displaying in the **Analysis Grid** viewer, to easily identify specific types of traffic at a glance, thereby lessening the need for additional actions and diagnostics. Rather than as a mechanism that isolates particular messages that meet specific criteria and removes those that do not, such as you have with a view **Filter**, you can think of **Color Rules** as a feature that serves the following purposes:  
  
-   **Alerts** — you can use **Color Rules** to serve as a warning or reminder function that invites closer scrutiny and further investigation of certain messages that meet rules criteria.  
  
-   **Diagnostics** — you can configure multiple **Color Rules** with varying decoration features to provide an instant visual cue of messages that meet the criteria of multiple rules, based on specified filtering configurations that target diagnostic issues.  
  
-   **Organization** — you can organize the view of network/protocol infrastructure at a high level.  
  
With **Color Rules** applied, you can quickly expose subtleties that are not readily obvious in the default display style of the **Analysis Grid** viewer — for example, network direction, message payloads, and error conditions. This can help you effectively evaluate common issues with accuracy and speed. Moreover, you can design multiple **Color Rules** with differing decoration configurations and filtering criteria that apply to specifically related message types, so that the default display style will alter to include the decoration schemes of all the matching **Color Rules**. Using **Color Rules** in this manner can provide a more visually robust indication of some state, condition, or value that you are trying to pinpoint at-a-glance.  
  
For example, you could very quickly expose messages with a particular transport and network protocol in a trace by applying the default **TCP** left gradient and **IPv4 Right Gradient** rules from the **Color Rules** drop-down list on the **Analysis Grid** toolbar. Thereafter, all **TCP** messages that use **IPv4** will display in the **Analysis Grid** viewer with the opposite facing gradient color configurations that are characterized by these rules. Note that the **Analysis Grid** viewer will expose these color configurations by showing them in top-level messages, even if one of those **Color Rules** applies to an unexposed origins message only.  
  
## Using the Default Color Rule Asset Collection Library  

 To help you get started and familiarized with real-world usage examples, Message Analyzer provides a default set of **Color Rules** in several different **Categories** in the **Message Analyzer Color Rules** asset collection **Library**. These categories provide some basic filtering rules, decoration schemes, and text styles that are useful for exposing messages from common protocols such as TCP, ARP, SMB, HTTP, RPC, and so on. Message Analyzer provides the default set of **Color Rules** in the following categories:  
  
-   **Network**  
  
-   **Azure Storage**  
  
-   **Event Log**  
  
-   **File Sharing and Authentication**  
  
-   **Internet**  
  
-   **Event Tracing for Windows**  
  
-   **Hardware and Parsing Errors**  
  
-   **RPC**  
  
You can select any or all of the default **Color Rules** in your rule Library to immediately apply the associated rule functionality to a currently displaying message set. As a result, the default display color and style of messages in the **Analysis Grid** viewer that match the filtering criteria of the applied **Color Rules** will be overlaid with the decoration scheme and styles of such **Color Rules**. This temporary alteration to the default message display style provides an instant visual cue that enables you to rapidly discover message data that may be of interest in your analysis process. When you deselect one or more **Color Rules**, the associated display schemes and styles are immediately removed from the corresponding messages in the **Analysis Grid** viewer.  
  
<a name="BKMK_UsingGradientDecorations"></a>   
## Using Gradient Decoration Configurations  
 You might note that some of the default **Color Rules** in the **Network** category make use of *color gradients*, for example left-to-right and right-to-left gradient configurations. Message Analyzer enables you to specify a gradient background for your **Color Rule** configurations as one way to design visual decoration cues that are distinguishable from each other when messages meet the criteria of multiple rules that overlap. For example, you might design two **Color Rules**, each with different but related filtering rule criteria, or you could apply one of the default **Color Rules** that are configured to produce multiple visual cues when a message meets the criteria of multiple rules.  
  
 Several default **Color Rules** in the **Network** category will overlap each other when their rules are met, to provide visual indications of the network and transport layer protocols contained in certain messages in a set of trace results. The **Color Rules** that enable this to occur consist of the **IPv4**, **IPv6**, **TCP**, and **UDP** rules. These rules are configured to work in pairs, as follows:  
  
-   **IPv4** and **TCP**  
  
-   **IPv4** and **UDP**  
  
-   **IPv6** and **TCP**  
  
-   **IPv6** and **UDP**  
  
The **Color Rule** filtering criteria in this example is simple. The **IPv4 Color Rule** uses an “IPv4” filter expression; the **TCP Color Rule** uses a “TCP” filter expression; the **UDP Color Rule** uses a “UDP” filter expression; and so on for **IPv6**. When a particular message meets the filtering criteria of any of the **Color Rule** pairs indicated in the example, both directional gradients will be overlaid on the message and rendered easily visible, thus providing a quick visual cue of the particular message types that the specified filtering criteria reflects. For example, in the case of the default **IPv4** and **TCP** rules, **IPv4** uses a **Right-Hand Side** gradient decoration and **TCP** uses a **Left-Hand Side** gradient decoration, such that both decoration schemes will be easily recognized in a message row when the filtering criteria of both these rules is met.  
  
> [!NOTE]
>  The default gradient **Color Rule** pairs are specifically designed to visually coordinate the display of their gradients in opposite directions when overlaid on a single message that matches the filtering criteria of both rules. This is possible because each **Color Rule** makes appropriate use of a white background for either the **Left-Hand Side** or **Right-Hand Side** color in the **Gradient Background** configuration, so that the overlaid gradients can show through.  
  
## Expanding the Default Color Rule Asset Collection Library  

 If the default **Color Rules** do not provide the features that you need, you can obtain additional **Color Rules** in the following ways:  
  
-   **Download** — download **Message Analyzer Color Rule** asset collection updates from the Message Analyzer feed in the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu.  
  
-   **Import** — use the **Manage Color Rule** dialog to **Import** additional **Color Rule** items directly from a file share or other location where team members have posted such items for sharing.  
  
-   **Develop** — create, configure, and save your own **Color Rules** in your local **Color Rule** Library.  
  
Note that you can also **Export** your **Color Rule** items through the Message Analyzer Sharing Infrastructure to a file share that you can configure as a feed to which others may subscribe. In a future Message Analyzer release, the Sharing Infrastructure publishing features will automatically enable others to synchronize to any updates that you make to your **Color Rule** items on the feed. However, you can currently perform a manual configuration process that enables users to synchronize to your item updates, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
> [!TIP]
>  Because it can be time consuming to create your own **Color Rules**, you should take advantage of **Message Analyzer Color Rule** asset collection updates that are periodically available from Microsoft through the **Message Analyzer** feed in the **Asset Manager** dialog, or from other users that have created and shared their **Color Rules**. To do this, you will make use of the auto-sync and download features for user Library asset collections and the Message Analyzer Sharing Infrastructure, which are available from the **Asset Manager**. Since these features provide a convenient and consistent method for managing and sharing these items, you can quickly learn from others how to apply different methods and approaches to problem diagnosis, and thereby realize improvements in your effectiveness and efficiency as a message analysis specialist.  
  
---  
  
**More Information**   
**To learn more** about **Color Rule** management features, see [Managing Color Rules](managing-color-rules.md).  
**To learn more** about the Message Analyzer Sharing Infrastructure, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.  
**To learn more** about auto-syncing and downloading user Library asset collection updates, see [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md).  

---  
  
## See Also  

[Applying Color Rules](applying-color-rules.md)