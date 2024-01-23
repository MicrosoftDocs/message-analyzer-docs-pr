---
title: "Enabling and Disabling Message Analyzer Aliases | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14a9abff-3a38-4a72-b61d-b11ecf38488a
caps.latest.revision: 20
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Enabling and Disabling Message Analyzer Aliases

You can enable or disable any **Alias** by toggling (selecting/unselecting) the appropriate check box in the **Aliases** drop-down list in the global Message Analyzer **Tools** menu or on the global toolbar. You can either enable each **Alias** one at a time, or you can enable one or more **Categories** that each contain multiple **Aliases** at once. When you enable one or more **Aliases** by selecting them, the current message set will be updated such that all data field values that are represented by the **Alias** configurations will be replaced by the **Alias** names. When you disable one or more **Aliases** by unselecting them, each **Alias** is removed from all previously set instances in the current message set that is displayed in the **Analysis Grid** and other viewers. However, each disabled **Alias** is still retained in the **Aliases** drop-down list until such time that you delete it.  
  
> [!NOTE]
>  The scope of **Alias** application encompasses all data viewers and sessions displayed in the current running instance of Message Analyzer, which in this context is referred to as the current message set.  
  
 Whenever you enable or disable an existing **Alias**, you are prompted by an **Aliases Changed** information bar that contains the following advisory message:  
  
 “**To avoid excessive CPU utilization when refreshing some data views, please wait until all alias changes are complete before you refresh.**”  
  
 When this information bar displays, you have the option to refresh your data viewers at the appropriate time by clicking the **Refresh Views** button on the bar.  
  
> [!NOTE]
>  If you enable an **Alias** that has a **Value** that matches that of another enabled **Alias**, Message Analyzer displays a **Duplicated value** message. When this occurs, you will be unable to apply the duplicate **Alias**.  
  
## Using the Built-In Alias Collection Items  

 Message Analyzer provides the following **Aliases** by default in the **My Items** category of your **Aliases** asset collection, which are accessible from the **Aliases** drop-down list in the previously specified locations. You can use these **Aliases** as is, for the convenience of friendly and quick identification of loopback traffic:  
  
-   **IPv4 Loopback** — provides a friendly name for the IPv4 address `127.0.0.1`, which is a special IP number that is designated for the software loopback interface on your machine.  
  
-   **IPv6 Loopback** — provides a friendly name for the IPv6 address `::1`, which is a special IP number that is designated for the software loopback interface on your machine.  
  
 > [!NOTE]
 >  A loopback interface is not associated with any hardware, nor is it physically connected to a network. Rather, the interface is a conduit for local application traffic, for example, between a local web server and a SQL server.  
  
 You can also modify and save any of the default **Alias** collection items as necessary, as described in [Modifying Message Analyzer Aliases](modifying-message-analyzer-aliases.md).  You can also share **Aliases** with others, including the default **Aliases**, by using the **Manage Aliases** dialog as described in [Managing Message Analyzer Aliases as Shared Items](managing-message-analyzer-aliases-as-shared-items.md).  
  
## Specifying a Default Alias List  

 If you want to specify a default set of **Alias** names to apply to all message data that you either capture in Live Trace Sessions or load into Message Analyzer through Data Retrieval Sessions, you can simply enable those **Alias** names that you want to automatically apply. You might consider creating a custom **Category** of **Aliases** that will serve as the default set, while manually enabling and applying other **Aliases** as needed. The default set of enabled **Aliases** will persist across Message Analyzer sessions, viewers, and restarts.  
  
> [!NOTE]
>  For a given data field type that is associated with a particular **Alias**, for example, a port or address type, you cannot apply another **Alias** asset with the same **Value** to a message set, although multiple **Alias** assets with the same **Value** can exist in your **Aliases** collection. However, you can only enable and apply **Aliases** with duplicate **Values** one at a time.