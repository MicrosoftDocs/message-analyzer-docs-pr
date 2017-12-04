---
title: "Configuring a Live Trace Session | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0fdd7ff-6f87-4a4b-a0ed-20ef281c50c3
caps.latest.revision: 41
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Configuring a Live Trace Session
To capture data live with Message Analyzer, you can either start a basic Live Trace Session instantly with a single click, as described in [Performing a Live Capture](../messageanalyzer_content/performing-a-live-capture.md), or you can create and configure a Live Trace Session from the **New Session** dialog. If you choose the latter, you will need to specify a capture configuration of choice that involves performing one or more of the following tasks from the **New Session** dialog:  
  
-   Selecting a built-in **Trace Scenario** or a custom scenario of your own design from the **Select Scenario** drop-down list, or selecting a system ETW Provider in lieu of a **Trace Scenario**. This is a required task.  
  
-   Specifying target computers for  data capture in the **Edit Target Computers** dialog, or accepting the default Local host.  
  
-   Optionally adding other system ETW Providers to the provider list of a selected **Trace Scenario** by choosing them from the **Add Providers** drop-down list, to customize the scope of data capture.  
  
-   Enhancing message provider configurations with driver-level filtering, by clicking the **Configure** link in the **ETW Providers** list and creating a filter in the **Advanced Settings** dialog.  
  
-   Setting a **Parsing Level** from the **Parsing Level** drop-down list in the **New Session** dialog to limit the stack level to which Message Analyzer will parse, for performance improvements and focusing trace results on specific messages.  
  
-   Selecting a built-in **Session Filter** from the centralized **Library** or creating a custom  Filter Expression of your own design in the **Session Filter** text box, to create focus on specific data you want to analyze while limiting the display of irrelevant data.  
  
-   Choosing a data viewer from the **Start With** drop-down list, or accepting the default viewer setting.  
  
 This section describes how to perform these tasks by using the integrated features of Message Analyzer. In the discussions that follow, see the following figure for the location of referenced features.  
  
 ![Live Trace Session configuration](../messageanalyzer_content/media/fig20-live-trace-session-configuration.PNG "Fig20-Live Trace Session configuration")  
  
 **Figure 20:  Live Trace Session configuration**  
  
## Live Trace Session Workflow Overview  
 The following steps are an overview of the workflow that you can follow when configuring a Live Trace Session:  
  
1.  Begin new session configuration by clicking the **New Session** button on the Message Analyzer **Start Page** to display the **New Session** dialog, from where you specify a **Live Trace** as the data source, as described in [Starting a Message Analyzer Session](../messageanalyzer_content/starting-a-message-analyzer-session.md).  
  
2.  Click the **Live Trace** button in the **New Session** dialog to display the configuration features that you can use for your Live Trace Session.  
  
3.  Accept the default **Localhost** specification in the **Target Computers** text box of the **New Session** dialog, or specify connection information for one or more target computers from which to capture data in the **Edit Target Computers** dialog that is accessible by clicking the **Edit...** button on the **Live Trace** tab, as described in [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md).  
  
4.  Select a built-in **Trace Scenario** to focus on messages at a particular stack level or messages from a device, application, or target computer, as described in [Selecting a Trace Scenario](../messageanalyzer_content/selecting-a-trace-scenario.md); you can also select a custom **Trace Scenario** template that you created, as described in [Using a Custom Trace Scenario Template](../messageanalyzer_content/using-a-custom-trace-scenario-template.md).  
  
5.  Optionally, select one or more system ETW Providers from the **Add System Providers** dialog, which is accessible from the **Add Providers** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog, to enhance the scope of the data capture, as described in [Adding a System ETW Provider](../messageanalyzer_content/adding-a-system-etw-provider.md).  
  
6.  Modify settings that can impact the performance and focus of message providers, which can include specifying **Fast Filters**, **WFP Layer Set** filters, adapter filters, NDIS stack filters, Hyper-V-Switch extension layer filters, packet filters, and event **Keyword** and **Level** filters, depending on the message provider/s in use, as described in [Modifying Default Provider Settings](../messageanalyzer_content/modifying-default-provider-settings.md).  
  
7.  Optionally, set the stack level to which Message Analyzer will parse, by specifying a **Parsing Level** in the **New Session** dialog to improve performance and focus trace results, as described in [Setting the Session Parsing Level](../messageanalyzer_content/setting-the-session-parsing-level.md), or use the default **Full** parsing specification.  
  
8.  Optionally, optimize the ETW buffer configuration and Flush Timer interval from the **ETW Session – Advanced Configuration** dialog, if you expect that packets will be dropped in your scenario, as related to the criteria described in [Specifying Advanced ETW Session Configuration Settings](../messageanalyzer_content/specifying-advanced-etw-session-configuration-settings.md).  
  
9. Optionally, specify a **Session Filter** to focus on specific message data that meets the criteria of the Filter Expression that you select from the centralized **Library** on the toolbar above the **Session Filter** text box in the **New Session** dialog, or configure your own Filter Expression, as described in [Working with Session Filters in a Live Trace Session](../messageanalyzer_content/working-with-session-filters-in-a-live-trace-session.md).  
  
10. Optionally, choose a data viewer from the **Start With** drop-down list in the **New Session** dialog for the display of Live Trace Session results, for example, the **Analysis Grid** viewer or the **Gannt** viewer, as described in [Selecting a Session Data Viewer](../messageanalyzer_content/selecting-a-session-data-viewer.md).  
  
11. Optionally rename your scenario in the **Name** text box and click the **Save Scenario** button in the **New Session** dialog to save your scenario with the customized settings that you specified, so that you can run it again on demand, as described in [Saving Trace Scenarios](../messageanalyzer_content/saving-trace-scenarios.md).  
  
12. Click **Start** in the **New Session** dialog to begin capturing data with your configured Live Trace Session.  
  
## Trace Scenario Configuration Overview  
 When configuring a Live Trace Session, you can select from a number of built-in **Trace Scenarios** that contain various provider configurations that perform common or focused tasks, as indicated in the table in the [Built-In Trace Scenarios](../messageanalyzer_content/built-in-trace-scenarios.md) section. You can also configure your Live Trace Session to use additional system ETW Providers that are accessible from the **Add System Provider** dialog, as described earlier.  However, if you include a system ETW Provider in your Live Trace Session configuration, you should be familiar with how to use it, which includes how to configure it to write specific events that you are interested in capturing through **Keyword** selection. For example, for system ETW Providers that define error **Level** and event **Keyword** values, you can  configure the error verbosity level and specific events to capture by selecting them on the **ETW Core** tab of the **Advanced Settings** dialog for any provider, to further refine the focus of the data retrieval action of the overall provider set in use.  
  
 You might be able to learn more about the events that a system ETW Provider writes if you can locate and review its manifest, which can define such information. This will ensure that you have a viable data capture configuration and understandable trace results. For more information about the **Keywords** that define the events that a provider captures, see [Using System ETW Providers as an Input Source](../messageanalyzer_content/targeting-live-data-as-an-input-source.md#BKMK_ETWProvidersInputSource) and [Finding System ETW Provider Metadata](../messageanalyzer_content/system-etw-provider-event-keyword-level-settings.md#BKMK_FindingKeywords).  
  
 Also, to narrow the focus of your Live Trace Session to retrieving specific message data of interest only, you can apply a **Session Filter** as previously described. However, you should note that applying a **Session Filter** can have an impact on parsing time.In addition, you can modify low-level provider settings and/or set a **Parsing Level** to improve performance and focus results.  
  
 Message Analyzer also provides you with the flexibility needed to ensure that your Live Trace Sessions are easily accessible and configurable, productive, and simple to save. Essentially, you can configure a Live Trace Session based on any of the following:  
  
-   A built-in **Trace Scenario**.  
  
-   A **Trace Scenario** that you previously created as a custom template.  
  
-   One or more Windows system ETW Providers.  
  
-   A combination of Microsoft-PEF and Windows system ETW Providers.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about creating your own **Trace Scenarios**, see [Creating and Managing Custom Trace Scenarios](../messageanalyzer_content/creating-and-managing-custom-trace-scenarios.md).   
___________________\_  
  
## Live Trace Session Configuration Features  
 The following subtopics provide further details about Message Analyzer's Live Trace Session configuration features along with various operations that Message Analyzer supports for live captures:  
  
 [Selecting a Trace Scenario](../messageanalyzer_content/selecting-a-trace-scenario.md)   
 [Using a Custom Trace Scenario Template](../messageanalyzer_content/using-a-custom-trace-scenario-template.md)   
 [Adding a System ETW Provider](../messageanalyzer_content/adding-a-system-etw-provider.md)   
 [Modifying Default Provider Settings](../messageanalyzer_content/modifying-default-provider-settings.md)   
 [Selecting Data to Capture](../messageanalyzer_content/selecting-data-to-capture.md)   
 [Working with Session Filters in a Live Trace Session](../messageanalyzer_content/working-with-session-filters-in-a-live-trace-session.md)   
 [Specifying Advanced ETW Session Configuration Settings](../messageanalyzer_content/specifying-advanced-etw-session-configuration-settings.md)   
 [Configuring a Remote Capture](../messageanalyzer_content/configuring-a-remote-capture.md)   
 [Selecting a Session Data Viewer](../messageanalyzer_content/selecting-a-session-data-viewer.md)   
 [Decrypting TLS and SSL Encrypted Data](../messageanalyzer_content/decrypting-tls-and-ssl-encrypted-data.md)  
  
 _____________________\_  
  
 **Capturing the Data**   
When you are ready to capture data with Message Analyzer, see [Performing a Live Capture](../messageanalyzer_content/performing-a-live-capture.md) to review several methods for starting a live capture.   
_____________________\_  
  
## See Also  
 [Message Analyzer User Roles](../messageanalyzer_content/message-analyzer-user-roles.md)