---
title: "Creating Message Analyzer Aliases | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 18c92a62-c954-4022-830d-c7c26b7673bd
caps.latest.revision: 26
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Creating Message Analyzer Aliases

Message Analyzer enables you to create an alphanumeric string value **Alias** for any data field value in the **Analysis Grid** viewer that is of a type that supports aliasing, as described in [Using and Managing Message Analyzer Aliases](using-and-managing-message-analyzer-aliases.md). You can create an **Alias** for only one data field value at a time; however, you can only create an **Alias** from the **Analysis Grid** viewer, as there are no other facilities to create one. Note that you can apply any alias while Message Analyzer is capturing data in a Live Trace Session or loading messages through a Data Retrieval Session.  
  
---  
  
 **Go To Procedure**   
To go directly to a procedure that creates an **Alias**, see [Create an Alias for a Data Field Value](procedures-using-the-data-viewing-features.md#BKMK_CreateAlias). However, you are advised to examine the information contained in this section before doing so.  

---  
  
## Enforcing Unique Alias Values  

 Message Analyzer enforces the restriction that the **Value** of each *applied* **Alias** must be unique. However, if you create an **Alias** and its **Value** matches that of another **Alias**, and you **Save** it, Message Analyzer simply adds that **Alias** to the **Aliases** drop-down list on the global Message Analyzer toolbar and to the **Aliases** submenu that is accessible from the global Message Analyzer **Tools** menu, and then sets it to the disabled state, while preventing it from being applied to the current message set. If you attempt to enable this **Alias**, Message Analyzer blocks application of the **Alias** and displays a **Duplicated value** message to indicate the inherent restriction. Even though this is a restriction, it does give you the flexibility to create multiple **Aliases** with different names for the same **Value**; however, you can only enable and apply them one at a time.  
  
> [!NOTE]
>  Note that although it is possible to create multiple aliases with the *same* name but with different **Values**, this is probably not the best use of this feature, except perhaps for multiple IP addresses that your computer may have.  
  
## Configuring an Alias  

 To configure an **Alias** for a particular data field value in a set of trace results, right-click a field value in the **Analysis Grid** viewer that supports aliasing, for example, an IP address in the **Source** column, and then select the **Create 'Source' Alias** context menu item. Thereafter, the **Alias Editor** dialog appears and enables you to specify the values or settings that follow:  
  
> [!NOTE]
>  The **Create ‘\<columnName>’ Alias**  menu item is enabled only for data field values that support aliasing. In addition, after you create a new **Alias**, the **Create ‘\<columnName>’ Alias** menu item for the new **Alias** will be grayed-out and disabled (if you right click the new **Alias**) until such time that you delete the existing **Alias** from the **Aliases** drop-down list. Note that the value *‘\<columnName>’* is the name of the **Analysis Grid** viewer column that contains data that is of a type that currently supports aliasing, for example, the **Destination** column that contains IP addresses.  
  
-   **Value** — the value of the data field that you right-clicked in the **Analysis Grid** viewer to create a new **Alias** is automatically passed in to the **Value** text box. For example, this could be an IP address or a TCP port number. This field is editable but cannot be blank, although Message Analyzer performs a validation that determines whether the entered value is correct for the field type.  
  
-   **Alias** — enter a friendly name for the new **Alias** in this text box. Specify a name that makes sense for your environment. This field is editable but cannot be blank; it should be between 1-64 characters long. Note that the alphanumeric string that you specify as the **Alias** name is automatically interpreted as a string in various Message Analyzer operations such as filtering, sorting, and grouping.  
  
-   **Description** — type a description of the new **Alias** in the **Description** text box, to define the usage context for future recollection and to notify users with whom you might share such an **Alias** asset, as the **Description** is included in the Message Analyzer sharing infrastructure. You also have the option to leave this text box blank.  
  
-   **Category** — in this text box, specify the name of the **Category** in which to store your new **Alias**. You can choose an existing **Category** that is populated in this combo box based on previously specified **Categories**, or you can create your own customized **Category** name, which is then retained as an editable **Category** drop-down list item for future use. Thereafter, you can simply select items from the **Category** drop-down menu as needed. If you create your own **Categories**, you might consider naming them by data types, for example, “IP Addresses”, MAC Addresses”, “TCP Ports”, and so on. All categories that you specify become subcategories that appear under the default **My Items** top-level category in the **Aliases** drop-down list. However, if you leave the **Category** combo box blank, the **Alias** will be stored directly in the **My Items** category.  
  
-   **Auto Refresh Views** — select this check box if you want Message Analyzer to refresh all data viewers that will be impacted by the new **Alias**, immediately after you **Save** the **Alias**.  
  
 > [!IMPORTANT]
 >  Be aware that the **Auto Refresh Views** function of the **Alias Editor** dialog can be activated only when creating a new **Alias**. It does not activate for other operations that you can perform, such as editing and saving an **Alias** or creating a copy of, modifying, and saving an **Alias**. In addition, when the current message set is refreshed to apply a newly created **Alias**, there could be an impact on performance depending on the number of messages that exist in the displayed message set.  
  
 If you do not select the **Auto Refresh Views** check box, and you **Save** the new **Alias**, Message Analyzer prompts you with the following message that displays on the **Aliases Changed** information bar above the **Analysis Grid** viewer:  

 “**To avoid excessive CPU utilization when refreshing some data views, please wait until all alias changes are complete before you refresh.**”  

 Thereafter, you have the option to manually click the **Refresh Views** button on the information bar at a time when it is appropriate to refresh your data viewers.  
  
When you are finished entering the **Alias** data in the **Alias Editor** dialog, click **Save** to store your new **Alias** in the specified category of the **Aliases** drop-down list. After adding the new **Alias** to your **Alias** collection, you can edit, make a copy, or delete the **Alias** at any time, as described in [Modifying Message Analyzer Aliases](modifying-message-analyzer-aliases.md).  
  
> [!NOTE]
>  Your Message Analyzer installation will save any **Aliases** that you create for use in subsequent sessions, however, **Aliases** do not persist in any data files that you save and share with others, such as a .matp trace file.