---
title: "Procedures: Using the Network Tracing Features | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: be833484-3e40-44c7-9efa-c53f31c597c7
caps.latest.revision: 73
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Procedures: Using the Network Tracing Features

The procedures in this section encapsulate some of the main functionalities described in the [Capturing Message Data](capturing-message-data.md) section, which includes defining the scope of data capture in a Live Trace Session. Although you can quickly start a Live Trace Session with a single click of the **Start Local Trace** button or of a specific **Favorite Scenario** on the Message Analyzer **Start Page**, you might want to specify your own Live Trace Session configuration settings before starting a trace. You can do this by clicking the **New Session** button on the **Start Page** to open the **New Session** dialog, from where you can specify a **Live Trace** as a data source and then customize the capture configuration of your Live Trace Session. You can also access the same configuration settings for a Live Trace Session by clicking the **New Session** button in the upper left corner of the Message Analyzer UI, or by selecting the **New Session** item from the Message Analyzer **File** menu.  
  
 You will use the **New Session** dialog to create capture configurations in all of the procedures in this section. Each of the procedures specified in this section are preceded by conceptual information that describes the purpose, configuration features, and/or expected results of the procedure.  
  
> [!NOTE]
>  The procedures serve as simple examples that are intended to demonstrate how to utilize Message Analyzer tracing configurations and other facilities, rather than providing a comprehensive treatment of network troubleshooting. Although these procedures demonstrate the use of Message Analyzer capabilities in some basic scenarios, they are only a sampling of what you can accomplish with Message Analyzer, given that you can also apply the methodologies described here to many other scenarios.  
  
---  
  
 **Procedure Overviews**   
A brief description of each procedure is included here for review, as follows.  

---  
  
 **[Configure and Run a Local Network Interfaces Trace](procedures-using-the-network-tracing-features.md#BKMK_configStartLinkLayerTrace)**  — provides an example of how to modify the default **Local Network Interfaces** **Trace Scenario**; by specifying an adapter on which to capture messages and by adding a combination of filters to the **Microsoft-PEF-NDIS-PacketCapture** provider configuration on computers running the Windows 7, Windows 8, or Windows Server 2012 operating system; or to the **Microsoft-Windows-NDIS-PacketCapture** provider configuration on computers running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system; that restrict the scope of data retrieval to only messages that pass the defined filtering criteria.  
  
 **[Configure and Run a Loopback and Unencrypted IPSEC Trace](procedures-using-the-network-tracing-features.md#BKMK_configStartFirewallTrace)**  — provides an example of how to modify the default **Loopback and Unencrypted IPSEC**  **Trace Scenario** by setting the **Microsoft-PEF-WFP-MessageProvider** configuration to capture only HTTP packets through a TCP port filter.  
  
 **[Configure and Run a Pre-Encryption for HTTPS trace](procedures-using-the-network-tracing-features.md#BKMK_configStartWebProxylTrace)**  — provides an example of how to modify the default **Pre-Encryption for HTTPS** **Trace Scenario** by defining filtering criteria that enables you to monitor HTTP message exchanges between a client browser and a specified web server.  
  
 **[Capture Traffic on a Remote Host](procedures-using-the-network-tracing-features.md#BKMK_CaptureRemoteHost)**  — provides an example of how to use the default **Remote Network Interfaces** **Trace Scenario** to capture data on a remote host that is running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system. Includes specifying special filtering settings for a Hyper-V Switch and a target virtual machine (VM) that it services.  
  
 **[Design and Run a Custom Trace Scenario](procedures-using-the-network-tracing-features.md#BKMK_designRunTraceScenario)**  — provides an example of how to create, save, and run a **Trace Scenario** template that monitors the manual Group Policy update process on the local machine for signs of any issues with Lightweight Directory Access Protocol (LDAP) communications.  
  
> [!IMPORTANT]
>  If you have not logged off Windows after the first installation of Message Analyzer, please log off and then log back on before performing these procedures. This action ensures that in all subsequent logons following installation, your security token will be updated with the required security credentials from the Message Capture Users Group (MCUG). Otherwise, you will be unable to capture network traffic in local **Trace Scenarios** that use the **Microsoft-Windows-NDIS-PacketCapture** provider, unless you start Message Analyzer with the right-click **Run as administrator** option.  
  
> [!NOTE]
>  Even if you log off your system, log back on, and receive the required security credentials from the MCUG, you will still need to use the **Run as administrator** option to capture message data with the **Microsoft-Windows-NDIS-PacketCapture** provider in the procedure [Capture Traffic on a Remote Host](procedures-using-the-network-tracing-features.md#BKMK_CaptureRemoteHost). This is the result of the inherent remote capabilities of this provider and the security restrictions that must therefore be applied to it.  
  
<a name="BKMK_configStartLinkLayerTrace"></a>   
## Configure and Run a Local Network Interfaces Trace  
 In the following procedure, you will select the default **Local Network Interfaces** **Trace Scenario** on a computer that is running the Windows 7, Windows 8, or Windows Server 2012 operating system. You will then configure the **Microsoft-PEF-NDIS-PacketCapture** provider to isolate captured messages to a particular network adapter device and a specific IPv4 address. You might use a trace configuration such as this to minimize disk and CPU impact while capturing data on a busy computer that is overwhelmed with traffic.  
  
> [!NOTE]
>  If you are running the Window 8.1, Windows Server 2012 R2, or Windows 10 operating system, and you select the **Local Network Interfaces**  **Trace Scenario** in the procedure that follows, the **Microsoft-Windows-NDIS-PacketCapture** provider used in this scenario has different filtering options than the **Microsoft-PEF-NDIS-PacketCapture** provider. For more information about how to specify filters for the **Microsoft-Windows-NDIS-PacketCapture** provider, see [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md). In addition, you will need to run Message Analyzer with the right-click **Run as administrator** option on computers running one of the above specified operating systems, due to security restrictions of the **Microsoft-Windows-NDIS-PacketCapture** provider.  
  
#### To configure and run a Local Network Interfaces trace  
  
1.  From the **Start** menu, **Start** page, or task bar of your computer, click the **Microsoft Message Analyzer** icon to launch Message Analyzer.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains in the **New Session** dialog.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog, click the **Local Network Interfaces** **Trace Scenario**.  
  
     If your operating system is Windows 7, Windows 8, or Windows Server 2012, the **ETW Providers** list on the **Live Trace** tab is populated with the **Microsoft-PEF-NDIS-PacketCapture** provider **Name** and **Id** (GUID). Otherwise, for the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, the **Microsoft-Windows-NDIS-PacketCapture** provider information displays.  
  
5.  In the **ETW Providers** list on the **Live Trace** tab, ensure that the **Microsoft-PEF-NDIS-PacketCapture** provider is selected and then click the **Configure** link to the right of its **Id** to display the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, as shown in [Using the Advanced Settings - Microsoft-PEF-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-pef-ndis-packetcapture-dialog.md). If you are working with the **Microsoft-Windows-NDIS-PacketCapture** provider, clicking the **Configure** link will display the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog, as shown in [Using the Advanced Settings - Microsoft-Windows-NDIS-PacketCapture Dialog](using-the-advanced-settings-microsoft-windows-ndis-packetcapture-dialog.md).  
  
6.  If you are working with one of the specified earlier operating systems and the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, proceed to the next step. Otherwise, if you are working with one of the specified later operating systems and the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog, proceed to step 15.  
  
7.  In the **System Network** tree grid on the **Provider** tab of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog, specify a physical or wireless adapter on which to capture data, by selecting the **In** and **Out** direction check boxes of the adapter.  
  
     The **Microsoft-PEF-NDIS-PacketCapture** provider is set to capture both inbound and outbound traffic on the adapter device that you specified.  
  
8.  In the **Fast Filters** pane of the **Advanced Settings - Microsoft-PEF-NDIS-PacketCapture** dialog under **Group 1**, click the drop-down arrow next to the **Fast Filter 1** designator to display the filter type menu items and then select the **IPv4Address** filter type from the menu.  
  
9. In the text box to the right of the filter type drop-down, enter an IPv4 address in a format similar to the following:  
  
     *192.168.1.1*  
  
10. In the **Fast Filters** pane of the **Advanced Settings** dialog under **Group 2**, click the drop-down arrow next to the **Fast Filter 1** designator to display the filter type menu items and then select the **LinkLevelAddress** filter type from the menu.  
  
11. In the text box to the right of the filter type drop-down, enter a MAC address for a different adapter that you want to block traffic to, in a format similar to the following:  
  
     *!=00-2F-39-7E-1F-36*  
  
     This filter ensures that traffic will be blocked from reaching the adapter for which you specified the negated **LinkLevelAddress**. Note that you can also achieve this same result by simply deselecting the **In** and **Out** directional check boxes on the adapter for which you want to block traffic. However, this example shows you a simple way to utilize filter **Groups**.  
  
12. In the **Advanced Settings** dialog, highlight the **System Network** tree grid row that contains the adapter device you initially specified and then click the **Apply To Highlighted** button in **Group 1** of the **Fast Filters** pane to assign the filter **Group** to the adapter.  
  
> [!NOTE]
>  When you click the **Apply To Highlighted** button, the name of the adapter device to which the **Fast Filter Group** is applied appears next to the **Target** label for the corresponding **Group**.  
  
13. In the **Advanced Settings** dialog, highlight the **System Network** tree grid row that contains the adapter device for which you specified a negated **LinkLevelAddress** filter and then click the **Apply To Highlighted** button in **Group 2** of the **Fast Filters** pane to assign the filter **Group** to the adapter.  
  
     The **Microsoft-PEF-NDIS-PacketCapture** provider is now configured to do the following in your Live Trace Session:  
  
    -   Isolate trace data to only the adapter device that you initially specified.  
  
    -   Block all packets to the device for which you created a negated **LinkLevelAddress** filter.  
  
    -   Target data for a specific IPv4 address.  
  
    -   Reduce message count and improve trace performance.  
  
     When packets arrive that are intended for the adapter device that you initially specified, the filter configuration for **Group 1** is applied to those packets to pass the message data. When packets arrive that are intended for the second adapter device, the filter configuration for **Group 2** is applied to those packets to block the message data.  
  
14. Click **OK** to exit the **Advanced Settings – Microsoft-PEF-NDIS-PacketCapture** dialog.  
  
15. If you are working with one of the specified later operating systems and the **Microsoft-Windows-NDIS-PacketCapture** provider, select the check box in the tree grid (Interface Selection) section of the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog for the Ethernet or wireless adapter on which to capture data, and unselect the other check boxes. Otherwise, if you are working with the **Microsoft-PEF-NDIS-PacketCapture** provider, proceed to step 19.  
  
16. In the **EtherTypes** text box of the **Advanced Settings** dialog, enter the Ethernet type value for an IPv4 address, as follows:   
    *0800*  
  
17. In the **IP Addresses** text box of the **Advanced Settings** dialog, enter the value of the IP address of the local computer in a format similar to the following:   
    *192.168.1.1*  
  
     The **Microsoft-Windows-NDIS-PacketCapture** provider is now configured to do the following in your Live Trace Session:  
  
    -   Isolate packet traffic to only the adapter device for which you selected a check box.  
  
    -   Block traffic to all other adapter devices.  
  
    -   Capture packet traffic for the target IPv4 address only, while removing all other traffic with the specified EtherType value.  
  
    -   Reduce message count and improve trace performance.  
  
18. Click **OK** to exit the **Advanced Settings – Microsoft-Windows-NDIS-PacketCapture** dialog.  
  
19. In the **New Session** dialog, you can optionally enter a name for the session in the **Name** text box.  
  
20. If the **Analysis Grid** is not already specified as the data viewer for your Live Trace Session, click the **Start With** drop-down menu in the **New Session** dialog and select it.  
  
21. Click the **Start** button in the **New Session** dialog to begin capturing data in your Live Trace Session.  
  
     Message Analyzer may begin capturing data immediately.  
  
22. As captured messages accumulate in a new **Analysis Grid** session viewer tab below the Message Analyzer global toolbar, attempt to reproduce any conditions that are related to a particular issue you might be having on the target computer.  
  
23. Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar, or use the keyboard shortcut `Shift+F5`.  
  
24. In the **Analysis Grid**, right-click the **DiagnosisTypes** column header and select **Group** from the menu that displays, to group any error messages you might have received, for further analysis of a related issue.  
  
     All Diagnosis messages of the same type will display in a separate group that is labeled by the **DiagnosisType**. If you have multiple types of Diagnosis messages, there will be a unique group for each type. You can expand these groups to view the messages associated with each type. For further details about Diagnosis message types, see the [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic.  
  
<a name="BKMK_configStartFirewallTrace"></a>   
## Configure and Run a Loopback and Unencrypted IPSEC Trace  
 In the following procedure, you will select the built-in **Loopback and Unencrypted IPSEC** **Trace Scenario** and configure a **Fast Filter** to retrieve data from **TCP port** 80, thereby filtering for HTTP traffic only. You might use a **Trace Scenario** such as this on a client computer to limit your capture to HTTP traffic only, along with the protocol stack that supports the HTTP operations. This can help you to troubleshoot webpage performance, detect issues with HTTP connectivity, or debug a website based on HTTP responses sent to the client. Also, the filter employed in this scenario minimizes the impact on disk I/O and the CPU because the filter selects specific messages for capture, resulting in reduced message count and thus better performance.  
  
> [!NOTE]
>  In this scenario, the **TCP port** filter will pass messages that transit both TCP source and destination ports.  
  
#### To configure and run a Loopback and Unencrypted IPSEC trace  
  
1.  Start Message Analyzer as indicated in the first procedure of this section.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog, click the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
5.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link to the right of the **Id** for the **Microsoft-PEF-WFP-MessageProvider** to display the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog, as shown in [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  
  
6.  In the **Fast Filters** pane on the **Provider** tab of the **Advanced  Settings** dialog, click the **Fast Filter 1** drop-down arrow and select the **TCP port** item in the drop-down list.  
  
7.  In the text box to the right of the drop-down selection you made, enter the number *80*.  
  
     The **Microsoft-PEF-WFP-MessageProvider** is now configured to filter for HTTP packets on TCP port 80.  
  
     The messages that this trace configuration returns can include WFPCapture events, HTTP operations (as indicated by blue-cubed icons to the left of message numbers) the underlying message stack that supported such operations such as  TCP packets captured on port 80, in addition to TCP fragments and other HTTP messages.  
  
8.  Click **OK** to exit the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog.  
  
9. In the **New Session** dialog, optionally specify a name for the Live Trace Session in the **Name** text box.  
  
10. If the **Analysis Grid** is not already specified as the data viewer for your Live Trace Session, click the **Start With** drop-down list in the **New Session** dialog and select it.  
  
11. Click the **Start** button in the **New Session** dialog to begin capturing data in your Live Trace Session.  
  
     Message Analyzer may begin capturing data immediately.  
  
12. As captured messages accumulate in a new **Analysis Grid** session viewer tab below the global Message Analyzer  toolbar, attempt to reproduce any conditions that may be related to HTTP connectivity or performance problems, for example, by navigating to a web server where clients experience these issues.  
  
13. Stop the trace at a suitable point by clicking the **Stop** button on the Message Analyzer global toolbar.  
  
14. In the **Analysis Grid** viewer, right-click the column with the **DiagnosisTypes** icon and select **Group** from the context menu that displays to group any diagnostic messages you might have received, for further analysis.  
  
15. Review HTTP **StatusCodes** for evidence of connection or performance issues on the server, as described in [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) of this documentation.  
  
> [!NOTE]
>  To create a prominent view of HTTP status data, add the **HTTP.Response.StatusCode** field to the default **Analysis Grid** viewer column **Layout** with the **Field Chooser** **Tool Window**, by right-clicking the **StatusCode** field name and selecting the **Add As Column** command from the context menu that appears, as described in [Using the Field Chooser](using-the-field-chooser.md).  
  
<a name="BKMK_configStartWebProxylTrace"></a>   
## Configure and Run a Pre-Encryption for HTTPS trace  
 In the following procedure, you will run the **Pre-Encryption for HTTPS** **Trace Scenario** on a client computer with a filter configuration that enables you to capture and monitor unencrypted HTTP browser messages that are sent to a specified HTTP host that is slow to send response messages.  
  
#### To configure and run a Pre-Encryption for HTTPS trace  
  
1.  Start Message Analyzer as indicated in the first procedure of this section.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar, click the **Pre-Encryption for HTTPS** **Trace Scenario**.  
  
5.  In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link to the right of the **Microsoft-Pef-WebProxy** provider **Id** to display the **Advanced Settings - Microsoft-Pef-WebProxy** dialog.  
  
6.  On the **Provider** tab of the **Advanced Settings** dialog, specify the host name for a web server that may be slowly responding in the text box to the right of the **Hostname Filter** property of the provider, in a format similar to the following:  
  
     *www.xxxxx.com*.  
  
7.  On the **Provider** tab of the **Advanced Settings** dialog, specify an HTTP port number in the text box to the right of the **Port Filter** property of the provider, to ensure that you capture HTTP traffic only. Specify the port number in integer format, as indicated in the following examples:  
  
     *80* for HTTP, or *443* for HTTPS  
  
     The **Microsoft-PEF-WebProxy** provider is now configured to capture HTTP packets that are sent to and from the specified web server.  
  
8.  Click **OK** to exit the **Advanced Settings - Microsoft-PEF-WebProxy** dialog.  
  
9. In the **New Session** dialog, optionally specify a name for the Live Trace Session in the **Name** text box.  
  
10. If the **Analysis Grid** viewer is not already specified as the data viewer for your Live Trace Session, click the  **Start With** drop-down list in the **New Session** dialog and select it.  
  
11. Click the **Start** button in the **New Session** dialog to begin capturing data in your Live Trace Session.  
  
     Message Analyzer may begin capturing data immediately.  
  
12. As captured messages accumulate in a new **Analysis Grid** session viewer tab below the global Message Analyzer toolbar, open a web browser and establish a connection to the specified HTTP host by launching an HTTP request to the associated site address.  
  
13. Stop the trace at a suitable point by clicking the **Stop** button on the Message Analyzer global toolbar.  
  
14. In the **Analysis Grid** viewer, right-click the column with the **DiagnosisType** icon and select **Group** from the context menu that displays, to group any diagnostic messages you might have received, for further analysis.  
  
15. Review HTTP **StatusCodes** for evidence of connection or performance issues on the server, as described in [Addendum 2: HTTP Status Codes](addendum-2-http-status-codes.md) of this documentation.  
  
     To create a prominent view of HTTP status data, add the **HTTP.Response.StatusCode** field to the default **Analysis Grid** viewer column **Layout** with the **Field Chooser** dialog, by right-clicking the **StatusCode** field name and selecting the **Add As Column** command from the context menu that appears, as described in [Using the Field Chooser](using-the-field-chooser.md).  
  
> [!TIP]
>  You can also **Group** the **StatusCode** column in the **Analysis Grid** viewer to organize status codes into groups, for ease of analysis. To do so, right-click on the **StatusCode** column and select the **Group** command from the context menu that appears.  
  
<a name="BKMK_CaptureRemoteHost"></a>   
## Capture Traffic on a Remote Host  
 In the following procedure, you will use the **Remote Network Interfaces** **Trace Scenario** on a computer that is running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, to capture traffic from a virtual machine (VM) that is serviced by a Hyper-V-Switch on a remote computer that is running one of the same operating systems. In the procedure, you will do the following:  
  
-   Select the **Remote Network Interfaces** **Trace Scenario**.  
  
-   Specify the remote host connection credentials.  
  
-   Make an initial connection with the host to enumerate its adapter configuration.  
  
-   Use the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog to specify special filtering configurations for the Hyper-V-Switch and the VM from which you will capture remote message traffic.  
  
#### To configure and run a Remote Network Interfaces trace  
  
1.  Start Message Analyzer as indicated in the first procedure of this section.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar, click the **Remote Network Interfaces** **Trace Scenario**.  
  
5.  On the **Live Trace** tab of the **New Session** dialog, click the **Edit** button adjacent to the **Target Computers** list to display the **Edit Target Computers** dialog.  
  
6.  Click the **Add** drop-down arrow in the **Edit Target Computers** dialog and select the **New Row** item in the menu that displays.  
  
     A new row is added to the target computers grid in the dialog.  
  
7.  Specify the name or IP address of the remote host on which you intend to capture message traffic, by entering it in the new row under the **Computer Name/IP Address** column of the **Edit Target Computers** dialog. You can specify the remote host name by simply entering the host name without including the forward backslashes that are customarily used in the Universal Naming Convention (UNC) standard.  
  
> [!TIP]
>  You have the option to capture traffic on multiple remote hosts, as long as each one is running a supported operating system. For each remote host, you will need to create a new row in the **Edit Target Computers** dialog and specify the host name and connection credentials. When your trace results are complete, all the captured message data will be returned to Message Analyzer and aggregated into a single **Analysis Grid** session viewer tab.  
  
8.  If you cannot use your current logon credentials to connect with the remote host, then specify an appropriate **User Name** and **Password** in the indicated columns of the new row you added. When specifying other logon credentials, use the Domain\Username format. Otherwise, you can leave these grid fields blank to connect to the remote host with your current logon credentials.  
  
9. In the grid of the **Edit Target Computers** dialog, optionally select the row that contains the default **Localhost** setting and then click **Delete** on the dialog toolbar.  
  
     The target computer configuration is now set to capture message traffic on the specified remote host only, assuming that you opted to remove the **Localhost** from the **Edit Target Computers** dialog.  
  
10. When complete, click **OK** to exit the **Edit Target Computers** dialog.  
  
11. In the **ETW Providers** list on the **Live Trace** tab, click the **Configure** link to the right of the **Microsoft-Windows-NDIS-PacketCapture** provider **Id** to display the **Advanced Settings - Microsoft-Windows-NDIS-PacketCapture** dialog.  
  
12. On the **Provider** tab of the **Advanced Settings** dialog, click the **Host** drop-down arrow and select the name of the remote host in the drop-down list. This drop-down appears only if there is more than one host from which you are capturing traffic, for example, a remote host and the local computer, or one or more remote hosts.  
  
     Message Analyzer attempts to connect with the remote host to enumerate the host and/or switch adapters on that computer. When complete, the enumerated adapters, switches, and VMs that Message Analyzer discovered on the remote host will populate the tree grid section of the **Advanced Settings** dialog.  
  
13. In the tree grid section of the **Advanced Settings** dialog, remove all selected adapters, switches, and VMs from configuration by deselecting the **Machine** check box.  
  
14. In the tree grid section of the **Advanced Settings** dialog, specify the VM on which to capture data by selecting the enabling check box in the second grid column for the target VM.  
  
15. For the **Layer** parameter in the **Filters** pane of the **Advanced Settings** dialog, select the **All Layers** check box to ensure that packets are intercepted at all Hyper-V-Switch extension layers and so that the filtering rules of each switch extension are applied to all packets that traverse the switch layers.  
  
16. For the **Direction** parameter in the **Filters** pane of the **Advanced Settings** dialog, select the **Egress** check box so that packets are intercepted on all Hyper-V-Switch extension layers, but only in the direction that you specified, which in this case is the egress path that goes up the switch extensions stack. Note that the ingress path goes down the extension stack.  
  
     Selecting **Egress** only will result in faster switch port management and subsequently an improvement in performance.  
  
17. For the **EtherType** parameter in the **Filters** pane of the **Advanced Settings** dialog, specify the hexadecimal value `0800`, without the “0x” designator, to target the IPv4 protocol.  
  
18. For the **IP Protocol Numbers** parameter in the **Filters** pane of the **Advanced Settings** dialog, specify the hexadecimal value `06`, without the “0x” designator, to target the TCP protocol.  
  
     The **EtherType** and **IP Protocol Number** settings that you specified will cause the remote trace to filter for and return only Ethernet frames that have IPv4 packet payloads, and of those IPv4 packets, only the ones that have TCP payloads.  
  
19. For the **MAC Addresses** parameter in the **Filters** pane of the **Advanced Settings** dialog, specify the MAC address of the target VM in a format similar to the following, to ensure that your **Remote Network Interfaces** trace returns remote traffic for the target VM only:  
  
     `10-60-4B-6D-8D-2D`  
  
20. Click **OK** to exit the **Advanced Settings** dialog.  
  
21. Start your remote Live Trace Session by clicking the **Start** button in the **New Session** dialog.  
  
     Message Analyzer may begin capturing data immediately.  
  
22. As remote traffic from the specified VM begins to accumulate in the **Analysis Grid** viewer, perform operations on the remote VM or attempt to reproduce any issues that may be occurring on the target VM, or on the Hyper-V-Switch that services it.  
  
     For example, you may be concerned with packets being lost from a particular protocol on the VM. Because you have enabled all extension layers of the Hyper-V-Switch to intercept packets, then if any packets are being dropped by a switch extension layer, they should generate events that you can detect in Message Analyzer trace results.  
  
23. Stop the remote trace at a suitable point by clicking the **Stop** button on the Message Analyzer global toolbar, so that you can analyze your data.  
  
24. Search for dropped packets, if you suspect that this is occurring in a Hyper-V-Switch extension layer. Do this by looking for ETW messages that contain the **ut:Dropped** event by applying  the following view **Filter** from the Filtering toolbar that is located  just above the **Analysis Grid** viewer:  
  
     `Etw.EtwProviderMsg.EventRecord.Header.Descriptor.Keywords == 0x0000010000000000`  
  
     You can also check to see if the KW_DROPPED flag is set in the **Flags** field of any ETW message in the **Details** **Tool Window**.  
  
> [!NOTE]
>  To make it easier to analyze ETW messages, select the **ETW Layer** **Viewpoint** from the **Viewpoints** drop-down list on the Filtering toolbar to display all ETW messages with no layers above them.  
  
> [!TIP]
>  When analyzing data that you have captured from multiple remote computers, you have the option to organize and summarize the captured data into groups that are labeled by host (data source) name. You can do this by adding the  **DataSource** field from the **General** category of the **Field Chooser** to the default **Analysis Grid** viewer column **Layout**, and then applying the **Group** command by selecting it from the context menu that displays after you right-click the newly added **DataSource** column.  
  
---  
  
 **More Information**   
 **To learn more** about the extension filtering stack on a Hyper-V-Switch, see [Overview of the Hyper-V Extensible Switch](http://msdn.microsoft.com/en-us/library/windows/hardware/hh582268\(v=vs.85\).aspx) on MSDN.  
**To learn more** about capturing traffic on a remote host and specifying adapter and filter configurations for the **Microsoft-Windows-NDIS-PacketCapture** provider, see [Configuring a Remote Capture](configuring-a-remote-capture.md).   
**To learn more** about the **Field Chooser**, see [Using the Field Chooser](using-the-field-chooser.md).   

---  
  
<a name="BKMK_designRunTraceScenario"></a>   
## Design and Run a Custom Trace Scenario  
 In the following procedure, you will create a custom **Trace Scenario** template that captures LDAP traffic on the local client computer during a manual Group Policy update. You can run the template file whenever it is necessary to ascertain whether a client computer is experiencing Group Policy update issues.  
  
 This procedure primarily uses the **Loopback and Unencrypted IPSEC** **Trace Scenario** to take advantage of the capability of the **Microsoft-PEF-WFP-MessageProvider** to focus on messages above the Network Layer. However, in the procedure, you  also have the option to add the **Microsoft-Windows-LDAP-Client** system ETW Provider to the trace configuration by specifying the **SASL LDAP Pre-encryption with WFP** scenario instead of the **Loopback and Unencrypted IPSEC** scenario, so that you can capture LDAP traffic unencrypted. In addition, the events written by the **Microsoft-Windows-LDAP-Client** provider can help you to better understand the state of the LDAP client when LDAP bind, search, request, and response messages are sent during Group Policy update.  
  
#### To design and run a custom Trace Scenario  
  
1.  Start Message Analyzer as indicated in the first procedure of this section.  
  
2.  On the Message Analyzer **Start Page**, click the **New Session** button to display the **New Session** dialog.  
  
3.  Under **Add Data Source** in the **New Session** dialog, click the **Live Trace** button to display the **Live Trace** tab along with the associated session configuration features that it contains.  
  
4.  In the **Network** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar, click the **Loopback and Unencrypted IPSEC** **Trace Scenario**.  
  
> [!TIP]
>  If you want your custom scenario to capture LDAP traffic unencrypted, you might try using the **SASL LDAP Pre-encryption with WFP** **Trace Scenario**, which includes both the **Microsoft-Windows-LDAP-Client** and **Microsoft-PEF-WFP-MessageProvider** as part of the scenario configuration.  
>   
>  Note that you can optionally add other system ETW Providers to your **Trace Scenario** configuration from the **Add System Providers** dialog, which is accessible by clicking the **Add Providers** drop-down list on the **ETW Providers** toolbar. You might do this to return specific events that such a provider's **Keyword** configuration enables.  
  
    The **ETW Providers** list on the **Live Trace** tab is populated with the **Name** and **Id** (GUID) of the **Microsoft-PEF-WFP-MessageProvider** (and the **Microsoft-Windows-LDAP-Client** if you selected the **SASL LDAP Pre-encryption with WFP** **Trace Scenario**).  
  
5.  In the **ETW Providers** list, click the **Configure** link to the right of the **Id** for the **Microsoft-PEF-WFP-MessageProvider** to open the **Advanced Settings - Microsoft-PEF-WFP-MessageProvider** dialog, as shown in [Using the Advanced Settings- Microsoft-PEF-WFP-MessageProvider Dialog](using-the-advanced-settings-microsoft-pef-wfp-messageprovider-dialog.md).  
  
6.  In the **Fast Filters** pane on the **Provider** tab of the **Advanced Settings** dialog, click the drop-down arrow next to the **Fast Filter 1** designator to display the filter type menu items, and then select the **IPv4** filter type from the menu.  
  
7.  In the text box to the right of the filter type drop-down, enter an IPv4 address for the local computer in a format similar to the following:  
  
     *192.168.1.1*  
  
8.  Click **OK** to exit the **Advanced Settings** dialog.  
  
9. In the text box of the **Session Filter** pane in the **New Session** dialog, enter the following filter expression:  
  
     `*Port == IANA.Port.LDAP`  
  
     Your Live Trace Session template is now complete and configured to only capture LDAP traffic and other events related to the LDAP client, for the specified local IP address. In addition, the **Loopback and Unencrypted IPSEC** **Trace Scenario** and the **Session Filter** in use will remove a significant portion of lower-layer noise and improve performance.  
  
> [!TIP]
>  To view the events that you can capture with the **Microsoft-Windows-LDAP-Client** ETW Provider, click the **Configure** link to the right of the **Id** for this provider to open the **Advanced Settings - Microsoft-Windows-LDAP-Client** dialog and then click the ellipsis (**...**) to the right of the **Keywords(Any)** or **Keywords(All)** text box. This action will display the **ETW Keyword Filter Property** dialog, from where you can view and select specific events to capture, that is, if they are triggered during a trace. For further information about setting **Keyword** bitmask filters, see [System ETW Provider Event Keyword/Level Settings](system-etw-provider-event-keyword-level-settings.md).  
  
10. In the **New Session** dialog, optionally specify a name for your custom **Trace Scenario** in the **Name** text box.  
  
11. On the **Live Trace** tab of the **New Session** dialog, click the **Save Scenario** button.  
  
12. In the **Edit Trace Scenario** dialog that displays, provide a unique name for the scenario template in the **Name** text box and a description in the **Description** text box. Then choose an existing **Category** for the scenario template or specify a new one in the editable **Category** combo box.  
  
13. Click the **Save** button in the **Edit Trace Scenario** dialog to save the scenario in the **Message Analyzer Trace Scenarios** Library and exit the dialog.  
  
     The **Trace Scenario** template that you saved should now display in the **My Items** category of the **Select Scenario** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog.  
  
14. Display your **Trace Scenario** template configuration at any time by selecting it in the **Message Analyzer Trace Scenarios** Library that is accessible from the **Select Scenario** drop-down list.  
  
     When you do this, the **New Session** dialog will be populated with the custom settings that you specified when you created the **Trace Scenario** template. Note that you still have the option at this point to reconfigure your **Trace Scenario** prior to running a Live Trace Session; for example, you could specify a different **Session Filter**, provider line up, or **Keyword** bitmask configuration.  
  
> [!TIP]
>  If you make further modifications to your **Trace Scenario** template, you can resave it with the new configuration settings without ever running it.  
  
15. Start a Live Trace Session based on your custom **Trace Scenario** template by clicking the **Start** button in the **New Session** dialog.  
  
     Message Analyzer may begin capturing data immediately.  
  
16. While Message Analyzer is capturing message traffic, run the following command string from an elevated command prompt (Run as Administrator) to update Group Policy on the local machine:  
  
     `gpupdate /force`  
  
     The Live Trace Session begins capturing LDAP traffic on the local machine as the Group Policy update process accesses the appropriate Active Directory Group Policy Objects (GPOs) containing user and computer policy settings for the client.  
  
17. Stop the trace at a suitable point by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
18. In the **Analysis Grid** viewer, right-click the **DiagnosisTypes** column and select **Group** from the menu that displays to group any diagnostic messages you might have received, for further analysis.  
  
19. In the **Analysis Grid** viewer, review the LDAP messages for any status indications or errors that might reveal issues with LDAP bind, search, request, or response operations during Group Policy update. For example, you could add a **ResultCode** field as a new column to the default **Analysis Grid** viewer column **Layout** from the **Field Chooser** **Tool Window**.