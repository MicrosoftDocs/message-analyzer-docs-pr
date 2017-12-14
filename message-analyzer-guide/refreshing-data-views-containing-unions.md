---
title: "Refreshing Data Views Containing Unions | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4bdd52b8-2a47-45cb-bbba-fc8adff456da
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Refreshing Data Views Containing Unions
This section briefly describes how Message Analyzer data and operations are refreshed in response to **Union** modifications.  
  
## Refreshing Message Data  
 If you change a **Union** field, property, or annotation but the **Type** does not change, and you do not modify the **Name** value of the **Union**, then an automatic refresh of message data is performed for all open data viewers in which the **Union** is active. For example, you might have a **Union** displaying in the **Analysis Grid** viewer as a result of loading a view **Layout** that contains a column that is named by the **Union**. Moreover, you might have a **Layout** for the **Chart** viewer that uses the **Union** in a visualizer component where you have configured a formula to perform a particular calculation for the data display. In these cases, a refresh of message data could involve an update to the displayed set of **Union** values. The previously indicated type of change to a **Union** is the only one that can result in an automatic refresh of message data in all data viewers and visualizers that are currently open and using the **Union**. In all other cases, there is no automatic refresh of data, as described in [Pending Changes](refreshing-data-views-containing-unions.md#BKMK_NoDataRefresh).  
  
## Refreshing Operations in Progress  
 If Message Analyzer is sorting, grouping, filtering, or performing some other operation on a message set when a **Union** data change occurs, all applicable data viewers that use the **Union** will restart those operations.  
  
<a name="BKMK_NoDataRefresh"></a>   
## Pending Changes  
 If you modify a **Union** by changing the **Name**, or if the **Type** changes because of adding or removing a **Union** field, property, or annotation, or if you delete the **Union**, then message data in all open data viewers that use the **Union** is *not* refreshed. Instead, the **Union** is internally marked for either the edited state or deleted state and awaits a Message Analyzer restart before the pending changes are applied.  
  
 At this time, you are advised to manually remove such a **Union** from all Message Analyzer features in which it is currently used. For example, if there was a **Name** change for the **Union**, after a restart it will no longer exist under its previous **Name** in any feature that formerly used it. Therefore any Filter Expressions, view **Layouts**, Chart **Layout** formulas, **Color Rules**, and so on, that use such a **Union** will be impacted. Note that even the display of **Aliases** can be affected. For example, a **Union** *value* that displays in an **Analysis Grid** column that is named by the **Union**, could be an **Alias** due to the underlying alias **Value** (as in the **Alias Editor** dialog), and **Union** modifications can change the way an **Alias** displays.