---
title: "Applying and Managing Filters | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e05606b9-674c-4bab-9714-a54e012a289b
caps.latest.revision: 101
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Applying and Managing Filters
After you display message data in one or more of the Message Analyzer data viewers, you can apply a view **Filter** to reduce the scope of the data presented in a viewer according to filtering criteria that you define. This enables you to create a concise focus on the data you want to analyze. A view **Filter** enables you to target and isolate specific information for presentation and analysis, while  preserving the original contents of your session results. For example, after you **Apply** a particular  **Filter** from the Filter Expression **Library**, you can simply undo the filtering action by clicking the **Remove** command on the  **Filter** panel, which appears whenever you click the **Add Filter** button on the Message Analyzer Filtering Toolbar. By executing the **Remove** command, Message Analyzer redisplays the trace results that existed immediately prior to applying the  **Filter** you are removing.  
  
 Note that all  built-in **Filters** are available from a common  **Library** and are based on the Filtering Language that is described in [Writing Filter Expressions](writing-filter-expressions.md). This **Library** contains the same Filter Expressions that are available as **Session Filters** when configuring a Live Trace Session or a Data Retrieval Session. The built-in **Filters** are provided by the **Message Analyzer Filters** asset collection, which is included with every Message Analyzer installation.  
  
 **Generating  Filters**   
You can display the controls and features you will need to create, apply, and remove one or more  **Filters** by clicking the **Add Filter** button on the Message Analyzer Filtering Toolbar that appears above any in-focus session viewer tab. A single set of the indicated controls and features displays on a Message Analyzer **Filter** panel by default; however, you can display additional  Filter panels for enhanced filtering, as described in [Using the Filtering Toolbar](using-the-filtering-toolbar.md). To generate the code for a view **Filter**, use any of the following methods:  
  
-   Select a built-in view **Filter** from the centralized Filter Expression **Library** drop-down list that appears whenever you click the **Add Filter** button on the Message Analyzer Filtering Toolbar.  
  
-   Utilize the IntelliSense statement completion service to write your own filters in any Filter Expression text box that appears when you click the **Add Filter** button on the Message Analyzer Filtering Toolbar.  
  
-   Automatically and quickly create view **Filter** code with the right-click context menu in the **Analysis Grid** viewer, as described in [Creating Filters from the Analysis Grid Context Menu](applying-and-managing-filters.md#BKMK_CreateFilterFromAG).  
  
-   Automatically and quickly create view **Filter** code with the right-click context menu in the **Details** **Tool Window**, as described in [Creating Filters from the Details Tool Window Context Menu](applying-and-managing-filters.md#BKMK_CreateFilterFromDetails).  
  
> [!NOTE]
>  When you use the methods  described in  the last two bullet points above  to generate  view **Filter** code, the Filter Expression code is added to the Filter Expression text box of the default **Filter** panel that appears whenever trace results are displayed in a data viewer.  
  
 After you generate the view **Filter** code, you must **Apply** the **Filter** for it to take effect, as described in [Applying a Filter](applying-and-managing-filters.md#BKMK_ApplyingViewFilter). Note that an **Apply** button appears in the default **Filter** panel and in each  subsequent **Filter** panel that displays  when you click the **Add Filter** button on the Message Analyzer Filtering Toolbar. Each  **Filter** panel also contains the **Remove**, **Library**, and **History** controls.  
  
<a name="BKMK_ApplyingViewFilter"></a>   
## Applying a Filter  
 By default, the filtering action of a view **Filter** impacts only the data viewer where you apply the view **Filter**, meaning that its action is specific to the current in-focus viewer only. The default action is initiated by  clicking the **Apply** button on the **Filter** panel that is associated with the  Filter Expression that you want to trigger.  
  
> [!TIP]
>  You can also apply a view **Filter** by using the keyboard shortcut `Ctrl+Enter` and you can remove an applied view **Filter** by using the keyboard shortcut `Ctrl+Shift+Enter`. However, the Filter Expression text box in which the view **Filter** code displays must have the focus for this to work properly.  
  
> [!NOTE]
>  A view **Filter** does not alter the original message data that you capture live or load into Message Analyzer. Whenever you run a Live Trace Session or Data Retrieval Session, a View Journal is automatically created as a repository for the results. A view **Filter** simply allows you to return a subset of View Journal data to your session viewer based on specified filtering criteria, for analysis purposes.  
  
<a name="BKMK_WorkWithTieredFiltering"></a>   
## Working with Tiered Filtering Configurations  
 The  Message Analyzer Filtering Toolbar contains the features that enable you to create, apply, and remove multiple view **Filters** against a set of trace results. With these features, you can create tiers of filtering that give you a finer level of control over the filtering process and how you display the data you want to examine. You can enhance your analysis process by selectively applying or removing any  view **Filter** or combination thereof that exists in a set of **Filters** that you created. Consider that if you have a tiered configuration of two or more Filter Expressions, you can alternately select or unselect each view **Filter** to enable or disable it, respectively, and obtain different results based on different combinations of filtering criteria, for enhanced analysis.  
  
 For instance, if you create a  view **Filter** such as `IPv4.Address==192.168.1.1` that enables you to isolate message conversations in which  a specified address participated, you may want to then drill down further into the results to see whether a particular port carried the IP conversations. Instead of discarding the first **Filter**, replacing it with a new Filter Expression, and losing the current set of filtered results, you can click the **Add Filter** button on the Filtering Toolbar to create a new view **Filter** instance such as `UDP.SourcePort==500` to further isolate the data based on that criteria. Thereafter, you can alternately remove and reapply either of these view **Filters** to conveniently display a different set of results that enhances your analysis perspective, or you might **Remove** both view **Filters** to return to the original data set without losing any of the Filter Expression code that you specified.  
  
 **Sample Tiered Filtering Configuration**   
An example of creating a tier of view **Filters** that you can apply and remove is shown in the figure that follows and is described in the procedure below.  
  
 ![Tiered Filter Configuration with AuthIP Filter applied](media/fig51-tiered-filter-configuration-with-authip-filter-applied.png "Fig51-Tiered Filter Configuration with AuthIP Filter applied")  
  
 **Figure 51: Tiered Filter Configuration with AuthIP Filter Applied**  
  
 This example enables you to isolate authentication traffic from the Internet Key Exchange (IKE) cryptographic protocol and the Authenticated Internet Protocol (AuthIP), which is a Microsoft proprietary protocol that is an extension of IKE. Note that AuthIP provides a second authentication level to standard IKE authentication to add support for   user-based authentication using Kerberos v5 or SSL certificates. The procedure captures data at the Link Layer with the **Microsoft-Windows-NDIS-PacketCapture** provider and makes use of four different view **Filters** that you can apply and remove in any combination. This simple example  shows you how to dice and slice the data in various ways to obtain unique perspectives for analysis.  
  
#### To create a tier of Filters that enhance the analysis process  
  
1.  From the **Start** menu, **Start** page, or task bar of a target  computer running the Windows 8.1, Windows Server 2012 R2, or Windows 10 operating system, click the **Microsoft Message Analyzer** icon to launch Message Analyzer. If you have not logged off and back on after first installing Message Analyzer, then start Message Analyzer with the right-click **Run as Administrator** option.  
  
2.  On the Message Analyzer **Start Page**, click the **Start Local Trace** button to begin capturing data at the Link Layer with the **Microsoft-Windows-NDIS-PacketCapture** provider.  
  
     While Message Analyzer is accumulating messages in the default data viewer, typically the **Analysis Grid**, initiate any action that can invoke Kerberos authentication, such as file server resource access or some other site sign-in process. Note that this can occur automatically in Transport Layer Security (TLS) negotiations.  
  
3.  At a suitable point, stop the trace by clicking the **Stop** button on the global Message Analyzer toolbar.  
  
4.  Expand the **TCP** or **UDP** node in the **Field Chooser** **Tool Window** and navigate the message hierarchy until you find the **SourcePort** field; then double-click it to add it as a new column in the **Analysis Grid** viewer.  
  
     This column is immediately populated with the  port numbers used by the corresponding protocol or module messages  in your trace results. Note that the display of column values will change as you apply specific view **Filters** in this procedure.  
  
5.  On the Message Analyzer Filtering Toolbar above the **Analysis Grid** viewer, click the **Add Filter** button three times to display an additional 3 sets of **Filter** panels and Filter Expression text boxes in which to create view **Filter** code. Note that a single **Filter** panel displays by default whenever Message Analyzer displays session results.  
  
6.  In the first Filter Expression text box, type the code `AuthIP`, to create an atomic filter that returns messages from the AuthIP protocol while filtering out everything else, with exception of the AuthIP stacks.  
  
     **Note** The meaning of an atomic filter is described in [Creating Filters from the Analysis Grid Context Menu](applying-and-managing-filters.md#BKMK_CreateFilterFromAG).  
  
7.  Click the **Apply** button on the Filter panel associated with the `AuthIP` filter to provide a concise set of AuthIP messages for analysis.  
  
8.  In the second Filter Expression text box, type the code `IKE`, to create an atomic filter that returns messages from the IKE protocol while filtering out everything else, with exception of the IKE stacks.  
  
9. Click the **Remove** button on the **Filter** panel associated with the `AuthIP` filter and then click the **Apply** button on the **Filter** panel associated with the `IKE` filter to provide a concise set of IKE messages for analysis.  
  
10. In the third Filter Expression text box, type the code `IPv4.Address==<192.168.1.1>` , while substituting appropriately for the placeholder address value in italics.  
  
     When applied, this filter will return only the messages that contain either a **Source** or **Destination** address that matches the specified IP address, thereby providing a concise set of IP conversations where IKE negotiations took place.  
  
    > [!NOTE]
    >  If you want to see only the AuthIP conversations, **Apply** the `AuthIP` filter and **Remove** the `IKE` filter.  
  
11. In the fourth Filter Expression text box, type the code `UDP.SourcePort==500`.  
  
     When applied, this filter will return only those AuthIP or IKE messages on UDP port 500 that provided authentication processes in  the Internet Security Association and Key Management Protocol (ISAKMP) framework of authentication and key exchange.  
  
12. Selectively apply and remove filters in the current tiered configuration in any combination, to expose different sets of information that can be useful for analysis and troubleshooting perspectives.  
  
     For example, if you **Remove** the first two filters `AuthIP` and `IKE` and you **Apply** the second two filters `IPv4.Address==<192.168.1.1>` and `UDP.SourcePort==500`, Message Analyzer will show you all the AuthIP and IKE conversations that transited port 500.  
  
    > [!NOTE]
    >  You are advised to experiment with different combinations of these view **Filters** so you can learn how to use tiered filtering configurations to expose different filtered results sets in a single data viewer and thereby enhance your data analysis process.  
  
## Using the Filter Expression Library  
 Message Analyzer provides a default set of built-in Filter Expression items that are accessible from the **Library** drop-down list that appears whenever you click the **Add Filter** button on the Filtering Toolbar. These **Filters** are sourced from the **Message Analyzer Filters** asset collection that you can manage from the **Manage Filter** dialog, which displays when you click the **Manage** item in the indicated **Library** drop-down list. You can also share this collection or any part of it (including any **Filters** that you have created) with others, by using the **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about the Asset Manager, see the [Asset Manager](asset-manager.md) topic.  
___________________\_  
  
 The centralized Filter Expression **Library** contains built-in **Filters** that you can apply as view **Filters** to data displaying in a chosen data viewer, simply by selecting the **Filter** in the **Library** drop-down list on a displayed  **Filter** panel. For example, you might apply the built-in Filter Expression `*SourcePort == IANA.Port.SMB` to the **Chart** viewer with a specified **Layout** to filter for messages of any protocol that have a **SourcePort** field equal to 445. You could then double-click some element in the **Chart** viewer **Layout**, for example, a bar element in the **Bar** visualizer component to which the filtering was applied, to automatically display the associated messages in a new instance of the **Analysis Grid** viewer for further examination.  
  
 You can also create your own Filter Expressions and add them to the **Library**, as described in [Adding a Custom Filter to the Library](applying-and-managing-filters.md#BKMK_AddCustomFilterToLibrary). Any Filter Expressions that you create and add to the **Library** are stored under a subcategory that you specify under the top-level **My Items** category. However, note that the default set of built-in **Filters** are all contained in the top-level **Message Analyzer** category, with the exception of an **Example** filter that is placed in the **My Items** category by default, for use in Filter Expression development.  
  
## Compiling and Applying a Filter  
 As previously described, you can create your own custom Filter Expression to apply to a set of trace results that are displayed in a chosen data viewer. However, if you create your own Filter Expression, it is subject to successful compilation verification; otherwise you will be unable to use it. Note that Message Analyzer automatically performs a compilation verification of any Filter Expression that you specify on a particular **Filter** panel after you click the **Apply** button on the same panel. This ensures that you have a valid Filter Expression before it is applied to your trace results. If the Filter Expression does not pass the compilation check, an error message displays. At this point, you will need to correct the expression or abandon it. If the Filter Expression does pass the compilation check, the Message Analyzer Runtime will then apply the filter to your trace results.  
  
> [!NOTE]
>  A similar compilation check is also applied to any **Session Filter** that you specify in the **New Session** dialog after you click the **Start** button in the dialog to begin a session, whether you are retrieving saved data or capturing live data.  
  
<a name="BKMK_AddCustomFilterToLibrary"></a>   
## Adding a Custom Filter to the Library  
 If you intend to add a custom-created **Filter** to the centralized Filter Expression **Library** for future use or to share with others, you will first need to display the **Edit Filter** dialog by selecting the **New Filter** item in the **Library** drop-down list on any  **Filter** panel where you intend to configure the Filter Expression. From this dialog, you can specify **Name**, **Description**, and **Category** information. You can also write the code for the  **Filter** in the Filter Expression text box of this  dialog. However, if your custom  filter  code already existed in the  Filter Expression text box of   the **Filter** panel with which you are working at the time you launched the **Edit Filter** dialog, the  Filter Expression code will have been automatically transferred to the dialog for your convenience. After you click the **Save** button in the dialog, Message Analyzer automatically performs a  compilation check to ensure that the Filter Expression successfully compiles before saving it to the **Library** as a new asset. If the Filter Expression is invalid, a **Compile Query Error** message displays. Otherwise, you can assume that compilation succeeded.  
  
> [!TIP]
>  You can expose the code for any  built-in **Filter**, modify it, and then save it under a different name in the **My Items** category of your Filter Expression **Library**. To do this, select the **Create a Copy** command that displays in the context menu that appears when you right-click the **Filter** in the **Manage Filter** dialog, modify the Filter Expression code, and then save it with a new **Name** and in a specified **Category**.  
  
<a name="BKMK_CreateFilterFromAG"></a>   
## Creating Filters from the Analysis Grid Context Menu  
 You can create and apply a  view **Filter** very quickly to your data by right-clicking a data field value in most columns of the **Analysis Grid** viewer column layout and selecting the **Add ‘\<columnName>’ to Filter** command from the context menu that displays. The *columnName* value in the indicated command is a placeholder for the actual name of the **Analysis Grid** viewer column containing the data value that you right-click. The column name is automatically retrieved and displayed in the right-click menu, and when you select it, Message Analyzer builds a Filter Expression based on existing message field data values. For example, by clicking an IPv4 address in the **Destination** column, Message Analyzer automatically builds a Filter Expression such as `IPv4.Destination==192.168.1.1` and adds it to the     Filter Expression text box that displays in the default **Filter** panel. Moreover, by clicking a **Module** column value such as **TCP**, Message Analyzer creates the atomic Filter Expression `TCP`. Note that as a result of the way these filters are created, they are guaranteed to return results.  
  
> [!NOTE]
>  A Filter Expression such as `TCP` is called an *atomic* filter in Message Analyzer because it is a simple, left-hand-side-only filter that does not use an “equals” sign or any operators or combinators such as OR, AND, or NOT.  
  
 You can also save any Filter Expression that you created with the previously specified right-click method. You can also save  Filter Expressions that you create in a similar manner from the **Details** **Tool Window**, as described ahead. For example, when you use the right-click method to create a Filter Expression, the text of the target Filter Expression is automatically transferred to the Filter Expression text box of the default **Filter** panel. To save this filter to your Filter Expression **Library**, first click the **Library** drop-down list and select the **New Filter** command to display the **Edit Filter** dialog. You can then specify a subcategory under the **My Items** top-level category of your **Library**, optionally add **Name** and **Description** information, and then click the **Save** button in the **Edit Filter** dialog to save the new Filter Expression.  
  
<a name="BKMK_CreateFilterFromDetails"></a>   
## Creating Filters from the Details Tool Window Context Menu  
 Similar to the way you create a view **Filter** from the **Analysis Grid** viewer context menu, you can also create a view **Filter** from the **Details** **Tool Window**, by right-clicking any field in the **Name** column of the **Details** window and selecting the **Add  ‘\<fieldName>’ to Filter** context menu item. The *fieldName* value in this command is a placeholder for the actual field name in the **Name** column of the **Details** window.  
  
> [!TIP]
>  If the **Details** window is not displayed, select the **Details 1** item from the **Details** drop-down list in the **Windows** submenu on the Message Analyzer global **Tools** menu to restore it.  
  
 As in the case of creating a view **Filter** from the **Analysis Grid** viewer, selecting the previously indicated context menu command in **Details** for creating a Filter Expression only adds its code to the Filter Expression text box of the default **Filter** panel. To see the results of the automatically configured view **Filter**, you must click the **Apply** button in the default **Filter** panel.  
  
## Managing Filters as Shared Items  
 Your local Filter Expression **Library** contains the default **Message Analyzer Filters** asset collection of **Filter** items plus any items that you create, and you can share all of these items with others. To do this, Message Analyzer provides a simple way to expose your Filter Expression items to others for sharing, or to retrieve Filter Expressions that others have shared. You can share your Filter Expression **Library** items directly with others by using the **Export** feature in the **Manage Filter** dialog to save one or more Filter Expression items to a designated file share. You can also use the **Import** feature in the same dialog to access Filter Expression items that have been shared by others. The **Manage Filter** dialog is accessible by selecting the **Manage Filters** item from the **Library** drop-down list on the **Filter** panel with which you are working.  
  
## Sharing Filters on a Feed  
 You can share your Filter Expression items through a user feed that you configure in the Message Analyzer Sharing Infrastructure. You can create your own feed from the **Settings** tab of the Message Analyzer **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu, and the feed (defined by a designated share or other location) will appear on the **Downloads** page of the same dialog. Thereafter, you can update existing Filter Expression items or add others and make them available to team members or other users through the configured feed, where they can view, synchronize, and download them from the **Downloads** or **Settings** tabs of the **Asset Manager** dialog. However, the synchronization aspect of the publishing feature on user feeds requires some manual configuration at this time to enable updates, as described in [Manual Item Update Synchronization](manual-item-update-synchronization.md).  
  
## Receiving Filter Asset Collection Updates  
 Message Analyzer also has a default **Message Analyzer** subscriber feed on the **Downloads** tab of the **Asset Manager** dialog that enables you to download the **Message Analyzer Filters** asset collection from a Microsoft web service and to synchronize with asset collection updates that are periodically pushed out by the service, as useful Filter Expressions are developed at Microsoft for the community of Message Analyzer users. To receive these updates that will appear in the **Message Analyzer** category of your local Filter Expression **Library**, the **Message Analyzer Filters** asset collection should be in the auto-sync state (circular icon with up and down arrows) on the **Asset Manager** dialog **Settings** tab. At any time, you can perform a download of an auto-synced collection from the **Settings** tab of the **Asset Manager**.  
  
> [!IMPORTANT]
>  The **Message Analyzer Filters** collection is installed by default with Message Analyzer, so it is unnecessary to download the collection each time you start Message Analyzer. But if it is the first time you have started Message Analyzer, you are presented with a **Welcome** dialog that provides you with the choice to opt in or out of automatic updates. If you choose to opt in to auto-syncing updates, then all Message Analyzer asset collections are automatically set to the auto-sync state, including the **Message Analyzer Filters** collection, and no further action is required.  
  
 However, if you opted out, you still have the option to automatically receive periodic collection updates later by setting the **Offline** mode to **Online** on the **Downloads** tab of the **Asset Manager** dialog and clicking the **Sync All Displayed Items** button. This action auto-syncs all asset collections; however, you can set individual collections to the auto-sync state on the **Downloads** tab as you require them. To do this, click the download icon to the right of the collection on the **Downloads** tab and select the **Automatically sync item collection updates when available** option in the **Item Download Options** dialog.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about applying view **Filters**, see [Filtering Message Data](filtering-message-data.md).  
**To learn more** about the Filtering Language and how to write filter expressions, see [Writing Filter Expressions](writing-filter-expressions.md).  
**To learn more** about sharing Message Analyzer Library items, including further details about the common **Manage** ***\<AssetType>*** dialog, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.   
**To learn more** about auto-syncing item collections, see [Managing Asset Collection Downloads and Updates](managing-asset-collection-downloads-and-updates.md).   
___________________\_  
  
## See Also  
 [Using the Filtering Toolbar](using-the-filtering-toolbar.md)   
 [Applying and Managing Viewpoints](applying-and-managing-viewpoints.md)   
 [Applying a Time Filter to Session Results](applying-a-time-filter-to-session-results.md)