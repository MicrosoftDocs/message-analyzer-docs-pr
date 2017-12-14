---
title: "TCP Rate and Diagnosis | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8965131-65b7-4862-983e-fd3eb0d43519
caps.latest.revision: 16
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# TCP Rate and Diagnosis
The **TCP Rate and Diagnoses** view **Layout** for **Charts** enables you to obtain a focused view of specific TCP data from a set of trace results that tells you the ratio of **Diagnoses** messages to all messages in each IP conversation in which **Diagnoses** errors occurred. This **Layout** uses a **Table** grid visualizer component that is driven by a data formula that automatically calculates a **Rate** value that exposes this message ratio. This **Layout** also has a **TCP** **Viewpoint** applied in the background, which isolates TCP messages to create a focused analysis context.  
  
## Using the TCP Rate and Diagnoses Layout  
 Because Message Analyzer automatically calculates the indicated **Rate** value, you can quickly narrow down the IP conversations where the highest **Rate** values exist, which in turn can provide a focus point for further investigation of TCP issues. For example, if you have a **Rate** value of .50, this means that half of the messages in a particular IP conversation contain underlying TCP **Diagnoses** messages. A **Rate** at this level could be significant, especially if the conversation also contains a high message count. To proceed with analysis, you might double-click the table grid row containing the **Rate** of interest to drive the display of conversation messages into a new instance of the **Analysis Grid** viewer for further analysis of the TCP **Diagnoses** messages and other message **Details**. From the **Analysis Grid** viewer, you can click a **Diagnoses** message icon in the **DiagnosisTypes** column to display the inline details for the **Diagnoses** message. In addition, given that the **Diagnostics** **Tool Window** data is driven by the content of the current in-focus data viewer, you can conveniently review the details of all **Diagnoses** messages in the IP conversation with which you are working from this **Tool Window**.  
  
> [!NOTE]
>  If the **Diagnostics** **Tool Window** is not displayed, you will need to enable it on the **Features** tab of the **Options** dialog in the global Message Analyzer **Tools** menu, and then restart Message Analyzer. Thereafter, you will need to select the **Diagnostics** window from the **Windows** submenu of the global **Tools** menu to launch it.