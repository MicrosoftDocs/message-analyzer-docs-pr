---
title: "Creating and Modifying Color Rules | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a06dc163-f447-4054-b066-e664aa7c5a8c
caps.latest.revision: 33
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Creating and Modifying Color Rules

Message Analyzer enables you to create new **Color Rules** of your own design or you can modify existing ones. Message Analyzer provides an **Example Color Rules** item under **My Items** in the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar that you can modify however you want for practice purposes, so you can begin familiarizing yourself with **Color Rule** features and functions. After you create a new **Color Rule** or modify an existing one, you can add it to an existing **Category** or populate it to a new **Category** that you define for your local **Message Analyzer Color Rules** asset collection Library. You can perform these operations by using the **Edit Color Rule** dialog, which is accessible in each of the following ways:  
  
-   By selecting the **New Color Rule** item from the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar. Note that this drop-down list is also available from the global Message Analyzer **Session** menu, but only when an **Analysis Grid** viewer tab has focus.  
  
-   By right-clicking a default **Color Rule** in a **Category** of your local rule Library and selecting the **Create a Copy** item in the context menu that displays.  
  
-   By right-clicking a **Color Rule** in a **Category** from within the **Manage Color Rules** dialog. This dialog is accessible by selecting the **Manage Color Rules** item from the **Color Rules** drop-down list in the previously specified locations.  
  
    > [!NOTE]
    >  If you configure a new **Color Rule** from the **Manage Color Rules** dialog by creating a copy of an existing rule and modifying it, or if you directly modify an existing rule, the changes will be added to your local **Color Rule** asset collection Library.  
  
> [!CAUTION]
>  You cannot use the **Edit Color Rule** dialog to modify any of the built-in **Color Rules** that are provided by default with every Message Analyzer installation.  
  
<a name="BKMK_CreatingNewColorRules"></a>   
## Creating New Color Rules  
 To create a new **Color Rule** with the **Edit Color Rule** and to specify a **Category** in which to place it, you will need to do the following:  
  
-   Open the **Edit Color Rule** dialog by selecting the **New Color Rule** item from the **Color Rules** drop-down list on the **Analysis Grid** viewer toolbar.  
  
-   Enter a name for the new **Color Rule** in the **Name** text box.  
  
-   Optionally describe the purpose of the **Color Rule** in the **Description** text box.  
  
-   Specify the **Category** that you want to contain the new rule, either by selecting an existing item from the drop-down menu of the **Category** combo box, or by typing a new category name in the **Category** combo box.  
  
-   Specify a Filter Expression for the new **Color Rule**.  
  
     To do this, you can manually configure a filter by entering the Filter Expression text directly in the filter text box below the **Edit Color Rule** dialog toolbar, or you can select a built-in Filter Expression from the centralized **Message Analyzer Filters** asset collection **Library**. If you want to manually configure a Filter Expression, the Filter IntelliSense service is available to provide statement completion assistance.  
  
 > [!NOTE]
 >  Whether you specify a manually configured Filter Expression or you modify one of the predefined expressions from the centralized **Library**, Message Analyzer automatically validates that the expression properly compiles when you attempt to **Save** the **Color Rule**. If the filter expression does not compile, you will be unable to save the new **Color Rule**.  
  
-   Configure the decoration scheme for the new **Color Rule** by using the controls in the **Style**, **Weight**, **Lines**, and **Colors** panes of the **Edit Color Rule** dialog. As you modify the **Color Rule** decoration scheme, the configuration is displayed in the **Preview** pane at the bottom of the **Edit Color Rule** dialog.  
  
     For each **Color Rule** you create, be sure to specify a unique decoration and text scheme that will readily convey its status to you as a warning, reminder, or diagnostic alert. **Color Rule** decoration schemes consist of a combination of the following visual components:  
  
    -   **Foreground** (text), **Gradient Background**, and **Background** colors.  
  
    -   **Normal**, **Italic**, and **Oblique** text styles.  
  
    -   **Normal** and **Bold** font styles.  
  
    -   **Normal**, **Underline**, **Strikethrough**, and **Overline** line text decorations.  
  
-   Create the new **Color Rule** and **Category** (if you specified one) by clicking the **Save** button in the **Edit Color Rule** dialog.  
  
 > [!NOTE]
 >  After you save a new **Color Rule** or an edited one, it is automatically applied to the current message collection displaying in the **Analysis Grid** viewer.  
  
## Modifying Color Rules  

 Message Analyzer enables you to modify, delete, or create a copy of any **Color Rule** under the **My Items** node only, in the **Color Rules** drop-down list. This includes the **Example Color Rule** that is provided for practice purposes. You can also **Create a Copy** of any predefined **Color Rule**, modify it, and then **Save** it, but you cannot directly modify a predefined **Color Rule** that is provided by default with Message Analyzer. The commands to perform these operations are available as the following context menu items, which display as appropriate for the category node in which you right-click a **Color Rule**:  
  
-   **Edit** — available for **Color Rules** under the **My Items** node only. Displays the **Edit Color Rule** dialog, from where you have access to the **Color Rule** configuration described in [Creating New Color Rules](creating-and-modifying-color-rules.md#BKMK_CreatingNewColorRules).  
  
-   **Create a Copy** — available for **Color Rules** under the **Message Analyzer** and **My Items** category nodes. Displays the **Edit Color Rule** dialog, from where you can copy an existing **Color Rule**, for example, into a different **Category**. You can also reconfigure the copy as a new rule and place it in a **Category** of choice, which is tantamount to creating a new rule.  
  
-   **Delete** — available for **Color Rules** under the **My Items** node only. Removes a single selected **Color Rule** under the **My Items** node.  
  
When you modify a **Color Rule**, for example, to specify a different decoration scheme or filtering configuration, you are using the same **Edit Color Rule** dialog with which you create new **Color Rules**.  
  
> [!TIP]
>  It is advisable to create a backup of your local **Color Rule** Library asset collection, so that you can always restore any custom rules you may have deleted under the **My Items** category of your **Message Analyzer Color Rules** asset collection Library.  
  
---  
  
**More Information**   
**To learn more** about managing **Color Rule** items, including sharing them with others, see [Managing Color Rules](managing-color-rules.md).   
**To learn more** about Filter Expressions, see [Writing Filter Expressions](writing-filter-expressions.md) and the [Filter IntelliSense Service](filter-intellisense-service.md) topic.  

---