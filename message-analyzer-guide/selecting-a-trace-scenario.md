---
title: "Selecting a Trace Scenario | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f8c029a4-089f-454a-be0d-7c0568272a09
caps.latest.revision: 35
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Selecting a Trace Scenario
Message Analyzer provides the **Message Analyzer Trace Scenarios** asset collection Library which contains various built-in **Trace Scenarios**. These built-in scenarios typically expose common Message Analyzer usage scenarios that are optimized for capturing messages of specific types or at a particular network stack layer. They are all accessible by clicking the **Select Scenario** drop-down list on the **Live Trace** tab in the **New Session** dialog. You can also access any **Trace Scenario** that you have set to Favorite status in either of the following ways:  
  
-   Click the **Favorite Scenarios** item in the Message Analyzer **File** menu and then select a favorite scenario in the submenu that appears.  
  
-   Click a scenario in the **Favorite Scenarios** list on the Message Analyzer **Start Page**.  
  
 Note that whenever you select a **Trace Scenario** that has **Favorite** status, a Live Trace Session is immediately started with no additional session configuration required. This gives you a quick and convenient method for very quickly starting a Live Trace Session.  
  
## Setting Trace Scenarios as Favorites  
 You can set any **Trace Scenario** as a **Favorite Scenario** by clicking the **Edit Favorites** label on the Message Analyzer **Start Page**. When the **Trace Scenario** library displays, you can set a scenario as a Favorite by clicking the white star to the left of the scenario name, at which point, the star color changes to amber and the scenario is then added to the **Favorite Scenarios** list. You can undo the favorite status of any **Trace Scenario** by clicking the amber colored star, at which time the star color changes to white and the scenario is removed from the **Favorite Scenarios** list. You can also perform similar actions from the **Select Scenario** drop-down list in the **New Session** dialog.  
  
## Selecting a Built-In Trace Scenario  
 The built-in **Trace Scenarios** provide you with various predefined provider configurations in the following categories, as described in [Built-In Trace Scenarios](../messageanalyzer_content/built-in-trace-scenarios.md):  
  
-   **Network**  
  
-   **Device**  
  
-   **System**  
  
-   **File Sharing**  
  
 When you select a built-in **Trace Scenario** in any of these categories, the following items display in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog:  
  
-   The names of the providers used in the scenario and an associated GUID that identifies each one that appears in the **ETW Providers** list.  
  
-   A **Configure** link that enables you to access the **Advanced Settings** dialog that provides configuration settings on the following tabs:  
  
    -   **ETW Core** — contains event **Keyword** and **Level** filter settings for any ETW Provider associated with the scenario.  
  
    -   **Provider** — contains filter or other settings for any provider that is associated with the scenario, for example, the **Microsoft-Windows-NDIS-PacketCapture** provider or any **Microsoft-PEF** provider.  
  
    > [!NOTE]
    >  While the **Advanced Settings** dialog for **Microsoft-PEF** providers and the **Microsoft-Windows-NDIS-PacketCapture** provider will display both a **Provider** and **ETW Core** tab, most system ETW Providers that you add to Live Trace Session configuration from the **Add System Providers** dialog display an **ETW Core** tab only in the **Advanced Settings** dialog.  
  
## Selecting a Custom Configured Trace Scenario  
 If you select a custom created **Trace Scenario** template from the **My Items** category of the **Trace Scenarios** Library, all of the settings that you previously specified for the template are contained in your Live Trace Session configuration. This can include any combination of **Microsoft-PEF** providers, the **Microsoft-Windows-NDIS-PacketCapture** provider, system ETW Providers, event **Keyword** and error **Level** filter settings, **Fast Filters**, a **Session Filter**, a **Parsing Level**, advanced NDIS stack and Hyper-V-Switch extension layer filters, and so on. Note that you have the option to reconfigure and save any of these settings as required, before you run your custom **Trace Scenario** template again, as described in [Using a Custom Trace Scenario Template](../messageanalyzer_content/using-a-custom-trace-scenario-template.md).  
  
 After selecting a custom **Trace Scenario**, you have the option to either start capturing data immediately or to modify various provider settings and then start your Live Trace Session.  
  
## See Also  
 [Built-In Trace Scenarios](../messageanalyzer_content/built-in-trace-scenarios.md)