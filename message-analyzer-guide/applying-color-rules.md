---
title: "Applying Color Rules | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2cb58d85-4c55-4416-b6e2-2eace1068a89
caps.latest.revision: 29
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Applying Color Rules
In the Message Analyzer **Analysis Grid** viewer, each row of the message grid displays in a default style. When a message meets the filtering criteria of a **Color Rule**, the colors and styles of the rule that differ from the default row style are applied on top of the associated message row. If the filtering criteria of another **Color Rule** also applies, both styles can be applied to the particular message row in the **Analysis Grid** viewer. For an example of this, see [Using Gradient Decoration Configurations](using-and-managing-color-rules.md#BKMK_UsingGradientDecorations).  
  
## Applying Color Rules to a Trace  
 When you are ready to apply **Color Rules** to the results of a Live Trace Session or a Data Retrieval Session, you can select the **Color Rules** that you want to apply in a few different ways, as follows:  
  
-   **Individually** — apply specific **Color Rules** by selecting them one at a time.  
  
-   **Categorically** — apply all the **Color Rules** in a **Category** by selecting the **Category**, for example, the **Network** category or **My Items** category.  
  
-   **Globally** — apply all the **Color Rules** in the local **Message Analyzer Color Rules** asset collection Library by selecting the **Message Analyzer** and **My Items** nodes in the **Color Rules** drop-down list, which is accessible on the **Analysis Grid** viewer toolbar.  
  
 Each rule **Category** contains a tree view of **Color Rules** that you can selectively enable or disable by placing a check mark in the check box of a rule, or by removing it, respectively. A **Category** that has only a subset of rules enabled is shown with its check box in the shaded tri-state condition. A **Category** that has all its rules enabled is simply shown with a check mark in its selection check box.  
  
> [!NOTE]
>  If you leave a **Color Rule** or one or more  **Categories** of rules enabled and you close the current Live Trace Session or Data Retrieval Session, the selected **Color Rules** will continue to be applied to all subsequent session results that you display in the **Analysis Grid** viewer, until such time that you disable them. Enabled **Color Rules** are also applied across all current Message Analyzer sessions.  
  
## See Also  
 [Creating and Modifying Color Rules](creating-and-modifying-color-rules.md)