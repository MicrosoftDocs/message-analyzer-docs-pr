---
title: "IPv6Address Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6823607-7c29-40c2-be9f-6b63429ecd6b
caps.latest.revision: 25
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# IPv6Address Filters
An **IPv6Address** is a type of **Fast Filter** that enables you to filter out all messages during a live trace except those that are sent to and from a specified IPv6 address. As with other **Fast Filter** configurations, you can also use several relational operators to enhance filtering functionality. For example, you could use the logical NOT (!=) operator to filter out all messages that are sent to and from a specified IPv6 address. You can also use the GREATER THAN (>) or LESS THAN (<) operators to isolate message traffic above or below a particular IPv6 address value, respectively.  
  
## Configuring an IPv6Address Fast Filter  
 To configure an **IPv6Address** filter, you must open the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog by clicking the **Configure** link to the right of the **Microsoft-PEF-NDIS-PacketCapture** provider **Id** in the **ETW Providers** list that displays on the **Live Trace** tab of the **New Session** dialog. When the **Advanced Settings** dialog displays, select the **Provider** tab and then click a **Filter** drop-down arrow in a **Fast Filter Group**. In the menu that appears, select the **IPv6Address** item as the address type. You must then enter the IPv6 address value with or without operators, by specifying it in the text box to the right of the selected filter type, in a format similar to the following examples:  
  
 `2001:4898:2b:3:ac0a:511:f971:5d85`   
 `!= 2001:4898:2b:3:ac0a:511:f971:5d85`   
 `> 2001:4898:2b:3:ac0a:511:f971:5d85`  
  
 You have the option to configure up to three **Fast Filters** per **Group** in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, with the same or different address types. For example, you might want to collect or block data from several IPv6 addresses. When you are finished with **Fast Filter** configuration, highlight the **System Network** tree grid row containing the adapter that you want to assign the **IPv6Address**  **Fast Filter** to, click the **Apply To Highlighted** button to assign the filter **Group** to the adapter, and then click **OK** to close the dialog. You can then start your Live Trace Session, at which time the **Microsoft-PEF-NDIS-PacketCapture** provider automatically isolates and captures messages that meet the criteria of the filtering configuration that you specified.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about **Fast Filter** configuration capabilities, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).   
___________________\_