---
title: "Modifying Message Analyzer Aliases | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9adf7889-aec2-47c0-8b3a-6a150fa5e151
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Modifying Message Analyzer Aliases
If you want to modify an existing **Alias**, you will need to open the **Alias Editor** dialog, which is the same dialog that enables you to create a new **Alias**. To backtrack for a moment, when you *create* a new **Alias**, you access the **Alias Editor** dialog by right-clicking the field value of a data type in the **Analysis Grid** viewer that supports aliasing and then selecting the **Create ‘\<columnName>’ Alias** menu item to display the dialog. However, to *modify* an existing **Alias**, you can only use either of the following methods to open the **Alias Editor** dialog:  
  
-   Right-click an existing **Alias** in the **Aliases** drop-down list that is accessible from the Message Analyzer global **Tools** menu or the global toolbar, and then select the **Edit** item in the context menu that appears.  
  
-   Click the **Aliases** drop-down list and then click the **Manage Aliases** command. From the **Manage Alias** dialog that displays, right-click the existing **Alias** that you want to modify, and then select the **Edit** item in the context menu that appears.  
  
## Using the Context Menu Commands  
 Whenever you right-click an existing **Alias**, either in the **Aliases** drop-down list or in the **Manage Alias** dialog, the following commands are accessible from the context menu that displays:  
  
-   **Edit** — click this command to open the **Alias Editor** dialog, as previously indicated. The values and settings that you can specify in the **Alias Editor** dialog are described in [Creating Message Analyzer Aliases](creating-message-analyzer-aliases.md). Note that after you edit and **Save** changes to a currently enabled **Alias**, your modifications are automatically applied to the current message set, without Message Analyzer displaying the **Aliases Changed** information bar that prompts you to refresh data views. If you edit and **Save** changes to a currently disabled **Alias** (see [Enabling and Disabling Message Analyzer Aliases](enabling-and-disabling-message-analyzer-aliases.md)), your modifications are saved but they are not applied to the current message set until you manually select the **Alias** to enable it.  
  
-   **Create a Copy** — click this command to open the **Alias Editor**, where you can work with an exact replica of an existing **Alias**, to either **Save** as is or modify as necessary. By providing an **Alias** template, this command enables you to quickly create a new **Alias** based on similar data from an existing one. When you select the **Create a Copy** command and edit the copy of an existing **Alias**, the following guidelines may apply:  
  
    -   **Enforcing Unique Alias Values** — Message Analyzer enforces the restriction that the **Value** of each *applied*  **Alias** must be unique, as previously specified. However, if you **Create a Copy** of an **Alias** and modify it such that its **Value** matches that of another **Alias**, and you **Save** it, Message Analyzer simply adds that **Alias** to the **Aliases** drop-down list and sets it to the disabled state, while preventing it from being applied to the current message set. If you attempt to enable this **Alias**, Message Analyzer blocks application of the **Alias** and displays a **Duplicated value** message to indicate the inherent restriction.  
  
    -   **Saving Exact Alias Copies** — if you **Save** an **Alias** *copy* as-is, it is added to the **Aliases** drop-down list, but it is not enabled, again because Message Analyzer enforces the restriction that the **Value** of each **Alias** must be exclusive.  
  
    -   **Saving Edited Alias Copies** — if you modify a copied **Alias** and **Save** it with an **Alias** name that is different than any other **Alias** name, but its **Value** is the same as another existing **Alias**, the saved **Alias** is added to the **Aliases** drop-down list and is disabled. This gives you the flexibility to create multiple **Aliases** with different names for the same **Value**; however, you can only enable and apply them one at a time.  
  
         If you modify a copied **Alias** and **Save** it with an **Alias** name that is identical to an existing **Alias** name, but its **Value** is different than that of any other existing **Alias**, Message Analyzer adds it to the **Aliases** drop-down list in the disabled state. However, you can enable and apply this **Alias** by simply selecting it in the drop-down list, at which time Message Analyzer displays the **Aliases Changed** information bar to prompt you to refresh your data views. After you click the **Refresh Views** button on the information bar, the **Alias** is then applied to the current message set, which includes all sessions and viewers.  
  
-   **Delete** — click this command to permanently remove an **Alias** from the **Aliases** drop-down list. If you **Delete** an **Alias** that is the only one in a particular **Category**, the **Category** will be removed as well. Whenever you delete a currently enabled **Alias**, Message Analyzer displays the **Aliases Changed** information bar to prompt you to refresh your data views. After you click the **Refresh Views** button on the information bar, the **Alias** is then applied to the current message set, which includes all sessions and viewers.