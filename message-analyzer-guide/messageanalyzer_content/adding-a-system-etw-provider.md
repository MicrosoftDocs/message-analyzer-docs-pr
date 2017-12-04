---
title: "Adding a System ETW Provider | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d5511531-f95a-459c-ac9a-8805f27546d2
caps.latest.revision: 50
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Adding a System ETW Provider
Message Analyzer enables you to expand or narrow the scope of the data that a Live Trace Session will capture by specifying a system ETW Provider configuration. For example, you can add a system ETW Provider to the  provider configuration that a built-in **Trace Scenario** provides by default, to capture events from a particular Windows component that will appear as additional data  in your trace results — assuming that such events were written by the component's ETW Provider during the trace. Alternatively, you can select only system ETW Providers  to narrow the focus to capturing events from specific components only, but you will need to be familiar with the component providers and the **Keywords** that you can enable for capturing specific events of interest.  
  
 The system ETW Providers that are registered on your system write events that are issued by various Windows components that have been instrumented with ETW technology to write such events. These providers are accessible from the searchable **Available System Providers** list in the **Add System Providers** dialog, which is accessible by clicking the **Add Providers** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog during Live Trace Session configuration. Note that many of these providers are based upon managed object format (MOF) schemas to define their events for ETW.  
  
 When you are considering which ETW Provider to add to a Live Trace Session, your familiarity with event tracing can be of significant value, given that you are likely to already understand the functions of various ETW Providers. However, if your experience is limited, choosing a provider may be a little more challenging. Many ETW Provider names are somewhat cryptic and may not adequately describe the provider functionality, whereas others are more clearly named. For example, the type of data captured by the **Microsoft-Windows-Dhcp-Client** provider is, generally speaking, not too difficult to determine. Moreover, if you review the **Keywords** for this provider, you will learn that it captures related system events in addition to others that reflect response time and client operational or administrative events. You might also try this approach when assessing other ETW Providers for possible inclusion in a Live Trace Session, because  formal documentation  for the large number of system ETW Providers is limited on Windows computers.  
  
> [!NOTE]
>  You may be able to determine more about the events that are written by the ETW Providers on your system by examining the event **Keyword** configurations of such providers. This information typically exists in the manifests for the ETW Providers, which you can expose in several different ways, as described in [Finding System ETW Provider Metadata](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords).  
  
## Selecting a System ETW Provider in Live Trace Session Configuration  
 Once you know which system ETW Providers are of interest for the type of tracing you want to perform, the process of selecting a system ETW Provider to add to the **ETW Providers** list in the **New Session** dialog is straightforward. However, because the system ETW Provider list is very long, Message Analyzer provides a search box that enables you to locate providers  quickly by name or GUID. To  search for a system ETW Provider to add to the Live Trace Session configuration, perform the following steps.  
  
1.  Open the **New Session** dialog by clicking the **New Session** button on the global Message Analyzer toolbar.  
  
2.  Click the **Live Trace** button in the **New Session** dialog and then click the **Add Providers** drop-down list on the toolbar in the **ETW Providers** pane of the **New Session** dialog.  
  
3.  In the drop-down list, select  the **Add System Providers** item to display the **Add System Providers** dialog that contains a list of system ETW Providers  that Message Analyzer enumerated on your local system during installation, as shown in the figure that follows.  
  
     ![Specifying ETW Providers for Live Trace Session Configuration](../messageanalyzer_content/media/fig21-specifying-etw-providers-for-live-trace-session-configuration.png "Fig21-Specifying ETW Providers for Live Trace Session Configuration")  
  
     **Figure 21: Specifying  ETW Providers for Live Trace Session Configuration**  
  
4.  Scroll down the  **Available System Providers** list to locate a particular provider by name, or alternatively, type an ETW **System Provider** name or GUID in the search box to locate the provider of interest.  
  
     If you have a general idea of the type of provider you want to locate, you can enter  text in the search box that partially reflects the provider name and Message Analyzer will return all provider names that contain the text you entered. For example, if you specify the text "dhcp", Message Analyzer will return a list of ETW Providers such as the **Microsoft-Windows-Dhcp-Client** and **Microsoft-Windows-DHCPv6-Client**.  
  
5.  After you locate the ETW Provider/s you want to add to the Live Trace Session configuration from the **Available System Providers** list of the **Add System Providers** dialog, highlight each one separately and then click the **Add To** button in the dialog to populate the **Selected Providers** list of the dialog.  
  
6.  After  all the ETW Providers that you are adding to the Live Trace Session configuration are displayed in the **Selected Providers** list, click the **OK** button to exit the **Add System Providers** dialog.  
  
     At this time, the ETW providers that you are adding to the Live Trace Session configuration appear in the **ETW Providers** list of the **New Session** dialog.  
  
7.  Optionally modify the event **Keyword** and/or **Level** settings for any ETW Provider, as described in [Configuring System ETW Providers](../messageanalyzer_content/adding-a-system-etw-provider.md#BKMK_ConfigETWProviders).  
  
> [!IMPORTANT]
>  You have the option to add a custom provider of your own  to the **Available System Providers** list by specifying a **Guid** and a **Name** in the **Add Custom Provider** dialog. This dialog displays when you select the **Add Custom Provider** item in the **Add Providers** drop-down list on the toolbar of the **Live Trace** tab in the **New Session** dialog.  
  
<a name="BKMK_ConfigETWProviders"></a>   
## Configuring System ETW Providers  
 After you select a system ETW Provider as previously described and it displays in the **ETW Providers** list, you can access the configuration settings for the provider on the **ETW Core** tab of the **Advanced Settings** dialog. This dialog displays when you click the **Configure** link that appears immediately to the right of the **Id** for any provider that is listed in the **ETW Providers** list. If you want to further refine the focus of the provider’s data retrieval action, you can modify the provider filtering configuration.  
  
 For example, you can specify event **Keyword** and **Level** filtering settings if the particular system ETW Provider defines such filters. To specify a **Level** filter from the **Advanced Settings** dialog, click the **Level** drop-down list and select an error **Level** that will cause the ETW Provider to return only the events that reflect the specified **Level** that you set. Note that **Level** filters are inclusive, as described in the "System ETW Provider Keyword and Level filter" Table in the [System ETW Provider Event Keyword/Level Settings](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md) topic.  
  
 To enable a **Keyword** filter from the **Advanced Settings** dialog, click the ellipsis (**…**) to the right of the **Keywords (Any)** or **Keywords (All)** text boxes to display the **ETW Keyword Filter Property** dialog. From there, you can place a check mark in one or more of the **Keyword** check boxes for the selected ETW Provider, to cause the provider to return only the events that the **Keyword** enables. Whenever you enable a **Keyword**, you will see that the hexadecimal value in the text box at the bottom of the **ETW Keyword Filter Property** dialog changes to a new value. The default value is the 16-digit hexadecimal number: 0x0000000000000000, which typically signifies that all events for which the provider is configured will be delivered to Message Analyzer, that is, if the events are triggered and written to the ETW Session under which your provider is running during a trace.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the differences between the **Keywords (Any)** and **Keywords (All)** settings, see [Filtering with System ETW Provider Event Keywords and Levels](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md#BKMK_KeywordFiltering).  
___________________\_  
  
## Correlating Events Defined by Keywords  
 The **Keywords** that you enable will cause the ETW Provider to return only the events that the **Keywords** define. **Keyword** definitions and descriptions are usually specified in the manifest of the ETW Provider with which you are working. To be successful at specifying event **Keyword** configurations, you will need to understand the correlation between **Keywords** and the types of events that will be returned. You may be able to discover this correlative information by employing some of the methods described in [Finding System ETW Provider Metadata](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords). If you do not specify any **Keywords** for an ETW Provider, the provider will deliver all events that it is configured to provide, just as some ETW Providers that have no **Keyword** configurations do.  
  
## Support for WPP Tracing  
 This section describes how Message Analyzer provides support for processing WPP-generated events, in a Data Retrieval Session or a Live Trace Session.  
  
 **Support for Parsing Static Trace Files**   
Message Analyzer can parse and display events that are generated by a Windows software trace preprocessor (WPP) trace provider. Because this type of provider writes events that can integrate with the ETW framework, Message Analyzer can load them from a saved event trace log (ETL) file that is created by an appropriate system tool such as *Logman* or *Netsh*. To enable parsing of WPP-generated events, users must specify the path to a trace message format (TMF)  file on the **WPP** tab of the **Options** dialog. If you have  only a program database (PDB) file that provides the formatting information for the WPP event structure definitions, you can create a TMF file from it by specifying the path to the PDB file and the path to the utility *Tracepdb* on the **WPP** tab of the **Options** dialog, as described in [Loading WPP-Generated Events](../messageanalyzer_content/loading-wpp-generated-events.md).  
  
 **Support for Parsing WPP Events Live**   
In scenarios where you want to view WPP events immediately after they are generated by a software component, it may be possible to capture WPP-generated events live through the use of an automatically-generated TMF file, if you specify a GUID for the WPP component that is generating the events. In this scenario, when the WPP component is compiled on a particular system, a TMF and/or a PDB symbol file will be automatically generated, for which Message Analyzer will need to search in order to locate the definition/s of the WPP event structure/s. This should enable Message Analyzer to parse the WPP events live.  
  
 To specify the GUID of the software component that is generating the events, you can enter it in the **Add Custom Provider** dialog, which is accessible from the **Add Providers** drop-down list on the **ETW Providers** toolbar in the **New Session** dialog during Live Trace Session configuration.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the configuration settings for system ETW Providers, including event **Keyword** and error **Level** filter configuration, see [System ETW Provider Event Keyword/Level Settings](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md).   
**To learn more** about the ETW framework and system ETW Provider functionality, see the [ETW Framework Conceptual Tutorial](../messageanalyzer_content/etw-framework-conceptual-tutorial.md).  
**To learn more** about how Message Analyzer supports WPP trace providers, see [Loading WPP-Generated Events](../messageanalyzer_content/loading-wpp-generated-events.md).   
**To learn more** about Message Analyzer support for MOF-based providers, including how to register and deploy one, see [Using MOF-Based ETW Providers](../messageanalyzer_content/message-analyzer-tutorial.md#BKMK_MOFProviders).  
___________________\_