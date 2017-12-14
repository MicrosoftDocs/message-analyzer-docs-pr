---
title: "Performing a Live Capture | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 440b6609-58d4-4669-8744-9bc814818417
caps.latest.revision: 27
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Performing a Live Capture
This topic describes several methods that you can use to perform a live capture with Message Analyzer. It also describes how to stop, pause, resume, or restart a Live Trace Session.  
  
## Methods for Starting a Live Trace Session  
 The first two methods in the list that follows require no initial configuration, which allows you to start a Live Trace Session with as little as a single click. The third method allows you to create a custom capture configuration before you start a Live Trace Session, which is a little more involved.  
  
-   **Start Local Trace** — click the **Start Local Trace** button on the Message Analyzer **Start Page**. Use this method to instantly start a trace that runs on your local computer and captures packets from the network with the **Microsoft-PEF-NDIS-PacketCapture** provider or the **Microsoft-Windows-NDIS-PacketCapture** provider, depending on the operating system that is running on the local computer, as described by the table in [Built-In Trace Scenarios](built-in-trace-scenarios.md).  
  
-   **Favorite Scenarios** — click a **Favorite Scenario** on the Message Analyzer **Start Page**. Use this method to select one of the following default **Favorite Scenarios** and instantly start capturing data at the Data Link Layer, Transport Layer, or Application Layer, respectively:  
  
    -   **Local Network Interfaces** — uses the **Microsoft-PEF-NDIS-PacketCapture** provider on computers running the Windows 7, Windows 8, or Windows Server 2012 operating system. Uses the **Microsoft-Windows-NDIS-PacketCapture** provider on computers running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system.  
  
    -   **Loopback and Unencrypted IPSEC** — uses the **Microsoft-PEF-WFP-MessageProvider** for any supported operating system that is running on the local computer.  
  
    -   **Pre-Encryption for HTTPS** — uses the **Microsoft-Pef-WebProxy** and Fiddler providers for any supported operating system that is running on the local computer.  
  
     You will find each of the  above **Trace Scenario** Favorites by performing any of the following actions:  
  
    -   Click the Message Analyzer **File** menu, point to the **Favorite Scenarios** item, and then select one of the above scenarios in the submenu that appears.  
  
    -   Click the **Favorite Scenarios** drop-down list on the Message Analyzer global toolbar, and then select one of the above scenarios.  
  
    -   Click one of the scenarios in the **Favorite Scenarios** list on the **Start Page**.  
  
        > [!TIP]
        >  To add more scenarios to the **Favorite Scenarios** list, which includes other built-in **Trace Scenarios** and any custom scenarios that you have created, click **Edit Favorites** on the **Start Page** to display the **Edit Favorites** dialog. From this dialog, configure a **Trace Scenario** as a Favorite and add it to the **Favorite Scenarios** list by clicking the white star next to a **Trace Scenario**, at which time the white star changes to the color yellow and the **Favorite Scenarios** list is updated to include the new Favorite that you are adding. The update is then reflected in the previously indicated locations where you can access the **Favorite Scenarios** list.  
  
-   **New Session** dialog — click the **Start** button in the **New Session** dialog. Use this method to create the capture configuration for a Live Trace Session prior to starting it. You could configure a session simply by selecting a particular **Trace Scenario** and then starting the session. Optionally, you can customize the capture configuration first with selected system ETW providers; with filtering configurations that can include a **Fast Filter**, **Session Filter**, **Parsing Level**, and an event **Keyword** bitmask or error **Level** filter; with advanced host adapter and/or switch adapter filters; by specifying a data viewer; and so on. If you want to create unique capture configurations that are tailored to your environment or other requirements, this is the method you will use most often.  
  
    > [!NOTE]
    >  After you create a custom capture configuration for a Live Trace Session, you can save the configuration as a new user **Trace Scenario**. It will then appear in the **My Items** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog, as described in [Saving Trace Scenarios](saving-trace-scenarios.md). You can then run the scenario on demand. Note that you can fully edit or delete any **Trace Scenarios** that you created, whereas, this is not possible for any of the built-in **Trace Scenarios** that install with Message Analyzer.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about how to create a unique capture configuration for a Live Trace Session, see [Configuring a Live Trace Session](configuring-a-live-trace-session.md).   
___________________\_  
  
<a name="BKMK_StopPauseRestartSession"></a>   
## Managing Session Stop, Pause, Resume, and Restart  
 While a Live Trace Session is in progress, you have the option to Pause the session by clicking the **Pause/Resume** button on the global Message Analyzer toolbar. You might do this at a point in time where you need to manually trigger some process, application, or event for which you want to capture messages. Immediately after you initiate such a trigger, you can resume the Live Trace Session by clicking the **Pause/Resume** button again.  
  
 When your data capture is complete, you can Stop the Live Trace Session by clicking the **Stop** button on the global Message Analyzer toolbar.  In addition, for any Live Trace Session that is Stopped, you can Restart the session by clicking the **Restart** button on the global Message Analyzer toolbar. Note that you cannot Restart a session that is in the Paused state, as you can only Resume or Stop a session that is Paused. Also be aware that when you Restart a Live Trace Session, all existing captured data will be lost unless you save it before restarting.