---
title: "LinkLevelAddress Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa567ad1-4737-4bb4-9eec-cffed775c05a
caps.latest.revision: 29
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# LinkLevelAddress Filters

A **LinkLevelAddress** is a type of **Fast Filter** that enables you to filter out all messages during a Live Trace Session except those that are sent to and from a specified physical address. You can also use several relational operators with **Fast Filters** to enhance filtering functionality. For example, for **LinkLevelAddress** filters, you could use the logical NOT (!=) operator to filter out all messages that are sent to and from a specified physical address. You might do this if you have multiple network adapters and you want to isolate traffic to a particular one. Other operators that are available for use with **Fast Filters** include EQUALS (==), LESS THAN (\<), and GREATER THAN (>).  
  
## Configuring a LinkLevelAddress Fast Filter  

 To configure a **LinkLevelAddress** filter, you must open the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog by clicking the **Configure** link to the right of the **Microsoft-PEF-NDIS-PacketCapture** provider **Id** in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. When the **Advanced Settings** dialog displays, select the **Provider** tab and then click a **Filter** drop-down arrow in a **Fast Filter Group**. In the menu that appears, select the **LinkLevelAddress** item as the address type. You must then enter a media access control (MAC) address for the network adapter on which to capture messages by specifying its value in the text box to the right of the selected filter type, in a format similar to the following examples:  
  
 `00-2F-39-7E-1F-36`   
 `!=00-2F-39-7E-1F-36`  
  
 You have the option to configure up to three **Fast Filters** per **Group** in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, with the same or different address types. For example, you might want to use three MAC addresses to collect or block data from a specified set of network adapters. When you are finished with **Fast Filter** configuration, highlight the **System Network** tree grid row containing the adapter that you want to assign the **LinkLevelAddress** **Fast Filter** to, click the **Apply To Highlighted** button to assign the filter **Group** to the adapter, and then click **OK** to close the dialog. You can then start your Live Trace Session, at which time the **Microsoft-PEF-NDIS-PacketCapture** provider automatically isolates and captures messages that meet the criteria of the filtering configuration that you specified.  
  
---  
  
 **More Information**   
 **To learn more** about **Fast Filter** configuration capabilities, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).   

---