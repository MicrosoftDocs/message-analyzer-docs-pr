---
title: "Map Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d044629-5e0b-4feb-a4f0-35f7c8af9a8a
caps.latest.revision: 10
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Map Tool Window
Message Analyzer provides the **Map** **Tool Window** to support data analysis in primary viewers that make use of data maps of various types, such as the **Gantt** and **Interaction** viewers. The **Map** window provides a high-level view of data points along with a navigation control that enables you to focus the corresponding primary data viewer on the data field locations that contain the messages you want to analyze. In the **Gantt** viewer, this means that you can quickly locate specific color-coded message groups on which you want to focus during analysis. For the **Interaction** viewer, this means that you can quickly locate data points in the  **Mapping**, **Diagram**, and **Chord** display formats of the **Interaction** viewer that contain the messages on which you want to focus your analysis. The modes of operation and zooming capabilities of the **Map** window are described in the section that follows.  
  
## Map Tool Window Controls  
 The **Map** window contains several commands that you can utilize from a context menu that displays when you right-click anywhere in the **Map** window data field. These commands consist of the following:  
  
-   **Mouse Mode** — provides the following commands:  
  
    -   **Zoom** — enables the **Zoom** mode, where you can create a data selection window by clicking and dragging your mouse across the **Map** window data field.  
  
         The **Zoom** mode works together with options of the **Zoom** item described below, by altering the zooming ratios of the **X** axis, **Y** axis, or both **X and Y** axis together, to enable you to focus on specific messages that you want to analyze. The presets that you can select to change the zoom ratio are accessible from the secondary context menu of the **Zoom** item described below.  
  
        > [!TIP]
        >  After you create a data selection window, you can click anywhere in the **Map** window data field and cause the selection window to track your mouse clicks by jumping to that location.  
  
    -   **Pan** — enables the **Pan** mode, where you can drag a fixed-size data selection window across the **Map** window data field to locate the messages on which you want to focus your analysis.  
  
-   **Zoom** — enables you to change the zoom ratio in the **Map** window by selecting preset zooming values for the **X** axis, **Y** axis, or **X and Y** axis together, as follows:  
  
    -   **1:1**  
  
    -   **Fit**  
  
    -   **In**  
  
    -   **Way In**  
  
    -   **Out**  
  
    -   **Way Out**  
  
-   **Fit Map to Window** — by selecting this mode, it enables you to fit the entire data field of the in-focus viewer into the **Map** window. By unselecting this mode, the **Map** window data field size no longer encapsulates the data field of the  in-focus viewer.