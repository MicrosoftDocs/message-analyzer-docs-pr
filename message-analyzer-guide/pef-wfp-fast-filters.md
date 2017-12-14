---
title: "PEF-WFP Fast Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0155104-ad21-4da1-8123-39d07fdcc411
caps.latest.revision: 37
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# PEF-WFP Fast Filters
The **Microsoft-PEF-WFP-MessageProvider** configuration on the **Provider** tab of the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog contains **Fast Filter** settings, which enable you to apply filtering to messages before they are passed to the Message Analyzer Runtime for parsing. By applying a **Fast Filter** at the driver-level rather than using a  **Session Filter** that is applied after parsing, you can lower system loads by reducing CPU processing, parsing less data, and writing fewer events to prevent more costly disk I/O. Driver-level filtering enables significant improvements in speed as compared to a **Session Filter**, where the Runtime parsing engine does the filtering.  
  
## Using WFP Fast Filters  
 The actual work that is performed by the **Fast Filters** that you specify in the **Microsoft-PEF-WFP-MessageProvider** configuration is accomplished by the WFP base filtering engine (BFE). The message frames that pass the filtering criteria are delivered to the **Microsoft-PEF-WFP-MessageProvider** callout drivers at the corresponding layers, which in turn send the messages to the enabling ETW session.  
  
 **WFP Fast Filters** consist of the following types:  
  
-   **IPv4** — enables you to filter live traffic based on a specified IPv4 address, as described in [IPv4Address Filters](ipv4address-filters.md).  
  
-   **IPv6** — enables you to filter live traffic based on a specified IPv6 address, as described in [IPv6Address Filters](ipv6address-filters.md).  
  
-   **TCP port** — enables you to filter live traffic based on a specified TCP port.  
  
-   **UDP port** — enables you to filter live traffic based on a specified UDP port.  
  
 When configuring **Fast Filters** in the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog, you have the option to enhance filter functionality with the use of several relational operators, including logical NOT (!), GREATER THAN (>), and LESS THAN (<). For example, you might apply **Fast Filter** configurations that exclude or include specific traffic on a **TCP port** or **UDP port**, respectively. To do this, you could configure one **Fast Filter** with the **TCP port** set to remove HTTPS traffic from your trace results and another **Fast Filter** with the **UDP port** set to exclude all traffic except LDAP messages, respectively, as follows:  
  
 **Fast Filter 1** value for **TCP port**:  `!= 443`  
**Fast Filter 2** value for **UDP port**:  `== 389`  
  
## Capturing Loopback Traffic  
 If you want to see only loopback (local application) traffic for IPv4 and IPv6 addresses in a Live Trace Session, you will need to explicitly filter for such traffic, or you can use the **Local Loopback Network** **Trace Scenario**, which does this with the following preset **Fast Filters**: `127.0.0.1` for the **IPv4** filter and `::1` for the **IPv6** filter.  
  
## Removing Loopback Traffic  
 If you want to remove local loopback traffic, you will need to explicitly filter out the loopback address and any traffic that is either coming from or going to an IPv4 or IPv6 address that is being used by the related application communications. To do this, you must negate the loopback traffic. When you use negation in a **Fast Filter** expression, it behaves similar to the way the tilde (~) character does in a **Session Filter** or view **Filter**, in that non-existence of a specified value is not evaluated as negation. For example, the IPv4 **Fast Filter**: `!=192.168.1.1` is equivalent to the view **Filter**: `*Address ~=192.168.1.1`. With either of these filters, only IPv4 traffic is evaluated and all other traffic is ignored, whereas the view **Filter**: `*Address !=192.168.1.1` filters out the specified IP address, but also evaluates all IPv4 traffic and passes all addresses that are not 192.168.1.1.  
  
 Therefore, to filter out all loopback traffic, use **Fast Filters** similar to the following:  
  
 `!=127.0.0.1` for the **IPv4** filter and `!=::1` for the **IPv6** filter.  
  
 If the related applications are using other IP addresses, filter those out as well with more **Fast Filters**. You can specify up to four filters in the **Advanced Settings** dialog for the **Microsoft-PEF-WFP-MessageProvider**.  
  
---  
  
 **More Information**   
 **To learn more** about configuring **Fast Filters** for the **Microsoft-PEF-WFP-MessageProvider**, see [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  
**To learn more** about the Windows Filtering Platform (WFP), see [Windows Filtering Platform](http://go.microsoft.com/fwlink/?LinkId=523807).   
---