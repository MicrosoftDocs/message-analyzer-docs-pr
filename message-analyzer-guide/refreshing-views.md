---
title: "Refreshing Views | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b4c2a31-0d5d-4217-a70c-60667b6bb2d1
caps.latest.revision: 19
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Refreshing Views
There are several **Alias** operations that you can perform that will trigger a refresh of message data that is displayed in Message Analyzer. In at least one case, the trigger is automatic and in others it is in response to a particular action. These triggers are described in the list that follows:  
  
-   **Modifying an applied Alias** — if you edit the **Value** of an **Alias** or its name while it is in an enabled state and you save it, Message Analyzer automatically performs a refresh of the current message set.  
  
-   **Enabling/applying an Alias** — whenever you enable a previously disabled **Alias** by selecting its check box, Message Analyzer displays the **Aliases Changed** information bar above the **Analysis Grid** viewer to prompt you to refresh your data views. The information bar also displays the advisory message that is described in earlier topics of this section.  
  
-   **Disabling an Alias** — whenever you disable a previously enabled **Alias** by unselecting its check box, Message Analyzer displays the **Aliases Changed** information bar above the **Analysis Grid** viewer to prompt you to refresh your data views.  
  
-   **Deleting an Alias** — whenever you delete an **Alias**, Message Analyzer displays the **Aliases Changed** information bar above the **Analysis Grid** viewer to prompt you to refresh your data views.  
  
 When any of the previously specified actions occur, Message Analyzer performs a global refresh of the current message set, which includes every session and viewer in the current Message Analyzer instance, including **Layouts** for the **Chart** viewer. The global refresh will also pertain to various Message Analyzer operations that are impacted by application of the **Alias**, such as any applied grouping, sorting, filtering, color rule, or find operation in a viewer where the **Alias** is in use.  
  
## Removing the Aliases Changed Information Bar  
 After the information bar displays, you can remove it in the following ways:  
  
-   **Perform a view refresh** — click the **Refresh Views** button to update the current message set with changes that you specified.  
  
-   **Remove the changes that you specified** — this applies to modifying, enabling, or disabling an **Alias** only. For example, if you edited an **Alias**, removing the changes would mean to undo the edits. In the case of enabling or disabling an **Alias**, it would mean to undo those actions.  
  
-   **Remove the information bar** — click the **X** button on the right side of the information bar to remove it. Note that if you click this button to remove the information bar, it may display again the next time Message Analyzer checks for changes to an **Alias**, at which point the previous update will be detected.  
  
> [!NOTE]
>  The **Aliases Changed** information bar also contains a **Show History/Output Window** icon that enables you to display the **Output** **Tool Window**. The  **Output** window keeps track of various Message Analyzer operations, including installation events, for informational purposes.