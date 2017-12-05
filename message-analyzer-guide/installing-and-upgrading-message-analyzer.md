---
title: "Installing and Upgrading Message Analyzer | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2511ee40-eabb-442b-bde1-e60cef5675f5
caps.latest.revision: 45
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Installing and Upgrading Message Analyzer
**Installing Message Analyzer for the First Time**   
If you have not already installed Microsoft Message Analyzer, go to the [Microsoft Message Analyzer](http://www.microsoft.com/en-us/download/details.aspx?id=44226) page on the **Microsoft Download Center** for a free download and installation of the latest version of Microsoft Message Analyzer. On this site, you will find details, new system requirements, brief installation instructions, and related resources such as **Known Issues** documentation and the Microsoft **Message Analyzer Operating Guide** in .pdf and .docx format. The Microsoft Message Analyzer release is available for installation in 32-bit and 64-bit versions. Installation requirements are listed in the table below for convenience.  
  
### Table 1. Message Analyzer Installation Requirements  
  
|Component|Requirement|  
|---------------|-----------------|  
|Supported Operating Systems|**32-bit and 64-bit**: Windows 7, Windows 8, Windows 8.1, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and Windows 10.|  
|Redistributable Packages|**Minimum** — .NET Framework 4; **Recommended** — .NET Framework 4.5|  
|Display Resolution|1024 x 768 or higher|  
|Hard Disk Space|**Installation** — Minimum: 350 MB<br /><br /> **Capturing and loading traces** — Recommended: 50 GB|  
|RAM|**64-bit** — Minimum: 2 GB; Recommended: 8 GB<br /><br /> **32-bit** — Minimum: 2 GB; Recommended: 4 GB|  
|CPU|**Minimum** — 1.4 GHz, **Recommended** — 2 x 2.80 GHz (64-bit)|  
  
> [!IMPORTANT]
>  If you intend to perform long captures or load large traces, it is recommended that you use a 64-bit computer. Also, given that some Message Analyzer operations are CPU intensive, for example when filtering is  combined with parsing, it is recommended that you use a dual-core processor for best performance.  
  
> [!CAUTION]
>  If you are installing Message Analyzer on a Windows 7 computer, you might experience a random reset of the TCP stack and a TCP connection loss. If this impacts an application, you may have to restart it. Otherwise, there is a possibility that you might have to restart your computer.  
  
> [!NOTE]
>  If you are installing Message Analyzer on a Windows 10 computer, the Windows Filtering Platform (WFP) message provider (Microsoft-PEF-WFP-MessageProvider) is installed as part of the operating system; therefore, the Message Analyzer installer (.msi) no longer installs this component. However, for all other supported down-level computers, such as Windows 8, the WFP message provider is installed with the Message Analyzer .msi application that you run from the download site. On Windows 10 computers, you can use this provider to conveniently capture traffic above the IP/Network Layer, which includes HTTP traffic, while removing lower-layer noise. Since the WFP provider is native to the Windows 10 operating system, you will not have to install any additional software to capture such traffic. To learn more about capturing this traffic on Windows 10 computers, see the WFP message provider PowerShell cmdlets on the TechNet [Windows and Windows Server Automation with PowerShell](https://technet.microsoft.com/en-us/library/dn249523.aspx) site.  
  
 **Upgrading an Existing Message Analyzer Installation**   
If you already have a Message Analyzer installation in place and you want to upgrade to the latest product version, read the **Warning** below and then proceed to [Upgrading Message Analyzer](installing-and-upgrading-message-analyzer.md#BKMK_UpgradeMessageAnalyzer).  
  
> [!WARNING]
>  If you have Message Analyzer v1.0 (RTM) or later currently installed, it will be detected by the Message Analyzer installer application, in which case, you will be offered an **Upgrade** option. When you perform an upgrade, your existing Message Analyzer installation is removed, along with certain user assets you might have created, which includes any custom OPN parsers and OPN configuration files for text logs that are stored in the **OPNs** and **TextLogConfiguration\DevicesAndLogs** folders, respectively, under the following directory: `%LocalAppData%\Microsoft\MessageAnalyzer\OPNAndConfiguration\`. Moreover, if you happen to have a Message Analyzer beta version installed, you will need to manually remove it prior to upgrading Message Analyzer. When performing an uninstall in this case (from **Programs and Features** in **Control Panel**), you will also lose the aforementioned assets that you have created. Therefore, before you upgrade or manually uninstall a beta version of Message Analyzer, see [Preserving User Created Assets Prior to Message Analyzer Installation](installing-and-upgrading-message-analyzer.md#BKMK_PreservingUserAssets) to learn how to avoid the loss of user data.  
  
<a name="BKMK_UpgradeMessageAnalyzer"></a>   
## Upgrading Message Analyzer  
 You may need to reinstall Message Analyzer, or you might simply want to upgrade to the latest Message Analyzer version  to take advantage of recent changes and improvements. When you perform the Message Analyzer upgrade, you have the option to allow the Message Analyzer installer to detect your existing Message Analyzer v1.0 or later installation and offer the **Upgrade** option. However, you also have the option to perform a clean installation by manually uninstalling your existing version from **Programs and Features** in **Control Panel** before you run the Microsoft installer from the [Microsoft Message Analyzer](http://www.microsoft.com/en-us/download/details.aspx?id=44226) page on the **Microsoft Download Center**. Also, you will definitely need to perform a clean installation if your existing Message Analyzer installation is a beta version, in which case the Microsoft Message Analyzer installer does not provide the **Upgrade** option. For this reason, you must be sure to manually uninstall your Message Analyzer beta version in the previously indicated manner prior to reinstalling from the **Download Center**.  
  
> [!IMPORTANT]
>  Whether you manually uninstall Message Analyzer prior to reinstallation or if you perform an upgrade, ***all binaries and data are removed***, which might include some user-created assets, depending on where they are located, as described in [Preserving User Created Assets Prior to Message Analyzer Installation](installing-and-upgrading-message-analyzer.md#BKMK_PreservingUserAssets)  
  
<a name="BKMK_PreservingUserAssets"></a>   
## Preserving User Created Assets Prior to Message Analyzer Installation  
 Whether you need to manually uninstall Message Analyzer prior to reinstallation or if you will perform the **Upgrade** process, be sure to first back up any custom OPN parsers that exist in the default OPN parser directory indicated in the list that follows, as this user data will be lost. This applies equally to any OPN configuration files for text logs that you have created and stored in their default location, also described in the list that follows. The only exception to this loss of data is if you have saved your custom OPN parsers and configuration files to a user-defined directory location, in which case they will not be deleted by a new installation of Message Analyzer. When your new Message Analyzer installation is complete, restore your custom OPN parser and OPN configuration files to the default directory locations so that Message Analyzer can locate and load them during application startup. The default directories are included in the list that follows:  
  
-   **Default OPN Parser directory** — the default location that Message Analyzer searches to load the default OPN parsers at startup is the following:  
    `%LocalAppData%\Microsoft\MessageAnalyzer\OPNAndConfiguration\OPNs\`  
    You can place all user-defined OPN parsers in this location and Message Analyzer will load them during startup; however, note that all parsers in this location will be overwritten if you manually uninstall/reinstall or **Upgrade** Message Analyzer.  
  
    > [!IMPORTANT]
    >  Please note that if you modify a default OPN parser in this directory, you will lose your changes when performing a new Message Analyzer installation. You will also lose your changes if an **OPN Parser** package that contains such a parser is set to auto-sync on the **Settings** tab of the **Start Page** in your current Message Analyzer installation and an update is pushed out by the sharing infrastructure. To avoid the possible loss of data in these circumstances, make a copy of the default OPN parser you wish to modify, rename it, and place it in a user-specified directory location, as described immediately below.  
  
    > [!NOTE]
    >  You also have the option to change the default OPN parser directory path that Message Analyzer uses, as specified in [Message Analyzer Startup Options](message-analyzer-startup-options.md).  
  
-   **User-specified OPN Parser directory** — you can define an additional path that Message Analyzer will include when searching for OPN parsers to load during startup, as described in [Message Analyzer Startup Options](message-analyzer-startup-options.md). In this case, you will need to start Message Analyzer from the command line and use the following switch to define the additional directory path:   
    `/OPNLoadPathMerge=<path>`  
    You can store all your custom OPN parsers in this location to prevent them from being deleted or overwritten.  
  
-   **Default OPN Configuration files for text logs directory** — the single, default location in which Message Analyzer searches for text log configuration files is the following:  
    `%LocalAppData%\Microsoft\MessageAnalyzer\OPNAndConfiguration\\TextLogConfiguration\DevicesAndLogs\`  
    You can place all custom OPN configuration files for parsing text logs that you create in this directory location;  note, however, that all configuration files in this location will be overwritten by a new Message Analyzer installation. The configuration files will also be overwritten if you have the **Device and Log File Version 1.3** asset package set to auto-sync on the **Settings** tab of the Message Analyzer **Start Page** and an update is pushed out by the sharing infrastructure.  
  
    > [!CAUTION]
    >  To avoid this loss of data, you are strongly advised to make a separate backup of any OPN configuration files for parsing text logs that you have created.  
  
> [!NOTE]
>  All other *user-created* assets such as **Filters**, **Charts**, **Aliases**, **Color Rules**, **View Layouts**, and so on, are stored in the following directory:  
> `%AppData%\Microsoft\MessageAnalyzer\My_Items\`  
> This location is not impacted by Message Analyzer upgrades.  
  
## Message Analyzer Window Docking Layout  
 Message Analyzer now uses a versioned docking layout configuration file to keep track of the locations in which you dock various windows in the user interface (UI), for example, the **Tool Windows**. When you shut down the Message Analyzer application, the file is updated with information for the current window docking configuration. This tracking enables you to maintain a consistent window layout in the UI across every Message Analyzer restart in the same installation. The configuration file is located in the following directory:   
`%LocalAppData%\Microsoft\MessageAnalyzer\app.WindowLayoutAsset.cfg`  
  
 When you perform an upgrade to the latest version of Message Analyzer, any existing docking layout configuration file in this location will be overwritten by a new default docking layout configuration file that comes with the your upgrade installation. As a result, you will lose your old window docking layout configuration in the Message Analyzer UI.  
  
## Installing Message Analyzer From the Command Line  
 You have the option to run the Message Analyzer installer (.msi) from the command line. To do this, you will need to save the .msi from the Microsoft Download site, rather than run it. After you save it, you can execute the following command at a command prompt to install Message Analyzer:  
`msiexec /i MessageAnalyzer.msi`  
  
 One reason that you might want to install Message Analyzer from the command line is that you can create an installation log, which can provide information about the install if you are having any issues:  
`msiexec /i MessageAnalyzer.msi /l* <logfilePath>`  
  
 To review additional installation options, see the msiexec help by running the following command string at a command prompt:  
`msiexec /?`  
  
<a name="BKMK_StartingMAFirstTime"></a>   
## Starting Message Analyzer for the First Time  
 When you are ready to start Message Analyzer for the first time, go to  the **Start** menu, **Start** page, or task bar of your computer and click the **Microsoft Message Analyzer** icon to launch Message Analyzer. For example, on computers running the Windows 10 operating system, click the **Start** page and type the text "Message Analyzer" to display the **Message Analyzer** program icon. To ensure that you will have access to all the critical Message Analyzer features and capabilities, start Message Analyzer in administrative mode by right-clicking its icon and then selecting the **Run as administrator** option.  
  
 However, if you are starting Message Analyzer immediately after installing it, you should log off and back onto your computer first, and then start Message Analyzer as indicated. This action ensures that in all subsequent logons following installation, your security token will be updated with the required security credentials from the Message Capture Users Group (MCUG) so that you can capture network traffic in **Trace Scenarios** that use the **Microsoft-PEF-NDIS-PacketCapure** provider, **Microsoft-Windows-NDIS-PacketCapture** provider, and the **Microsoft-PEF-WFP-MessageProvider**.  
  
 Note also that when you start Message Analyzer for the first time, you will be prompted to opt in or out of automatic asset updates from a dedicated Microsoft web service, as described in [Syncing Message Analyzer Assets for Automatic Updates](installing-and-upgrading-message-analyzer.md#BKMK_SyncingAssets) below.  
  
 **Security Contexts and Restrictions**   
You should also be aware that when you run Message Analyzer in the administrative mode, it can result in varying security contexts between applications. For example, this means that you will be unable to use the Message Analyzer drag-and-drop feature to open saved trace and log files while running in administrative context.  
  
> [!IMPORTANT]
>  Even if you log off your system, log back on, and receive the required security credentials from the MCUG, you will still need to use the **Run as administrator** option if you want to capture message traffic in Message Analyzer **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider or the **Microsoft-PEF-WFP-MessageProvider**, which both have remote capabilities. Because of the inherent remote capabilities of these message providers, security restrictions must be applied.  
  
 **Syncing Message Analyzer Assets for Automatic Updates**   
The first time that you start up Message Analyzer, you have the option  to configure the Automatic update of Message Analyzer assets, such as **Filters**, **Trace Scenarios**, **Viewpoints**, **Chart** viewer **Layouts**, and so on. If you opt in to automatic updates, no further action is required, as the update process occurs silently in the background whenever you start up Message Analyzer and asset updates are available. If you do not opt in, then the asset versions that install with the latest version of Message Analyzer will not be updated by the Microsoft web service that handles the installation of such asset versions. However, you can set any asset collection or all of them to the auto-sync state anytime thereafter with the use of the **Asset Manager** dialog.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about syncing Message Analyzer assets for automatic updates at first startup, see [Syncing Items on First Startup](syncing-items-on-first-startup.md).  
**To learn more** about the **Asset Manager** dialog, see the [Asset Manager](asset-manager.md) topic.  
___________________\_  
  
## See Also  
 [Quick Session Startup](quick-session-startup.md)