---
title: "Modifying Unions | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aba2ae4a-d745-4b25-abff-16c69b886e28
caps.latest.revision: 27
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Modifying Unions
After you configure one or more **Unions** according to the instructions outlined in [Creating Unions](creating-unions.md), you have the option to modify, delete, or create a copy of any **Union** you have created. To do this, you can use the Message Analyzer  commands that appear in the **My Items** category of the **Manage Unions** dialog. These commands are available from the context menu that displays in the **Manage Unions** dialog whenever you right-click a **Union** in the **My Items** category of the dialog. You can access the **Manage Unions** dialog by clicking the **Unions** item on the global Message Analyzer **Tools** menu and selecting the **Manage Unions** item. To edit a **Union** in the **My Items** category, you must right-click the **Union** you want to edit and then select the **Edit** command from the context menu that appears. This action displays the **Edit Union** dialog from where you can modify the **Union**. The other commands in this context menu are **Create a Copy** and **Delete**, as described in the next section.  
  
## Commands for Modifying Unions  
 After you right-click a **Union** in the **My Items** category, you can make use of the following commands to modify it.  
  
-   **Edit** — click this command to open the **Edit Union** dialog, in which you can use the same controls to modify a **Union** that you use when creating a new **Union**, as described in [Creating Unions](creating-unions.md). The modifications that you can perform or effect from the **Edit Union** dialog are listed below.  
  
    -   **Edit a Union name** — edit a **Union** name by entering your changes in the **Name** text box.  
  
    -   **Change a Union category** — select a different category for the **Union** from the **Category** drop-down list, or enter a new category name in the **Category** combo box.  
  
    -   **Add fields to a Union** — click the **Add** button to open the **Field Chooser** **Tool Window**, from where you can add one or more fields, properties, or annotations to the **Union**, one at a time. Note that this action can result in a **Type** change.  
  
    -   **Remove fields from a Union** — highlight a field that you want to remove and click the **Remove** button to exclude it from the **Union**. This too can result in a **Type** change.  
  
    -   **Change message data** — if you add or remove fields, properties, or annotations in a **Union** that does not cause a corresponding **Type** change, and the **Union Name** also remains unchanged, this can result in an immediate update to the underlying message data in any active data viewer that uses the **Union**. This might include currently active viewers such as the **Analysis Grid** or **Chart** viewer. In addition, if a sort, group, or other operation is in progress when such a data change occurs, all active viewers will restart those operations. Lastly, you might observe that the **Change Union** dialog does not display in this case because a message data change is immediate and does not require a [Restarting Message Analyzer](modifying-unions.md#BKMK_MARestart).  
  
    > [!NOTE]
    >  If there is a change to a **Union** field, property, or annotation and there is also a **Type** or **Name** change involved, then the **Change Union** dialog displays to indicate the type of change that will be applied after Message Analyzer is restarted. The dialog also indicates that you should remove the **Union** from any Message Analyzer features that are configured to use it, for example, a Filter Expression or a Chart **Layout**. In addition, the dialog prompts you to continue or not, which you decide by clicking either the **Yes** or **No** button, respectively. Note that the previously existing **Union** name remains active and that the **Union** still functions normally until Message Analyzer is restarted.  
  
-   **Create a Copy** — click this command to open the **Edit Union** dialog that is automatically populated with a replica of the existing **Union** configuration. You can then modify the copy and **Save** it under a new **Union** name. By providing a **Union** template, this command enables you to quickly create a new **Union** based on similar data from an existing one. When working with a copy of an existing **Union**, the following guidelines apply:  
  
    -   **Saving a Union copy that matches an existing name** — if you try to **Save** a copy of an existing **Union** without changing its **Name** value, Message Analyzer displays a message to indicate that the **Union** name is already in use. Message Analyzer does not allow you to save such a **Union** because all **Union** names must be unique.  
  
    -   **Saving an edited Union copy** — if you modify a copied **Union** and **Save** it with a **Union** name that is different than any other **Union** name, Message Analyzer adds it to the **Unions** list in the **Manage Unions** dialog, whether or not a **Type** change has also occurred. The **Union** is also added to the **Field Chooser** window under the **Unions** node. Note that changes you make to a copied **Union** can include a **Type** change, for example, by adding or removing a field that causes a **Type** change.  
  
-   **Delete** — click this command to delete a **Union**.  
  
     The deleted **Union** is then removed from the **Unions** list in the **Manage Union** dialog, as it is no longer an editable or shareable asset. Note that any **Analysis Grid** viewer column that contains the **Union** name continues to persist. However, after the **Union** is removed at the next Message Analyzer restart, it will no longer be available from **Field Chooser** and therefore you will be unable to add it as a new data column in the **Analysis Grid** viewer. Until such time, you can continue to display and use the **Union** as needed.  
  
<a name="BKMK_MARestart"></a>   
## Restarting Message Analyzer  
 When you restart Message Analyzer, any changes that are queued up for one or more **Unions** will be applied. Note that any **Union** you delete in the **My Items** category of the **Manage Unions** dialog will be removed from the root **Unions** node in the **Field Chooser** window following a Message Analyzer restart.  
  
## Consumers of Changed Unions  
 If a changed **Union** is called by a Message Analyzer feature that uses the **Union** (for example, a Chart **Layout** formula or Filter Expression), Message Analyzer handles these situations within the context of existing functionality. For instance, if you attempt to create a Filter Expression that utilizes a **Union** that has had a **Name** change, or that you removed with the **Delete** command, an automatic compilation check that occurs before the filter is applied to a message set might display the **Compile Query Error** dialog. This dialog indicates that the Filter Expression failed to compile because the **Union** entity could not be found. Note that a similar process takes place for **Pattern Expressions**, which are also subject to a compilation check.  
  
> [!IMPORTANT]
>  If you have any Message Analyzer feature that uses a **Union** — for example, any type of **Layout** or Filter Expression — that has undergone a change in **Name**, **Type**, or is pending deletion, you are advised to manually remove such a **Union** from those features, as described in [Pending Changes](refreshing-data-views-containing-unions.md#BKMK_NoDataRefresh).  
  
## See Also  
 [Creating Unions](creating-unions.md)   
 [Refreshing Data Views Containing Unions](refreshing-data-views-containing-unions.md)