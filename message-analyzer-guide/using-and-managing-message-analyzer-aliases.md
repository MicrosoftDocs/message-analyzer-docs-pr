---
title: "Using and Managing Message Analyzer Aliases | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: abf59004-c012-4540-b0aa-58c42ac1f448
caps.latest.revision: 29
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Using and Managing Message Analyzer Aliases

Message Analyzer provides an **Aliases** function that enables you to substitute friendly names for several types of data field values in the **Analysis Grid** and other viewers. **Aliases** facilitate easy recognition of values that otherwise can be somewhat cryptic and difficult to work with. Message Analyzer maintains a default set of **Aliases** and any new ones that you create in an **Aliases** Library, which is accessible from the **Aliases** drop-down list on the global Message Analyzer toolbar and from the global Message Analyzer **Tools** menu. The intent of this feature is to improve your ability to discover and analyze specific message traffic through the use of simple user-defined naming conventions that have meaning in the context of your troubleshooting environment. By customizing your data analysis environment with aliasing, you can make it easier to keep track of traffic to or from different host IP addresses, physical addresses, ports, and so on. The data field types that currently support aliasing consist of the following:  
  
-   **Source and Destination IP Address** — for any **Source** or **Destination** IP address that displays in the **Analysis Grid** viewer, you can substitute a friendly name for the address value, for example, “MyComputer”.  
  
-   **Source and Destination Media Access Control (MAC) Address** — for any message that can display a MAC address data field value in the **Analysis Grid** viewer, for example an ARP message, you can substitute a friendly name for the address value, for example, “SenderAdapterMAC”, “TargetAdapterMAC”, and so on.  
  
-   **TCP SourcePort and TCP DestinationPort** — for any message that can display a TCP **SourcePort** or **DestinationPort** data field value in the **Analysis Grid** viewer, you can substitute a friendly name for the port. For example, you might use an application acronym prefix in the alias name that corresponds with the associated port, such as “HTTPPort”, “DNSPort”, “LDAPPort”, and so on.  
  
> [!NOTE]
>  In the case of MAC addresses, TCP **SourcePort**, and TCP **DestinationPort**, it is likely that you will need to use the **Field Chooser** **Tool Window** to add the necessary columns in the **Analysis Grid** viewer for displaying the values of these data field types, before you can create an **Alias** for a value in one or more of these columns.  
  
## Alias Example  

 As an example, the IPv6 address of a server, such as `FE80:0:0:0:4D45:3FCD:BDE0:69BE`, can be very difficult to read and keep track of when performing data analysis, as it is difficult to distinguish from other IPv6 addresses. Users often have to create an alternate method of externally mapping these addresses to a more friendly name, for example in a Notepad listing, which can be time-consuming and cumbersome during data analysis. With the Message Analyzer **Aliases** feature, you can simply replace such an IPv6 value with a friendly name such as “WebServer” or “DatabaseServer” to make traffic from the associated **Alias** address immediately obvious.  
  
---  
  
 **What You Will Learn**   
In the following topics of this section, you will learn how to create, manage, share, and perform Message Analyzer operations with aliases:  
[Creating Message Analyzer Aliases](creating-message-analyzer-aliases.md)  
[Modifying Message Analyzer Aliases](modifying-message-analyzer-aliases.md)  
[Enabling and Disabling Message Analyzer Aliases](enabling-and-disabling-message-analyzer-aliases.md)  
[Performing Message Analyzer Operations with Aliases](performing-message-analyzer-operations-with-aliases.md)  
[Managing Message Analyzer Aliases as Shared Items](managing-message-analyzer-aliases-as-shared-items.md)  

---