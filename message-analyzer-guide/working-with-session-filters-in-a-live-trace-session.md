---
title: "Working with Session Filters in a Live Trace Session | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2efa2a6-2335-4db9-b4a6-bb2c2a3a8261
caps.latest.revision: 45
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Working with Session Filters in a Live Trace Session
Prior to starting any Live Trace Session, you can specify a **Session Filter** that will be applied by the Runtime in *user mode* to messages captured by one or more message providers that are included in the **Trace Scenario** you selected. To specify a **Session Filter**, you can select one of the built-in filters from the centralized **Message Analyzer Filter** asset collection **Library**. This user **Library** is accessible from the following locations during the indicated session phases, although you can  only use the first location below to specify a **Session Filter**:  
  
> [!NOTE]
>  You can also create your own Filter Expression in either of these same locations and save it to the **Library**, at which point you can use it as a **Session Filter**.  
  
-   **Session configuration** — locate a **Session Filter** in the centralized **Message Analyzer Filter** asset collection **Library** drop-down list above the **Session Filter** text box in the **New Session** or **Edit Session** dialog.  
  
-   **Session analysis** — locate a  view **Filter** from the same **Library** on a Filter panel of the Filtering toolbar that appears above the analysis surface of any data viewer in a set of trace results.  
  
> [!NOTE]
>  You can also apply any Filter Expression item in the **Message Analyzer Filter** asset collection **Library** as a **Session Filter** when configuring a Data Retrieval Session. This **Library** is in the identical location as when you are configuring a Live Trace Session in the **New Session** dialog.  
  
> [!IMPORTANT]
>  Although a **Session Filter** can reduce the noise of unwanted traffic and narrow the scope of data capture, Message Analyzer must still parse messages according to the **Session Filter** criteria, which can take time. As a result, there is the possibility that messages could be dropped in very heavy traffic conditions. While you may be able to offset this possibility by configuring **Live Trace Message Buffer** settings (click the **Options** item in the Message Analyzer **Tools** menu and go to the **General** tab of the **Options** dialog), there are limitations on how much you can compensate.  
  
<a name="BKMK_SelectingSessionFilters"></a>   
## Selecting Built-In Session Filters  
 To select a built-in Filter Expression for a Live Trace Session, click the **Library** drop-down list on the toolbar above the **Session Filter** text box in the **New Session** dialog and then select a filter item. After you select a filter, the filter code displays in the **Session Filter** text box. Note that you can optionally modify any built-in **Session Filter** configuration *for the session only*, by specifying your Filter Expression changes prior to starting your Live Trace Session. Note that you cannot alter the default configuration of any built-in Filter Expression item that is contained in the centralized Filter Expression **Library**. The built-in **Library** Filter Expressions that are included by default in Message Analyzer fall into the following categories of application. The functions of the filters that exist in the below categories are described in [Filtering Live Trace Session Results](../messageanalyzer_content/filtering-live-trace-session-results.md), with exception of the **Azure Storage** category:  
  
> [!NOTE]
>  The **Azure Storage** category filters are not described in this Operating Guide, as Microsoft provides related information in Azure blogs and tutorials, which you can access from the topic [Filtering Live Trace Session Results](../messageanalyzer_content/filtering-live-trace-session-results.md). Note that the **Azure Storage** category will only exist in your user **Library** if you download the **Azure Storage Filter** asset package with the use of  the **Asset Manager** dialog.  
  
-   **Azure Storage**  
  
-   **Address Filtering**  
  
-   **Diagnosis**  
  
-   **General Examples**  
  
-   **RegEx**  
  
-   **Contains Filters**  
  
-   **HTTP**  
  
-   **TCP**  
  
-   **LDAP**  
  
-   **Remove Noise**  
  
-   **File Sharing**  
  
-   **USB**  
  
## Creating New Session Filters  
 To create your own **Session Filter**, you can write a Filter Expression in the **Session Filter** text box of the **New Session** or **Edit Session** dialogs prior to starting a Live Trace Session or prior to applying configuration changes to an existing session, respectively. You can then click the **New Filter** item in the **Library** drop-down list to display the **Edit Filter** dialog, which captures the filter code that you specified and enables you to **Save** the new Filter Expression to the **Examples** category of your user **Library**.  
  
 However, before you write a new Filter Expression, you might want to review the topics specified in **More Information** to familiarize yourself with some of the built-in filters provided with Message Analyzer and the Filtering Language with which they were created. Also, to assist you in Filter Expression development, Message Analyzer provides the Filter IntelliSense Service, which activates as soon as you begin typing in the **Session Filter** text box. You can also open the **Field Chooser** **Tool Window** and navigate through the message hierarchy of supported protocols to see a tree list view of such hierarchies, so that you can discover at a glance the defined fields that are accessible for your Filter Expressions.  
  
 You can also create and save a view **Filter** in an Analysis Session, which is then added to the centralized **Message Analyzer Filter** asset collection  **Library**; at which point you can select that filter from the **Library** on the toolbar above the **Session Filter** text box of the **New Session** or **Edit Session** dialog to add it as a **Session Filter** to a current or subsequent Live Trace Session or Data Retrieval Session.  
  
 To create a new Filter Expression from any of the previously indicated locations, you must select the **New Filter** item in the centralized **Library** drop-down list. Thereafter, the **Edit Filter** dialog displays, from where you can create a new Filter Expression, either by developing a new filter configuration or by modifying an existing/predefined Filter Expression from the **Library**.  
  
> [!NOTE]
>  If you have created a Filter Expression that uses an **Alias** (typically a friendly name that replaces some cryptic field value), that filter will appear in your user **Library** drop-down list in the  **New Session** dialog. You can use such a Filter Expression that contains an **Alias** just as you would any other filter.  
  
## Applying a Session Filter  
 As described in several topics in this Operating Guide, adding a **Session Filter** to your Live Trace Session configuration enables you to focus on capturing specific data of interest after you have started a Live Trace Session. **Session Filters** also enable you to reduce message count and realize better performance. When you start a Live Trace Session, the messages that are captured by one or more providers in the **Trace Scenario** that you selected for the session are all automatically subjected to the filtering criteria of the **Session Filter** that you specified.  
  
> [!NOTE]
>  When you apply a **Session Filter** to a Live Trace Session, a funnel icon displays to the right of the corresponding top-level session node in the **Session Explorer** **Tool Window**, to indicate that the session has had a **Session Filter** applied to it. This icon provides a quick reminder of the initial configuration status of the session.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using the Filtering Language, see [Writing Filter Expressions](../messageanalyzer_content/writing-filter-expressions.md).   
**To learn more** about the built-in filters in the centralized **Message Analyzer Filter** asset collection **Library** that are provided with Message Analyzer, see [Filtering Live Trace Session Results](../messageanalyzer_content/filtering-live-trace-session-results.md).   
**To learn more** about using the statement completion feature for Filter Expressions, see the [Filter IntelliSense Service](../messageanalyzer_content/filter-intellisense-service.md) topic.  
**To learn more** about the **Field Chooser**, see the [Field Chooser Tool Window](../messageanalyzer_content/field-chooser-tool-window.md) topic.  
___________________\_  
  
## See Also  
 [Filtering Message Data](../messageanalyzer_content/filtering-message-data.md)