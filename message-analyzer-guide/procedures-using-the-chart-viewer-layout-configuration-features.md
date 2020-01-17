---
title: "Procedures: Using the Chart Configuration Features | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50f33d9e-ff89-4fed-9204-46b2bd5e9064
caps.latest.revision: 36
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Using the Chart Configuration Features

This section provides an example of how to extend Message Analyzer data
viewing capabilities by creating a custom **Chart** data viewer that you
can use to analyze message volume against HTTP payload content types.

---

**Procedure Overviews**  
A brief description of the procedure in this section is included below
for review. Note that more **Chart** development procedures will be
provided in the future.  

---

**[Create and Edit an HTTP Chart Data Viewer](#BKMK_CreateCharts)** —
demonstrates how you can create your own chart-style data viewer for
enhanced data analysis perspectives. This particular **Chart** exposes
the message volume associated with various HTTP content types being
delivered to a client computer in HTTP response messages, which can
provide an indication of the load on a web

<a name="BKMK_CreateCharts"></a>
## Create and Edit an HTTP Chart Data Viewer

This example demonstrates how to create a new **Chart** viewer that is
named “HTTP Content Types”, which provides a **Bar Chart** visualizer
component that shows the relative volume distributions of the content
types for HTTP messages captured in a
trace.

### To create and edit a Chart viewer

1. From the **Start** menu, **Start** page, or taskbar of your
    computer, click the **Microsoft Message Analyzer** icon to start
    Message Analyzer.
1. From **Favorites** list on the Message Analyzer **Start Page**,
    click the **Pre-Encryption for HTTPS** **Trace Scenario** and then
    navigate to one or more web sites to generate browser traffic and
    capture HTTP messages.
    
    Message Analyzer begins to collect HTTP and other messages in the
    **Analysis Grid** viewer.
1. At a suitable point, stop the trace by clicking the **Stop** button
    on the global Message Analyzer toolbar.
1. From the **New Viewer** drop-down list on the global Message
    Analyzer toolbar, click the **New Chart** item to display the
    **Chart** visualizer surface and data entry tabs.
1. In the **Name** property text box on the **Chart Layout** tab to the
    right of the **Chart** visualizer surface, enter the text “HTTP
    Content Types” to specify the name that will display for your new
    **Chart** viewer in the **New Viewer** drop-down list.
1. In the **Component Common** section of the **Component Layout** tab
    to the right of the **Chart** visualizer surface, specify a title
    for your **Chart** viewer in the **Name** text box.
1. In the **Component Common** section of the **Component Layout** tab
    to the right of the **Chart** visualizer surface, click the **Type**
    drop-down list and select the **Bar Chart** visualizer component.
1. On the **Data** tab to the right of the **Chart** visualizer
    surface, click the ellipsis (**…**) on the right side of the
    **Column Fields** property box to display the **Data Mapping Field
    Collection Editor** dialog.
1. In the **Data Mapping Field Collection Editor** dialog, click the
    **Add** drop-down list and select the **Formula** menu item.
    
    A new **Formula** item appears in the **Members** pane.
1. Click the **FormulaType** drop-down list in the **Formula
    properties** pane of the **Data Mapping Field Collection Editor**
    and select the **Count** item.
1. In the **Formula properties** pane of the **Data Mapping Field
    Collection Editor** dialog, click the ellipsis (**…**) to the right
    of the **Arguments** property to display the **Argument Collection
    Editor**.
1. In the **Argument Collection Editor**, click the **Add** button to
    add an **Argument** item to the **Members** pane.
1. In the **Argument properties** pane of the **Argument Collection
    Editor**, click the **FieldName** ellipsis (**…**) to display the
    **Field Chooser** **Tool Window**.
1. In the **Field Chooser** window, scroll down to the **HTTP** node,
    expand it, and select the **HTTP.Operation.ContentType** field.
1. In the **Field Chooser**, click the **Select** button to exit the
    dialog.
    
    The **ContentType** field displays in the **Arguments** list of the
    **Data Mapping Field Collection Editor**.
1. Click **OK** to exit the **Data Mapping Field Collection Editor**.
1. On the **Data** tab, click the **Row Fields** ellipsis (**…**) to
    display the **Data Mapping Field Collection Editor** again, click
    the **Add** button to display the **Entity** item.
    A new **Entity** displays in the **Members** pane of the editor.
1. In the **Entity properties** pane, click the **Name** ellipsis
    (**…**) to display the **Field Chooser** window.
1. In the **Field Chooser** window, scroll down to the **HTTP** node,
    expand it, and select the **HTTP.Operation.ContentType** field.
1. In the **Field Chooser** window, click the **Select** button to exit
    the dialog.
    
    The **ContentType** field displays as the **Name** property in the
    **ContentType properties** pane of the **Data Mapping Field
    Collection Editor**.
1. Click **OK** to exit the **Data Mapping Field Collection Editor**.
    
    Your new **HTTP Content Types Chart** displays each different HTTP
    content type as a separate horizontal bar in the **Bar Chart**
    visualizer component, with each bar representing the count of HTTP
    messages that carried the indicated **ContentType** payload, for
    example, image/gif, text/html, image/jpeg, and so on.
  
    To view the messages that correspond with the different content
    types, double-click any bar and the messages display in a separate
    **Analysis Grid** viewer tab.
1. Save your existing **Chart** configuration by clicking the **Save
    Chart** command in the **Charts** submenu that appears in the global
    Message Analyzer **Session** menu.
  
    Your new **Chart** appears in all of the locations described in
    [Built-In Chart Data
    Viewers](https://technet.microsoft.com/library/dn281863.aspx#BKMK_Charts),
    from where you can select the **Chart** as required for simple HTTP
    analysis.
1. To edit your new **Chart** at any time, select it from the **New
    Viewer** drop-down list against a set of trace results and then
    click the **Edit Chart** item in the **Charts** submenu that appears
    in the global Message Analyzer **Session** menu.
    
    Your **Chart** enters the edit mode and the data entry tabs appear
    to the right of the **Chart** visualizer surface. From here, you can
    modify your **Chart** settings with the use of the **Add
    Component**, **Remove Component**, and **New Data Mapping** commands
    from the **Charts** submenu that appears in the global **Session**
    menu. Note that you can also modify settings directly from the data
    entry tabs.