---
title: "OLP Filters | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 3271d95c-cc58-4f94-b48f-78b450bbf34d
caps.latest.revision: 31
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# OLP Filters
An OLP filter is a type of **Fast Filter** that enables you to locate message fields containing a specific **IPv4Address**, **IPv6Address**, **LinkLevelAddress**, string, or other value, by specifying an **O**ffset value,  bit **L**ength, and value **P**attern.  Only messages containing a match to the specified pattern are identified by the OLP filter for further processing.  Messages containing a match are then either included or excluded from the returned trace data, depending on the operator you configure in the OLP expression.  
  
## Using the OLP Format for Fast Filters  
 You can use the following format as a template when specifying an OLP filter as a **Fast Filter**:  
**op bit-offset:bit-length:hex-value**  
where “op” can be one of the following operators:  
  
-   Equals (==).  If not specified, “==” is assumed.  
  
-   Not equal to (!=).  
  
-   Greater than (>).  
  
-   Less than (<).  
  
 The OLP filter parameters for which you specify values are delimited by a colon (:).  These parameters have the following meanings:  
  
-   **Bit-offset** — is specified in hexadecimal format and represents the number of offset bytes that precede an address being searched for.  
  
-   **Bit-length** — is specified as an integer that equals the length in bits of the hex-value pattern.  
  
-   **Hex-value** — is specified in hexadecimal format and represents the address pattern for which you are searching.   
    Address patterns can be any of the following:  
  
    -   An **IPv4Address** in x.x.x.x format — is specified as an 8-digit hexadecimal number, 32-bits long; for example: *9D3B54DF*.  
  
    -   An **IPv6Address** in xx:xx:xx:xx:xx:xx:xx:xx format — is specified as a 32-digit hexadecimal number, 128-bits long; for example:  *9D3B54DFC4D7A46F0000000000000000*.  
  
    -   A **LinkLevelAddress** in xx-xx-xx-xx-xx-xx format — is specified as a 12-digit hexadecimal number, 48-bits long; for example: *001F297D2F46*.  
  
 By using an OLP filter, you can be very specific and granular about pinpointing messages that meet the filtering criteria that you define. This can have a big impact on reducing the amount of traffic you capture and improving performance, for example, to minimize the effect of a capture on a busy server.  
  
## Configuring an OLP Fast Filter  
 To configure an **OLP** filter, you must open the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog by clicking the **Configure** link to the right of the provider **Id** in the **ETW Providers** list that displays on the **Live Trace** tab of the **New Session** dialog. When the dialog displays, select the **Provider** tab and then click a **Filter** drop-down arrow in a **Fast Filter Group**. In the menu that appears, select the **OLP** item as the address type. You must then enter an OLP address in the text box to the right of the selected filter type, in the format that is described in this section.  
  
 You have the option to configure up to three **Fast Filters** per **Group** in the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, with the same or different address types. When you are finished with **Fast Filter** configuration, highlight the **System Network** tree grid row containing the adapter that you want to assign the **OLP Fast Filter** to, click the **Apply To Highlighted** button to assign the filter **Group** to the adapter, and then click **OK** to close the dialog. You can then start your Live Trace Session, at which time the **Microsoft-PEF-NDIS-PacketCapture** provider automatically isolates and captures messages that meet the criteria of the filtering configuration that you specified.  
  
---  
  
 **More Information**   
 **To learn more** about **Fast Filter** configuration capabilities, see [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md).   
---