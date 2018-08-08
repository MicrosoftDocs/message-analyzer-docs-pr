---
title: "Automating Tracing Functions with PowerShell | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56fca5fb-8fa3-4fea-a3b2-9435547f823e
caps.latest.revision: 61
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Automating Tracing Functions with PowerShell

At times, it may be advantageous for you to automate certain Message Analyzer functions that enable you to do the following:  
  
-   Utilize enhancements to the manner in which you start and stop traces, for example, with various types of triggers such as a time trigger or process trigger.  
  
-   Gain control over the type of trace that you run, for example, a linear or circular trace.  
  
-   Run traces while you are focusing on other high-priority issues.  
  
To enable these scenarios, Message Analyzer provides you with the capability to automate the capture of network messages through PowerShell scripting. Message Analyzer makes this feature available by providing PowerShell commandlets (cmdlets) that programmatically expose PEF message tracing functionality in the PowerShell scripting environment. Other supporting configuration capabilities are also provided in the PowerShell environment to facilitate some basic Trace Session configuration, including automation triggers that define how and when Trace Sessions are started and stopped.  
  
---  
  
 **What You Will Learn**   
In the topics of this section that are listed below, you will learn about the PowerShell automation features that are available for Message Analyzer.  

---  
  
 **[Encapsulating Tracing Functionality](automating-tracing-functions-with-powershell.md#BKMK_EncapsulatedFunctionality)**  — learn what types of tracing functions you  an automate with PowerShell.  
  
 **[Using PowerShell Cmdlets](automating-tracing-functions-with-powershell.md#BKMK_pshellcmdlets)**  — review the functions of the PowerShell cmdlets that can work with Message Analyzer.  
  
 **[Examining a PowerShell Script Example](automating-tracing-functions-with-powershell.md#BKMK_PSScriptExample)**  — look over the code for a PowerShell script example that does the following:  
  
-   Creates a trace session object that is configured for circular capture mode.  
  
-   Specifies a message provider that will capture the data.  
  
-   Adds a TCP trace filter that is applied 150 seconds after the trace session starts.  
  
-   Creates a time trigger that defines when the session will start and a keyboard key stroke that defines how the session will stop.  
  
-   Specifies a file name and path where trace data is stored when the session is stopped.  
  
**[Accessing PowerShell Cmdlets and Help](automating-tracing-functions-with-powershell.md#BKMK_AccessingPSFunctionality)**  — learn how to obtain the latest version of PEF cmdlet Help.  
  
> [!IMPORTANT]
>  Before you run any PEF PowerShell cmdlets, ensure that you update the PEF PowerShell cmdlet help for Message Analyzer, as described in [Accessing PowerShell Cmdlets and Help](automating-tracing-functions-with-powershell.md#BKMK_AccessingPSFunctionality).  
  
<a name="BKMK_EncapsulatedFunctionality"></a>   
## Encapsulating Tracing Functionality  
 The pre-configured PowerShell commandlets (cmdlets) that are available for Message Analyzer enable you to do the following:  
  
-   Configure new Trace Sessions.  
  
-   Specify a message provider for your Trace Session.  
  
-   Run Trace Sessions in circular capture mode.  
  
-   Apply a **Trace Filter** to your Trace Session configuration by specifying a predefined or custom filter expression.  
  
-   Specify the following types of triggers that can start and stop a Message Analyzer Trace Session, or perform other functions:  
  
    -   DateTime  
  
    -   KeyDown  
  
    -   Message  
  
    -   Process  
  
    -   Event Log  
  
    -   Win32 Events  
  
    -   TimeSpan  
  
-   Receive notification when a particular condition is met, for example, when an event triggers Message Analyzer to start a Trace Session or when a Trace Session stops.  
  
-   Save a message data collection in the file system.  
  
<a name="BKMK_pshellcmdlets"></a>   
## Using PowerShell Cmdlets  
 The following PowerShell cmdlets automate several Message Analyzer functions so that you can streamline your network problem solving tasks, gain more control over tracing functions, and achieve better time management. The cmdlets enable you to configure, start, stop, and save data for Trace Sessions and to specify trigger events that invoke or respond to these actions, as described below.  
  
- **Action scripts**:  
  
  -   **Invoke-PefCustomAction** — enables you to run a PowerShell script block that invokes PEF actions. You must specify the script block you want to run and a trigger for the actions it invokes. When the trigger occurs, such as a specified date-time to start or stop a Trace Session, the specified script block is invoked. The script block can contain any custom script necessary to perform custom PEF actions, for example, a script that stops a Trace Session and sends an email at that time. To learn more about script blocks, you can invoke `Get-Help about_script_blocks` at the PowerShell command line.  
  
  -   **Save-PefDataCollection** — enables you to save a collection of messages from a Trace Session. You must specify the session you want to save and the file path for the data. You can also specify a trigger that activates the save action when a Trace Session completes, so that you can save all messages currently contained in the session. You can also save a specified number of bytes so that you can analyze the data without stopping the Trace Session.  
  
  -   **Set-PefTraceFilter** — enables you to override the **Trace Filter** that you specified in a Trace Session object that you originally created with the **New-PefTraceSession** cmdlet. You can specify a string value for the **Trace Filter** and the target Trace Session as parameters of the **Set-PefTraceFilter** cmdlet. If you use the **Set-PefTraceFilter** to specify a **Trace Filter**, it will override any filtering value that you specified with the **Filter** parameter of the **New-PefTraceSession** cmdlet. If you do not specify a trigger for the override action, the Trace Filter that you specify will take effect immediately. However, if you do specify a trigger, you can control the point in time at which the Trace Filter is applied in the Trace Session.  For example, you can set the **Filter** parameter of the **New-PefTraceSession** cmdlet to a specific value and then use the **New-PefTimeSpanTrigger** cmdlet to specify a time span after which a **Trace Filter** configured by the **Set-PefTraceFilter** cmdlet is inserted into the PEF Runtime component parsing and filtering processes.  
  
       When you start a Trace Session with the **Start-PefTraceSession** cmdlet, the **Trace Filter** that you specify with the **Set-PefTraceFilter** cmdlet functions the same way as any other **Trace Filter** configured in the Message Analyzer UI. The **Set-PefTraceFilter** cmdlet also returns the target session to enable pipelining.  
  
  > [!NOTE]
  >  If you specify a file-based data source (such as a log file) as the message provider when creating a Trace Session with the **New-PefTraceSession** cmdlet, any filter that you specify with the **Set-PefTraceFilter** cmdlet will act as a **Trace  Filter**.  
  
- **Start-PefTraceSession** — enables you to start a Message Analyzer Trace Session and to specify a trigger for the startup action. **Start-PefTraceSession** acts as an entry point for message processing. If you do not specify a trigger, **Start-PefTraceSession** initiates a processing loop where no other PowerShell cmdlets or functions are executed until the loop ends. If the **Start-PefTraceSession** cmdlet has a trigger, it will start a message processing loop only when that trigger is fired. When a message processing loop terminates, all active Trace Sessions are stopped. You can stop a Trace Session by invoking the **Stop-PefTraceSession** cmdlet, which causes **Start-PefTraceSession** to exit the processing loop. This cmdlet also returns the target session to enable pipelining.  

- **Stop-PefTraceSession** — provides the means to define how you will stop a specified Trace Session. When the session is stopped, it is terminated and the PEF Runtime state is cleaned up. You can also use this cmdlet to define the trigger action that stops a specified Trace Session, which you configure prior to starting the Trace Session. To store the data retrieved in the Trace Session, you can specify values for the `SaveOnStop` parameter when creating a Trace Session with the **New-PefTraceSession** cmdlet, or you can use the **Save-PefDataCollection** cmdlet to specify where to store retrieved data.  
  
  > [!NOTE]
  >  When you write a PowerShell script, you typically specify the **Stop_PefTraceSession** cmdlet before the **Start-PefTraceSession** cmdlet, because the Trace Session will start as soon as you hit return at the PowerShell command line after specifying the **Start-PefTraceSession** cmdlet.  
  
- **Trigger scripts**:  
  
  -   **New-PefDateTimeTrigger** — enables you to create a date-time trigger that you can use to start a Trace Session, stop a Trace Session, or inject a **Trace Filter** into the Trace Session at a specific time. When you associate a date-time trigger with a PEF action, the computer where the Trace Session will run sets a timer that triggers the specified PEF action when the trigger is activated.  
  
  -   **New-PefKeyDownTrigger** — enables you to create a trigger action based on keyboard input, by pressing a key that you specify with the `–Key` parameter. Note that the `Ctl+C` keyboard combination is no longer supported as a trigger for this cmdlet. You can use a specified keystroke trigger to start or stop a Trace session. When you associate this trigger with a PEF action, the PEF action occurs when the trigger fires on the computer where the Trace Session is running.  
  
  -   **New-PefMessageTrigger** — provides the means to create a message trigger that you can use to start, stop, save, or filter a PEF Trace Session, for example, based on a captured message type. When you associate this trigger with a PEF action, the PEF action occurs when the trigger fires on the computer where the Trace Session is running.  
  
  -   **New-PefProcessTrigger** — enables you to create a process trigger that starts a Trace Session when a process exits. For example, you might start a Trace Session after a started executable process has finished running. When you associate this trigger with a PEF action, the PEF action occurs when the trigger fires on the computer where the Trace Session is running.  
  
  -   **New-PefTimeSpanTrigger** — enables you to create a timer trigger that fires after a specified time span. You can use this timer trigger to start, stop, or add a **Trace Filter** to a Trace Session when a specified interval of time elapses.  
  
  -   **New-PefEventLogTrigger** — enables you to create a trigger that fires when an entry is created in the Windows Event Log.  
  
  -   **New-PefWin32EventTrigger** — enables you to create a trigger that fires when a Win32 Event object is set.  
  
- **Miscellaneous scripts**:  
  
  -   **Add-PefMessageProvider** — enables you to add one or more message providers to a specified Trace Session object that you create with the **New-PefTraceSession** cmdlet. A message provider can be a PEF message provider such as the **Microsoft-Pef-WFP-MessageProvider**, a system ETW provider, or even a file-based message source such as a log file.  
  
  -   **Add-PefMessageSource** — enables you to add various message sources to a PEF Trace Session. You can specify any of the following types of message sources for this cmdlet:  
  
      -   A saved file as a message source in a Data Retrieval Session, for example, a .cap or .matp file.  
  
      -   A log file as a message source in a Data Retrieval Session, for example, an event log (.etl) or a text log (.log) file.  
  
      > [!NOTE]
      >  When specifying a text log as input to a Data Retrieval Session, you can also specify a text log configuration file for parsing the log.  
  
  -   Manifest-based PEF message providers such as the **Microsoft-PEF-WFP-MessageProvider** or **Microsoft-PEF-NDIS-PacketCapture** provider, as a message source in a Live Trace Session.  

  -   Manifest-based system ETW providers such as the **Microsoft-Windows-Dhcp-Client** as a message source in a Live Trace Session.  

  -   The object created by the **Add-PefProviderConfig** cmdlet can also serve as input to the **Add-PefMessageSource** cmdlet.  

- **Add-PefProviderConfig** — enables you to add a provider to the configuration of a Live Trace Session that targets a remote host, by specifying the friendly provider name (not a GUID).  

  The provider configuration is accessible by using the object that this cmdlet creates, from where you can configure provider error levels, event keywords, filters, and other provider-specific options for providers such as the **Microsoft-Windows-NDIS-PacketCapture**, **Microsoft-Pef-WebProxy**, and **Microsoft-Pef-WFP-MessageProvider**.  

- **New-PefTraceSession** — enables you to create a Trace Session object that captures live data or retrieves stored messages, for example, from a log file. You can specify whether to capture data in circular or linear mode to control how much data is held in the Trace Session. You can also configure a **Trace Filter** to focus the data retrieval action on messages that meet specific filtering criteria. If you want to save the data to a file after the Trace Session is stopped, you can do so by specifying the **SaveOnStop** parameter. For each Trace Session that you configure, you must add the message provider you want to use, such as the **Microsoft-Pef-NDIS-PacketCapture** or **Microsoft-Pef-WFP-MessageProvider**, by specifying it with the **Add-PefMessageProvider** cmdlet. To start and stop the Trace Session, you can use the **Start-PefTraceSession** and **Stop-PefTraceSession**, respectively, along with configuring any triggers that facilitate such actions.  

- **New-PefTargetHost** — enables you to create a target host object that you specify as a target computer for remote tracing in a Live Trace Session. You can target and add multiple computers to a Live Trace Session with this cmdlet. Use the object that this cmdlet creates as input to the **Add-PefProviderConfig** cmdlet. Note that this cmdlet uses the current user credentials by default, although you can provide other credentials by specifying the -Credentials parameter.  
  
  > [!NOTE]
  >  This cmdlet uses the Microsoft-PEF-WFP-MessageProvider, which is now enabled for remote tracing. You can use this provider to capture remote traffic, but     on a remote Windows 10 host only, and while running on a Windows 8.1, Windows Server 2012 R2, or Windows 10 computer only.  
    
  > [!TIP]
  >  On the Windows 10 client operating system, you can capture traffic locally or remotely in promiscuous mode (p-mode) by using the **Add-NetEventNetworkAdapter** and the **Add-NetEventPacketCaptureProvider** PowerShell cmdlets. With the **Add-NetEventNetworkAdapter** cmdlet, you can specify the –PromiscuousMode parameter for a supporting network adapter that you are adding as a filter on a remote packet capture provider. With the **Add-NetEventPacketCaptureProvider** cmdlet, you can specify the **Windows-NDIS-PacketCapture** provider to capture remote traffic and save a \*.etl file locally on the remote computer. Note that you can import this file into Message Analyzer from the **Files** tab of the **New Session** dialog to retrieve the data for analysis. In a future Message Analyzer release, you may have the option to capture in the promiscuous mode directly from the user interface.  
  > **To learn more**, see the [Add-NetEventNetworkAdapter](/powershell/module/neteventpacketcapture/add-neteventnetworkadapter?view=win10-ps) and [Add-NetEventPacketCaptureProvider](/powershell/module/neteventpacketcapture/Add-NetEventPacketCaptureProvider?view=win10-ps) cmdlets on TechNet.  
  
<a name="BKMK_PSScriptExample"></a>   
## Examining a PowerShell Script Example  
 To automate Message Analyzer network trace functionality with PowerShell, you will need to string together PowerShell cmdlets to achieve a desired result. The base cmdlet upon which all other cmdlet functionality depends is the **New-PefTraceSession** cmdlet. For example, you must use this cmdlet first to create a trace session object and then use other cmdlets to include additional configurations, such as adding the provider to use in the Trace Session, specifying an override filter, adding data saving functions, and configuring trigger actions.  
  
 The following example uses the `New-PefTraceSession` cmdlet to create a Trace Session object that is stored in the variable `$TraceSession01` and is configured for the circular capture mode. The script then uses the `Add-PefMessageProvider` cmdlet to specify the provider that Message Analyzer should use to capture data and associates the provider specification with `$TraceSession01`. Next, the `Set-PefTraceFilter` configures a “TCP” **Trace Filter** that will be applied to the trace 150 seconds after the Trace Session starts, as specified by the variable `$Trigger01`, which is configured with the `New-PefTimeSpanTrigger` cmdlet. The script then specifies two more triggers; `$Trigger02`, which configures the time at which the Trace Session will start, and `$Trigger03`, which specifies the PEF action that stops the Trace Session, which in this case is a keyboard key that is specified by the  `-Key` parameter. These triggers are then associated with the `Stop-PefTraceSession` and `Start-PefTraceSession` cmdlets, respectively. Lastly, the `Save-PefDataCollection` cmdlet specifies the trace file type (.matu) and the file name and full path where the Trace Session data will be stored at the time `$Trigger03` occurs. The `Force` parameter in this cmdlet causes the data of any existing file of the same name to be overwritten. The `Start-PefTraceSession` cmdlet then begins the session when `$Trigger02` fires.  
  
 The syntax for this functionality is specified as follows:  
  
```PowerShell
$TraceSession01 = New-PefTraceSession -Mode Circular  
Add-PefMessageProvider -PEFSession $TraceSession01 –Provider "Microsoft-PEF-WFP-MessageProvider"  
$Trigger01 = New-PefTimeSpanTrigger -TimeSpan (New-TimeSpan -Seconds 150)  
Set-PefTraceFilter -PEFSession $TraceSession01 –Filter "TCP" -Trigger $Trigger01  
$Trigger02 = New-PefDateTimeTrigger -DateTime "9/30/2013 7:00 AM"  
$Trigger03 = New-PefKeyDownTrigger –Key S  
Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger03  
Save-PefDataCollection -PEFSession $TraceSession01 -Path <"fullTracePath\myTrace.matu"> -Force -Trigger $Trigger03  
Start-PefTraceSession -PEFSession $TraceSession01 –Trigger $Trigger02  
```  
  
---  
  
 **More Information**   
 **To learn more** about writing **Trace Filters** and other Filter Expressions, see the [Writing Filter Expressions](writing-filter-expressions.md) topic in this Operating Guide. Note that a **Trace Filter** in a PowerShell script performs a function that is identical to a **Session Filter** in the Message Analyzer user interface.  
 
---  
  
<a name="BKMK_AccessingPSFunctionality"></a>   
## Accessing PowerShell Cmdlets and Help  
 To take advantage of the functionality provided in the previously described [Using PowerShell Cmdlets](automating-tracing-functions-with-powershell.md#BKMK_pshellcmdlets) for Message Analyzer, you must have PowerShell v3.0 installed. PowerShell v3.0 installs automatically with Windows 8 and later operating systems; however, if you are running Windows 7, you will need to install the [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/?LinkId=523822) to obtain a PowerShell v3.0 installation. After you have a PowerShell v3.0 installation in place on your Windows 7 machine, you will need to run the following command to import the PEF PowerShell module into your PowerShell session:   
`Import-Module PEF`  
Then, to update the help, run the following command to download the latest cmdlet Help content from TechNet:   
`Update-Help -Module PEF -Force –Verbose`  
  
> [!NOTE]
>  PowerShell cmdlet help documentation is available at the PowerShell command line and also in the TechNet Library on the [Message Analyzer Cmdlets](http://go.microsoft.com/fwlink/?LinkId=523823) site. For complete command-line syntax, parameter specifications, and usage examples, see these locations. If you want to view help at the PowerShell command line for a particular cmdlet, specify the following command string:   
> `get-help <cmdletname>`