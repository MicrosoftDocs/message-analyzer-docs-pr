---
title: "Filtering Live Trace Session Results | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37fdb0f4-05a4-4d48-a449-7a8ea9d5da9e
caps.latest.revision: 80
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Filtering Live Trace Session Results
After you capture data in a Live Trace Session, load data through a Data Retrieval Session, or load data using the **Open** or **Recent Files** features, you will typically analyze your trace results in one of the Message Analyzer data viewers, such as the default **Analysis Grid** viewer. As part of analysis, it is likely that you will need to manipulate the trace results to expose specific information that you want to examine. In Message Analyzer, a primary method for isolating specific data during trace results analysis is to apply a view **Filter**, which temporarily alters the data that Message Analyzer displays according to applied filtering criteria. When you finish analyzing the effects of the applied view **Filter**, you can simply click the **Remove** button on the Filtering toolbar to remove the filter and return to the original trace session results.  
  
 You can specify a view **Filter** in any of the following ways:  
  
-   **Predefined configuration** — select a built-in Filter Expression from the **Message Analyzer Filters** asset collection in the centralized user **Library** on the Filtering toolbar, which is located in the upper sector of every session viewer tab.  
  
-   **Dynamic configuration** — right-click a column field in the **Analysis Grid** viewer to display a context menu that enables Message Analyzer to automatically configure a view **Filter** that is coded with a corresponding field value.  
  
     For example, you could right-click an address value in the **Analysis Grid** grid under the **Destination** column and then select the **Add “Destination” to Filter** command in the context menu that appears, to encode the right-clicked Destination address in a new Filter Expression, which might look similar to the following when complete:  `WFPCapture.Destination == 192.168.1.1`, that is, if you used the **Microsoft-Pef-WFP-MessageProvider** to capture the messages.  
  
-   **Manual configuration** — manually configure a Filter Expression in the *filter expression* text box on the Filtering toolbar.  
  
     To learn more about manually configuring Filter Expressions, see [Writing Filter Expressions](writing-filter-expressions.md).  
  
## Using the Filtering Toolbar to Apply and Remove a View Filter  
 After you specify a Filter Expression on the Filtering toolbar for the data in a particular session viewer tab and you click the **Apply** button on the toolbar, the filter isolates the message data that meets the filtering criteria that you specified, such that only those messages are visible. However, a view **Filter** does not modify the original data set, as Message Analyzer persists the full data set such that you can redisplay it whenever you remove the specified view **Filter**. In addition, when you click the **Remove** button on the Filtering toolbar to undo the results of a view **Filter** that you applied to a set of messages, the Filter Expression text in the  text box on the Filtering toolbar remains unchanged. This enables you to retain the Filter Expression text should you decide to reapply it, as described in [Working with Tiered Filtering Configurations](applying-and-managing-filters.md#BKMK_WorkWithTieredFiltering). For example, if you have a tiered configuration of two or more Filter Expressions, you can alternately select or unselect each filter to enable or disable it, respectively, and obtain different results based on different combinations of filtering criteria, for enhanced analysis.  
  
> [!NOTE]
>  After you apply a view **Filter**, Message Analyzer indicates the number of messages that passed the filtering criteria by providing an indication next to the **Available** label in the lower-left sector of the Message Analyzer user interface.  
  
 Whenever you apply a built-in or manually-configured view **Filter**, Message Analyzer conveniently persists the Filter Expression text that you specified for future use.  This enables you to access up to the last ten applied **Filters** by clicking the **History** drop-down list on the Filtering toolbar and selecting a chosen filter. In the **History** list, previously applied filters are displayed in chronological order, with the most recent applied filter as the first one in the list.  
  
<a name="BKMK_AssesBuiltInFilters"></a>   
## Assessing the Built-In Filter Expressions  
 Every Message Analyzer installation provides built-in Filter Expressions in a centralized **Library** that contains the **Message Analyzer Filters** asset collection, which is updateable from the [Asset Manager](asset-manager.md) dialog. In the **Library**, these Filter Expressions are contained in 12 different categories, in addition to an **Examples** category that contains an example filter that you can modify as required, so you can get started with developing Filter Expressions of your own. These categories and the filters they contain are described in the sections that follow. You are advised to assess these filters prior to applying them so that you will be able to more clearly recognize their effects upon trace results.  
  
 The categories in which the built-in Message Analyzer Filter Expressions are contained are described in the following sections:  
  
-   [Azure Storage Category](filtering-live-trace-session-results.md#BKMK_AzureFilterNote)  
  
-   [Address Filtering Category](filtering-live-trace-session-results.md#BKMK_AddressFilteringCat)  
  
-   [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums)  
  
-   [General Examples Category](filtering-live-trace-session-results.md#BKMK_GeneralExamples)  
  
-   [RegEx Category](filtering-live-trace-session-results.md#BKMK_RegEx)  
  
-   [Contains Filters Category](filtering-live-trace-session-results.md#BKMK_ContainsFilters)  
  
-   [HTTP Category](filtering-live-trace-session-results.md#BKMK_HTTPFilters)  
  
-   [TCP Category](filtering-live-trace-session-results.md#BKMK_TransportExamples)  
  
-   [LDAP Category](filtering-live-trace-session-results.md#BKMK_LDAPFilters)  
  
-   [Remove Noise Category](filtering-live-trace-session-results.md#BKMK_RemoveNoiseFilters)  
  
-   [File Sharing Category](filtering-live-trace-session-results.md#BKMK_FileSharingCategory)  
  
-   [USB Category](filtering-live-trace-session-results.md#BKMK_USBFilters)  
  
-   [Examples Category](filtering-live-trace-session-results.md#BKMK_ExamplesFilter)  
  
> [!IMPORTANT]
>  The **Azure Storage** category filters are not described in this section, as Microsoft provides related information in Azure blogs that you can access, as indicated immediately below.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about troubleshooting Azure storage logs, see the following documentation:   
[End-to-End Troubleshooting Using Azure Storage Metrics and Logging, AzCopy, and Message Analyzer](https://azure.microsoft.com/en-us/documentation/articles/storage-e2e-troubleshooting/)  
[Monitor, Diagnose, and Troubleshoot Microsoft Azure Storage](https://azure.microsoft.com/en-us/documentation/articles/storage-monitoring-diagnosing-troubleshooting/)  
___________________\_  
  
<a name="BKMK_AddressFilteringCat"></a>   
## Address Filtering Category  
 This filtering category contains several filters that isolate data based on Ethernet, IPv4, or IPv6 addresses, as follows:  
  
-   **\*Address==02-01-0A-01-01-64** — filters out all messages except those that are intended for a specified MAC address, such as that of an Ethernet adapter.  
  
-   **IPv4.Address in 10.1.0.0/16** — filters for a particular IPv4.Address in a subnetwork generated by a specified subnet mask, which in the example is indicated by 16 (=255.255.0.0).  
  
-   **IPv4.Address ==**  ***192.168.1.1***  — filters out all messages except those that contain a **Source** or **Destination** address that matches the specified IPv4 address value.  
  
    > [!NOTE]
    >  Before applying any of these filters, you should substitute your actual search address for the *italic* values in these Filter Expressions. The same is true of any built-in Filter Expression that has placeholder values.  
  
-   **IPv4.Address ~=**  ***192.168.1.1***  — filters out all IPv4 messages that contain a **Source** or **Destination** address that matches the specified IPv4 address value. Use of the tilde (~) character ensures that you will only return IPv4 traffic. Otherwise, other traffic would not be blocked.  
  
     For example, if you specified the Filter Expression as `IPv4.Address != 192.168.1.1` or `!(IPv4.Address == 192.168.1.1)`, all protocol messages that do not meet this criteria are returned, which means you would get all messages that are not IPv4 messages in addition to the target IPv4 traffic. However, as an alternative, you could add “`&& IPv4`” to either  expression if you want to pass only IPv4 messages.  
  
    > [!NOTE]
    >  The Filter Expression `!(IPv4.Address == 192.168.1.1)` is semantically equivalent to `IPv4.Address != 192.168.1.1`. For more details about the use of the “!” operator, see [Other Filtering Considerations](understanding-the-filtering-language-basics.md#BKMK_OtherFilteringConsiderations).  
  
-   **IPv6.Address ==**  ***2001:4898:0:FFF:200:5EFE:4135:4A7***  — filters out all messages except those that contain a **Source** or **Destination** address that matches the specified IPv6 address value.  
  
-   **\*Address ==**  ***192.168.1.1***  **or \*Address ==**  ***2001:4898:0:FFF:200:5EFE:4135:4A7***  — filters out all messages except those that contain a **Source** or **Destination** address that matches either the specified IPv4 address or IPv6 address value. *Address can also specify an Ethernet address.  
  
    > [!NOTE]
    >  By using the expression “*Address”, you can mix IPv4 and IPv6 addresses in this Filter Expression.  
  
<a name="BKMK_DiagnosisEnums"></a>   
## Diagnosis Category  
 This filtering category enables you to identify messages that have parsing errors. There are two types of filters in this category that reflect OPN parsing errors. These consist of **DiagnosisLevels**, which indicate parsing error severity level; and **DiagnosisTypes**, which describe the source of errors that can occur during parsing:  
  
-   **#DiagnosisLevels** — this filter passes all messages that have a diagnosis-level error. This Filter Expression is semantically equivalent to `#DiagnosisLevels != nothing`. If you want to be more specific, you can specify different enumeration values to filter for certain diagnosis levels. In the table that follows, friendly enumeration names are given along with their equivalent integer values that you can include as right-hand side values in this Filter Expression:  
  
    ### Table 15.   Enum Values for DiagnosisLevel Filters  
  
    |Filter Expression with Friendly Enum Name|Filter Expression with Integer Enum Value|Description|  
    |-----------------------------------------------|-----------------------------------------------|-----------------|  
    |#DiagnosisLevels==Standard.DiagnosisLevel.Error|#DiagnosisLevels==1|Filters for messages that contain an Error-diagnosis level.|  
    |#DiagnosisLevels==Standard.DiagnosisLevel.Warning|#DiagnosisLevels==2|Filters for messages that contain a Warning-diagnosis level.|  
    |#DiagnosisLevels==Standard.DiagnosisLevel.Information|#DiagnosisLevels==4|Filters for messages that contain an Information-diagnosis level.|  
  
    > [!NOTE]
    >  In the Filtering Language, **DiagnosisLevels** is a global annotation, meaning that it is applicable to any OPN message. The character “#” provides access to an annotation, as differentiated from other filters that use a dot (.) operator to enable access to a field.  
  
-   **#DiagnosisTypes==2** — this filter passes any messages that contain validation type diagnosis errors that occurred during the OPN message ValidationCheck, as part of the parsing process. A validation error is a *soft* error, meaning that it is not severe enough to halt the parsing process. Validation errors typically occur when a message deviates from associated protocol specifications, which can include occurrences such as out-of-range values, invalid collection sizes, data element constraint violations, and so on.  
  
     **DiagnosisTypes** is described in the OPN language as a flag pattern, which is a special type of enum. The table that follows specifies the enumeration values of the **DiagnosisTypes** enum that you can use in a **DiagnosisTypes** filter. Friendly enumeration names are given along with their equivalent integer values. You can specify the enum values in either format as right-hand side values in this Filter Expression.  
  
    ### Table 16.  Enum Values for DiagnosisType Filters  
  
    |Filter Expression with Friendly Enum Name|Filter Expression with Integer Enum Value|Description|  
    |-----------------------------------------------|-----------------------------------------------|-----------------|  
    |#DiagnosisTypes == Standard.DiagnosisType.Application|#DiagnosisTypes==1|Filters for messages that contain Application-type diagnosis errors, for example, an application-related or network communication issue.|  
    |#DiagnosisTypes == Standard.DiagnosisType.Validation|#DiagnosisTypes==2|Filters for messages that contain Validation-type diagnosis errors. A Validation error is an indication that a message does not align with its protocol definition.|  
    |#DiagnosisTypes == Standard.DiagnosisType.InsufficientData|#DiagnosisTypes==4|Filters for messages that contain InsufficientData-type diagnosis errors. An InsufficientData error is an indication that message data was lost, for example, when Message Analyzer is attempting to group messages into an operation or when performing data reassembly.|  
    |#DiagnosisTypes == Standard.DiagnosisType.Parsing|#DiagnosisTypes==8|Filters for messages that contain Parsing-type diagnosis errors. A Parsing error is an indication that parsing failed when Message Analyzer attempted to decode invalid message data.|  
  
<a name="BKMK_GeneralExamples"></a>   
## General Examples Category  
 This filtering category contains an example of how to AND two expressions together and an example of how to specify an explicit path to a field value in the TCP message hierarchy:  
  
-   **HTTP and !UDP** — this filter passes all messages that do not have HTTP over UDP.  
  
-   **TCP::Flags:SYN == true** — this filter uses an explicit path expression to pass TCP messages that have their SYN bit set (0x02). Note that the missing value between the double colons (::) is the **Segment** message-type specifier.  
  
    > [!TIP]
    >  You could also specify the equivalent of this Filter Expression as: “`TCP:Segment::SYN==true`” or even “`TCP:::SYN==true`”, to obtain an identical filtering result. At a minimum, an explicit path expression should specify a protocol or module as the first entity in the left-side expression and the field for which you are searching in a particular message hierarchy as the last entity in the expression, separated by an appropriate number of colons to delimit any skipped hierarchical entities. However, for the best performance, you should specify all entities in an explicit path.  
  
<a name="BKMK_RegEx"></a>   
## RegEx  
 Message Analyzer provides several regular expressions (RegEx) that you can use as view **Filters**, as follows:  
  
-   **regex "(?!000)([0-6]\\\d{2}&#124;7([0-6]\\\d&#124;7[012]))([ -]?)(?!00)\\\d\\\d\\\3(?!0000)\\\d{4}"** — enables you to find a phone number pattern.  
  
-   **regex @"^([\w\\.\\-]+)@([\w\\-]+)((\\.(\w){2,3})+)$"**— enables you to find an email address pattern.  
  
-   **regex @"^\d{3}-\d{2}-\d{4}$"** — enables you to find a social security number.  
  
-   **regex @"\bthis\W+(?:\w+\W+){1,6}?that\b"** — enables you to find the string “this” near the string “that”.  
  
<a name="BKMK_ContainsFilters"></a>   
## Contains Filters Category  
 This filtering category contains filters that you can use to search for various strings and values in your trace results. You can search for messages that contain specified text in case-sensitive and case-insensitive searches. You can also locate hexadecimal patterns with this type of filter:  
  
-   **\*Summary contains “error”** — this filter searches the **Summary** column for all messages in the **Analysis Grid** viewer that contain the text "error".  
  
-   **contains "Microsoft" caseSensitive** — this filter performs case-sensitive filtering that passes all messages containing the specified “Microsoft” search text. The default insensitive encoding will match ASCII, Unicode, or any other encoding type.  
  
-   **contains "Microsoft" encoding ASCII** — this filter performs case-sensitive filtering that passes all messages containing the specified search text in the supplied query encoding. The query encoding value can be any of the following:  ASCII, UTF7, UTF8, Unicode, UTF32, BigEndianUnicode, and Base64.  
  
-   **contains "Microsoft"** — this filter performs case-insensitive filtering that passes all messages containing the specified search text.  
  
-   **contains $[**  ***534d42***  **]** — this filter passes messages that contain the specified hexadecimal pattern, which in this example represents the ASCII characters for “SMB”.  
  
<a name="BKMK_HTTPFilters"></a>   
## HTTP Category  
 This filtering category contains filters that isolate HTTP messages with errors, specified address text, and a specific stack configuration.  
  
-   **HTTP.StatusCode >= 400** — returns HTTP client and server error messages that have a StatusCode that is greater than or equal to 400, for troubleshooting purposes.  
  
-   **HTTP.Uri contains "msn"** — isolates HTTP addresses that contain the text "msn". The filtering criteria are both case- and encoding-insensitive.  
  
-   **HTTP\TCP.Port == IANA.Port.HTTP** — passes messages where HTTP is directly above TCP, as defined by the stack path specification “`HTTP\TCP.Port`”. By using the stack path specifier “\”, you can increase the specificity of your Filter Expressions.  
  
<a name="BKMK_TransportExamples"></a>   
## TCP Category  
 This filtering category contains various Transport Layer filters that isolate TCP messages based on various criteria such as TCP ports, flags, window size, and options, as follows:  
  
-   **tcp.port == IANA.Port.HTTP** — enables you to filter for HTTP over TCP traffic in either direction. You can also substitute a port number in this expression, for example, “tcp.port == 80”.  
  
-   **TCP.SourcePort in [**  ***6608*** , ***6609***, ***6610*** **]** — this filter passes all TCP messages that have a source port of 6608, 6609, or 6610.  Note that the *italic* source port numbers in this expression are unassigned ports that serve as placeholders only.  
  
-   **tcp.options** — this filter passes only the TCP messages that have TCP options defined.  
  
-   **tcp.syn == true** — this filter passes TCP messages that have their SYN bit set (0x02). If you want to pass all TCP messages that specify the SYN field, you can drop the Boolean evaluation and apply the Filter Expression as: “`tcp.syn`”.  
  
    > [!NOTE]
    >  Although there is a **Segment** message type and a **Flags** container in the upper hierarchy for the **SYN** flag, it is unnecessary to specify a fully qualified expression such as “`TCP.Segment.Flags.SYN`”. In the Filtering Language, the dot notation is commonly used to traverse the message type-hierarchy, which is shown in the **Field Chooser** **Tool Window**. A dot (.) in a Filter Expression means the filter should find any entity at any depth in the hierarchy, hence in this example: `tcp.syn==true`. However, to improve performance, you can create an explicit path that uses colons, as indicated in the text of the earlier Filter Expression `TCP::Flags:SYN == true`.  
  
-   **TCP.Windowscaled \<**  ***1000***  — this filter passes TCP messages having a receive window size that is less than 1000.  
  
     Note that TCP Window Scaling increases the TCP receive window size above its default maximum value of 65,535 bytes for better throughput, for example, in cases where a receiver is overwhelmed with high message volumes such as a web server might be.  
  
    > [!NOTE]
    >  If you encounter a bottleneck, it might be caused by a small TCP receive window size that should be increased above the default setting by using a tool such as **netsh**. Windows 7, Windows 8, Windows 8.1, and Windows Server 2012 operating systems provide a Receive Window Auto-Tuning Level configuration that is set by default to “Normal”, which allows the TCP receive window size to grow automatically to accommodate most conditions. If TCP Auto-Tuning is disabled, the receive Window size is limited to the default size of 65,535 bytes (64 KB).  
  
<a name="BKMK_LDAPFilters"></a>   
## LDAP Category  
 This filtering category contains an LDAP filter that removes all traffic that transits the LDAP port.  
  
-   **\*Port != IANA.Port.LDAP** — removes all LDAP port traffic, regardless of the protocol. Port represents either SourcePort or DestinationPort for UDP and TCP messages, or any protocol with a field or property named Port. The asterisk in the expression “*Port” indicates that the filter should look at any protocol that defines a field or property named “Port” and filter out any LDAP port traffic that might have been invoked by that protocol. This filter will also pass messages from any protocol where a Port field is nonexistent.  
  
<a name="BKMK_RemoveNoiseFilters"></a>   
## Remove Noise Category  
 This filtering category contains filters that remove unwanted messages so that you can display a more streamlined message set.  
  
-   **!(\*Port in [3389, 1494, 1503])** — removes all Remote Desktop messages that traverse ports 3389, 1494, and 1503 in either direction, for various remote desktop (RDP) communication protocols.  
  
-   **WiFi.FrameControl.Type !=0** — removes Wi-Fi noise by filtering out beacons.  
  
<a name="BKMK_FileSharingCategory"></a>   
## File Sharing Category  
 This filtering category contains several examples that you can use to filter trace results for SMB messages with diagnosis errors, SMB messages with a **Filename** field defined, or any file sharing traffic captured on TCP port 445:  
  
-   **\*SMB.FileName ~= "" OR SMB2.FileName ~= ""** — this filter passes only SMB and SMB2 messages that have a FileName field defined, in which the field value is not equal to an empty string. This Filter Expression is not the same as `SMB.FileName != "" OR SMB2.FileName != ""`, which returns non-SMB traffic as well. By using the tilde (~) character in this filter, you ensure that only SMB traffic is returned.  
  
-   **SMB#DiagnosisLevels** — this filter passes all SMB messages that have parsing errors. This filter is equivalent to the expression `SMB && #DiagnosisLevels`. You can also apply any of the enumeration values specified by the table in [Diagnosis Category](filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) to this Filter Expression. For example, you could specify `SMB#DiagnosisLevels== Standard.DiagnosisLevel.Warning` to return all SMB messages that contain a Warning diagnosis level.  
  
-   **\*Port == IANA.Port.SMB** — this filter passes messages from any protocol that has a top-level source or destination Port field equal to 445, including TCP and UDP. It also returns any top-level protocol that has a field or property named “Port”.  
  
<a name="BKMK_USBFilters"></a>   
## USB Category  
 This category contains an example of filtering for USB transfer messages that contain errors:  
  
-   **Microsoft_Windows_USB_USBPORT.fid_URB_Hdr_Status ~= 0** — this filter passes all messages from the **Microsoft-Windows-USB-USBPORT** provider that contain the Fid_URB_Hdr_Status field with a value not equal to zero, indicating an error condition. Note that this Filter Expression is not the same as `Microsoft_Windows_USB_USBPORT.fid_URB_Hdr_Status != 0`, which returns all messages captured by the provider, whether it had the specified field or not.  
  
<a name="BKMK_ExamplesFilter"></a>   
## Examples Category  
 The **Examples** filtering category exists under **My Items**, where all view **Filters** that you create and save with the **Edit Filter** dialog are displayed. The **Edit Filter** dialog is accessible by clicking the **New Filter** item in the **Library** drop-down list in any Filter panel on the Filtering toolbar. The **Examples** category contains a single filter that you can modify as you like, so that you can get started with creating your own filters.  
  
> [!NOTE]
>  Any Filter Expression that you create becomes part of your centralized user **Library** and is available to you as **Session Filter** whenever you are configuring a Data Retrieval Session or Live Trace Session. Such a Filter Expression is also available to you as a view **Filter** whenever you are analyzing trace results in an Analysis Session. In addition, note that Filter Expressions you create can contain an **Alias** or a **Union**, as appropriate.  
  
 The Filter Expression that is included as a startup example is specified as follows:  
  
-   **HTTP** — this filter will return all top-level HTTP operations and any other messages where HTTP exists in the stack.  
  
     You are encouraged to browse through the HTTP message hierarchy with the **Field Chooser** window to review the types of fields that you can specify in an HTTP filter. You can also make use of the Filtering IntelliSense feature that kicks in and exposes the message hierarchy when you type a dot (.) after “HTTP” in the Filter Expression text box of the **Edit Filter** dialog (or in the Filter Expression text box on any Filter panel). You can open the **Edit Filter** dialog by right-clicking the HTTP example and selecting the **Edit** item in the context menu that appears.  
  
## Sharing Filter Items  
 You can share  items from your centralized filter **Library** with other users, including any that you create, by exporting them as a **Filter** asset collection (\*.asset file) through the Message Analyzer Sharing Infrastructure. The features of the Sharing Infrastructure enable you to export and import **Filter** items to and from a designated user file share or other location, respectively, or to a user feed that you create from the **Settings** tab of the Message Analyzer **Asset Manager** dialog, which is accessible from the global Message Analyzer **Tools** menu. To learn how to manage view **Filters** from the **Manage Filters** dialog, see [Applying and Managing Filters](applying-and-managing-filters.md).  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about using **Aliases** in Filter Expressions, see [Performing Message Analyzer Operations with Aliases](performing-message-analyzer-operations-with-aliases.md).   
**To learn more** about using **Unions** in Filter Expressions, see [Performing Message Analyzer Operations with Unions](performing-message-analyzer-operations-with-unions.md).   
___________________\_  
  
## See Also  
 [Writing Filter Expressions](writing-filter-expressions.md)   
 [Filter IntelliSense Service](filter-intellisense-service.md)