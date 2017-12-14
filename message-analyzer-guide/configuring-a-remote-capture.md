---
title: "Configuring a Remote Capture | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e3ac52dd-9502-4dd6-8338-e017d0b853fb
caps.latest.revision: 69
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Configuring a Remote Capture
Message Analyzer enables you to capture traffic on remote machines by running the **Remote Network Interfaces** **Trace Scenario**. This scenario uses the **Microsoft-Windows-NDIS-PacketCapture** provider for remote tracing. However, you can capture remote traffic with the **Remote Network Interfaces** scenario only from computers that are running the Windows 8.1, Windows Server 2012 R2, Windows 10, or later operating system. In addition, the source machine from where you start the **Remote Network Interfaces** scenario must also be running one of these same operating systems. Note that the **Remote Network Interface** scenario is not available on computers that are running the Windows 7, Windows 8, or Windows Server 2012 operating system.  
  
 Other requirements also apply, as follows:  
  
-   **WinRM configuration** — this service requires configuration on both the source computer where you are running the Message Analyzer remote trace and on target computers from which you are capturing data. You can configure the WinRM service by running the following command string from an elevated command prompt (Run as Administrator):  
  
     `winrm quickconfig`  
  
-   **Trusted Hosts configuration** — when the source computer and remote target host/s are not in the same domain, you must add the remote host name to the source computer Trusted Hosts list by running the following command string from an elevated command prompt, while substituting appropriately for the *RemoteHostName* value:  
  
     `winrm set winrm/config/client @{TrustedHosts="RemoteHostName"}`  
  
    > [!IMPORTANT]
    >  If you intend to capture data from multiple remote hosts, you should use the previous command to specify them in comma-separated format surrounded in quotes, as follows:  
    > `winrm set winrm/config/client @{TrustedHosts="RemoteHost1Name, RemoteHost2Name,.."}`, and so on  
  
## Connecting with Remote Hosts  
 If your systems match the indicated requirements, you can start remote configuration for your Live Trace Session by first specifying the name of one or more remote Windows 8.1, Windows Server 2012 R2, or Windows 10 hosts on which to capture remote message traffic, possibly along with Administrator credentials (see [Specifying Remote Host Connection Data](configuring-a-remote-capture.md#BKMK_SpecifyRemHostData)), to connect with those computers. You can specify the connection information from the **Edit Target Computers** dialog, which is accessible by clicking the **Edit** button on the **Live Trace** tab of the **New Session** dialog. If you do not specify any remote computers on which to capture traffic, then your Live Trace Session defaults to capturing messages on the local computer, as indicated by the default **Localhost** setting in the **Target Computers** list on the **Live Trace** tab.  
  
 Moreover, Message Analyzer enables you to capture traffic with the following target configurations:  
  
-   **Localhost** — the default setting to capture message traffic on the local computer.  
  
-   **One or more remote computers** — remove the  **Localhost** setting and add target remote computers on which to capture message traffic concurrently to the **Target Computers** list.  
  
-   **Local and remote computers** — retain the **Localhost** setting and add remote computers on which to capture message traffic concurrently to the **Target Computers** list.  
  
> [!NOTE]
>  When you capture messages from multiple computers, the results are aggregated in the data viewer that you specified in the **Start With** drop-down menu of the **New Session** dialog. If this is the **Analysis Grid** viewer, you can  add the **DataSource** field to your trace results display from the **General** node of **Field Chooser** (right-click **DataSource** and select **Add as Grouping**) to group and therefore differentiate the messages from each data source (remote computer).  
  
<a name="BKMK_SpecifyRemHostData"></a>   
## Specifying Remote Host Connection Data  
 To provide remote host connection information, click the **Add** drop-down in the **Edit Target Computers** dialog and then select **New Row** from the menu. A new row is then added to the **Edit Target Computers** dialog for specifying the host name or IP address in the **Computer Name / IP Address** text box, along with required connection credentials in the **User Name** and **Password** text boxes. If you are connecting to multiple remote hosts and the connection credentials are identical, you should select the **Automatically copy credentials** check box to avoid repeating duplicate credential entries for each host.  
  
 If you can use your current logon credentials to connect with specified hosts, leave the **User Name** and **Password** text boxes blank. You can do this if you will be connecting to a remote computer in the same domain and your local logon credentials have sufficient access (Administrative) privileges to the remote computer. Otherwise, you should specify your user name in the Domain\Username format and provide a valid password. You will still need sufficient access privileges in this case to connect with the remote computer that is in a different domain. When you are done adding host connection information, click **OK** to exit the **Edit Target Computers** dialog.  
  
 If you want to edit the connection information for any of the hosts that display in the **Target Computers** list, simply click **Edit** on the **Live Trace** tab of the **New Session** dialog and modify the information as required. Note that Message Analyzer retains all the connection information that you specify from session to session, until you remove it with the **Delete** control in the **Edit Target Computers** dialog. In addition, all the host names and user names that you entered in the **Edit Target Computers** dialog are retained in the **Add** drop-down list for future selection as required.  
  
## Specifying Advanced Settings for Remote Hosts  
 After you have specified connection credentials for remote computers on which to capture message traffic, and you have selected the **Remote Network Interfaces** **Trace Scenario**, you have the option to specify special filtering configurations in the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog. To access this dialog, click the **Configure** link to the right of the **Microsoft-Windows-NDIS-PacketCapture** provider **Id** in the **ETW Providers** list on the **Live Trace** tab of the **New Session** dialog. When the dialog opens, select the **Provider** tab and then click the **Host** drop-down to display the list of target computers that your Live Trace Session will connect with. To specify different filtering configurations for different hosts, you must select each host separately in the **Host** drop-down and then specify the filters you want to use, as described in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
 **Enumerating Adapters**   
When you select an item in the **Host** drop-down list, Message Analyzer attempts to connect with the specified host computer that is running any of the following operation systems: Windows 8.1, Windows Server 2012 R2, or Windows 10. If the connection attempt is successful, Message Analyzer may display a progress bar while enumerating the network adapters on the selected remote host, which can include both host adapters and virtual machine (VM) adapters that are serviced by a Hyper-V-Switch. Message Analyzer returns the results of the enumeration to the Interface Selection grid of the **Advanced Settings** dialog and populates it with adapter **Name** and **MAC Address** information. Thereafter, when you open the **Advanced Settings** dialog in the current session, the tree grid section of the dialog is automatically populated with this information. You can then apply the filtering configurations that you specify to one or more enumerated adapters that you select in the **Advanced Settings** dialog.  
  
 If you want to specify unique filtering configurations for each remote host, you will need to repeat the previously indicated process for each host in the **Host** list on the **Provider** tab of the **Advanced Settings** dialog. However, to simplify the process, you have the option to apply a common filtering configuration to all hosts by clicking the **Apply Changes to All Hosts** button on the **Provider** tab. Before you do this, you should carefully consider the applicability of the filtering configuration that you apply to all adapters on the remote hosts. For example, certain filters have a different effect on the interception layer and packet traversal path through the NDIS stack for host adapters, versus the extension layers of a Hyper-V-Switch adapter that services one or more virtual machines (VMs). For more details on the effects of **Layer** filtering and packet traversal **Direction** filters, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
<a name="BKMK_PromiscuousMode"></a>   
## Capturing Remotely in Promiscuous Mode  
 If you want to capture data remotely with an adapter that supports Promiscuous Mode, you can use the **Advanced Settings — Microsoft-Windows-NDIS-PacketCapture** dialog to do so. In the Interface Selection section of the dialog, you can simply select a P-Mode enabled adapter to capture in Promiscuous Mode, as indicated in [Selecting Adapter Interfaces](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md#BKMK_SelectAdapInterfaces).  
  
> [!TIP]
>  Please be aware that you can also capture data on the local computer in P-Mode, but you must use a **Trace Scenario** that contains the **Microsoft-Windows-NDIS-PacketCapture** provider, otherwise, you will not be presented with the **Advanced Settings** dialog for this provider where you can select an adapter that supports P-Mode. You can display this dialog by clicking the **Configure** link that appears next to the **Microsoft-Windows-NDIS-PacketCapture** provider in the **ETW Providers** list of the **New Session** dialog during Live Trace Session configuration,  
>   
>  You can also specify the **Microsoft-Windows-NDIS-PacketCapture** provider separately, outside of a built-in Message Analyzer **Trace Scenario** that contains this provider, by locating it in the **Add System Providers** dialog that displays when you click the **Add Providers** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog.  
>   
>  In either case, you will need to determine an adapter that supports P-Mode and then select that adapter in the **P-Mode** column of the Interface Selection section of the **Advanced Settings — Microsoft-Windows-NDIS-PacketCapture** dialog to enable a Promiscuous Mode capture with the selected adapter.  
  
## Filtering and Adapter Configurations  
 Message Analyzer enables you to specify the remote adapters on which to capture traffic by selecting specific adapters in the tree grid section of the **Advanced Settings** dialog. In addition, you can specify various filters such as **All Layers**, **Direction**, **Truncation**, **EtherType**, **IP Protocol Numbers**, **IP Addresses**, and **MAC Addresses**.  
  
> [!IMPORTANT]
>  If you want to capture traffic from a target remote VM, you will need to select the VM in the tree grid section of the **Advanced Settings** dialog and then create  a **MAC Address** filter based on the VM's MAC address to isolate the data. Otherwise, you will capture  Hyper-V-Switch traffic that is destined for all VMs that are serviced by the switch, given that a Hyper-V-Switch driver cannot of itself distinguish between VMs.  
  
 Some filters can have a different effect, depending on where you apply them. For example, selecting the **All Layers** and **Direction** check boxes together enables you to define the layer of the NDIS stack on which packets are intercepted and the traversal path (direction) in which they are intercepted. This can help you determine whether an adapter is dropping packets at a particular NDIS layer. When applied to a switch adapter, you can also define the interception layer and path of packets as they traverse the Hyper-V-Switch Extension layers. However, note that these filters have a slightly different effect, depending on whether you apply them to the NDIS layers of a host adapter versus the Extension layers of a switch adapter. The differences are explained in the **Layer** and **Direction** bullet points of the topic [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
 By choosing adapters and setting filters in the **Advanced Settings** dialog, you can be very specific about where you capture remote traffic and how much data you capture. For example, in addition to the previously indicated filters, you could also capture only the packet headers for a particular protocol of interest, by setting a truncation value that matches the header length of that protocol. You can access the configuration of all of the special filters for the **Microsoft-Windows-NDIS-PacketCapture** provider in the **Filters** pane of the **Advanced Settings** dialog, the details of which are further described in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
> [!TIP]
>  The **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog configuration settings are tied to the **Microsoft-Windows-NDIS-PacketCapture** provider. As a result, you can use this dialog to specify configuration settings for any **Trace Scenario** that employs the **Microsoft-Windows-NDIS-PacketCapture** provider. You simply access the dialog in the previously indicated manner for this provider. Note that the remote capabilities of the **Microsoft-Windows-NDIS-PacketCapture** provider are available in all **Trace Scenarios** that use this provider on computers that are running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system; but you can only capture remote data successfully if you are targeting computers that are running one of the same operating systems.  
  
## Starting a Remote Trace  
 After Message Analyzer has connected to one or more remote hosts and you have optionally specified adapter and filtering configurations in the **Advanced Settings** dialog, you can close the dialog and start your remote Live Trace Session the same way you start any trace — by clicking the **Start** button in the **New Session** dialog. At this time, Message Analyzer starts multiple concurrent subsessions, that is, if you have successfully connected with multiple hosts for remote capture, where each subsession captures message traffic on a different host that is specified in the **Target Computers** list on the **Live Trace** tab of the **New Session** dialog. The captured data then begins to aggregate from all the subsessions into the **Analysis Grid** viewer, or whichever viewer you specified from the **Start With** drop-down in the **New Session** dialog prior to starting the trace.  
  
## See Also  
 [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md)