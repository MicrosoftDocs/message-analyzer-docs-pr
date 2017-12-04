---
title: "Using the Filtering Language | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8966f7ac-f762-4141-9516-3f74f5c0c5a5
caps.latest.revision: 49
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Using the Filtering Language
The topics of this section as listed below describe how to use various features of the Filtering Language.  
  
 ___________________________________\_  
  
 [Using Truncated Filter Expressions](../messageanalyzer_content/using-the-filtering-language.md#BKMK_UsingTruncatedFilters)   
 [Traversing the Message Hierarchy with Explicit Paths](../messageanalyzer_content/using-the-filtering-language.md#BKMK_TraverseMessageHierarchyExpPaths)   
 [Accessing Message Properties and Annotations](../messageanalyzer_content/using-the-filtering-language.md#BKMK_AccessPropertiesAnnotations)   
 [Referencing Enumerations](../messageanalyzer_content/using-the-filtering-language.md#BKMK_ReferenceEnums)   
 [Using Special Filtering Functions](../messageanalyzer_content/using-the-filtering-language.md#BKMK_UseSpecialFilterFunctions)   
 [Browsing Message Origins](../messageanalyzer_content/using-the-filtering-language.md#BKMK_BrowseMessageOrigins)   
 [Using Aliases](../messageanalyzer_content/using-the-filtering-language.md#BKMK_usingAliases)   
___________________________________\_  
  
 For each of these discussion areas, working filter examples are provided so that you can copy and paste them into a Filter Expression text box and test them. However, please observe the following advisory note.  
  
> [!CAUTION]
>  When copying and pasting filter expressions into a Filter Expression text box, please be aware that quotation marks may not work as expected due to environment formatting issues. If this occurs, simply retype the quotes in the Filter Expression text box and then apply the filter. Also note that other formatting issues may occur when copying content from HTML.  
  
<a name="BKMK_UsingTruncatedFilters"></a>   
## Using Truncated Filter Expressions  
 When writing a Filter Expression, you are not always required to provide the fully qualified expression to a field, since the dot notation is interpreted by the OPN Compiler to mean “look for a matching entity at any hierarchy depth”. For example, the filter expression `TCP.Segment.Flags.Syn==True` can also be written `TCP.Syn==True` to return an identical result. In practice this means that if there is more than one possible match with such a filter, it will return all matches, which can introduce a measure of ambiguity. In addition, the Filtering Language allows you to use a placeholder asterisk to shorten the expression to `*Syn==True`. This filter expression would then look for *any* protocol that has a SYN field set to True, which for example could expectedly include a TCP message, but also could include a message such as a Session Multiplex Protocol (SMP) connection request, which also uses a SYN flag when making a session connection.  
  
> [!NOTE]
>  If you do not specify a leading asterisk in your Filter Expression, a protocol name is required.  
  
 The following table depicts some of these variations in Filter Expressions, using the HTTP protocol as an example.  
  
### Table 18.   Truncating Filter Expressions  
  
|Expression|Meaning|  
|----------------|-------------|  
|`HTTP.Method==“GET”`|This filter returns only HTTP messages that have the value of their Method field set to “GET”. In this filter, note that the HTTP “Request” message type is not specified.|  
|`*Method==“GET”`|This filter has a result that is identical to `HTTP.Method==”GET”`, although both the protocol name and message type are omitted from the expression. Although this filter expression looks for messages from *any* protocol with a Method field set to “GET”, it is highly unlikely that such a message would be found, thus only HTTP messages will be returned.|  
|`*Port==443`|This filter looks at any protocol that has Port field defined. TCP defines SourcePort and DestinationPort fields, so this filter will capture HTTPS over TCP traffic because “Port” is an alias that represents both these fields, as described in [Using Aliases](../messageanalyzer_content/using-the-filtering-language.md#BKMK_usingAliases). However, messages from any other protocol that have a Port field defined might also be returned if their Port values are set to 443. **Note:**  When viewing the results of a filter such as this, consider that if the origin tree includes messages with a Port value equal to 443, you may also see other messages with Port values that are not set to 443, as indicated in the **Filter applicability** bullet item in [Other Filtering Considerations](../messageanalyzer_content/understanding-the-filtering-language-basics.md#BKMK_OtherFilteringConsiderations).|  
  
<a name="BKMK_TraverseMessageHierarchyExpPaths"></a>   
## Traversing the Message Hierarchy with Explicit Paths  
 When you apply a Filter Expression that uses an asterisk, as in the example `*Port==443`, you might notice that additional processing time is incurred to return filter results and that there may be a level of ambiguity inherent to those results. To improve the efficiency of such a filter and to disambiguate the results, you can specify an explicit traverse path for the filter by substituting the colon (:) separator for the dot (.) notation. When you use a colon separator to traverse the message hierarchy, the OPN Compiler interprets the separator to mean “look for a matching entity exactly one level below”. The following table provides some examples of what several filter expressions might look like with the colon (:) separator.  
  
### Table 19. Using Explicit Traversal Paths in Filter Expressions  
  
|Expression|Meaning|  
|----------------|-------------|  
|`HTTP:Request:Method == “GET”`|This filter returns only HTTP Request messages that have their Method field set to “GET”. By using colon separators in this filter expression, any other entity in the HTTP message hierarchy that is named “Request” will be ignored.|  
|`HTTP::Method == “GET”`|This filter also returns only HTTP Request messages that have their Method field set to “GET”. The missing value between the double colons is the “Request” message type specifier. The use of two separators signifies to the compiler that it should look for a matching entity two levels below.|  
  
<a name="BKMK_AccessPropertiesAnnotations"></a>   
## Accessing Message Properties and Annotations  
 Other data that you might want to return with a Filter Expression includes message properties and annotations. You can access message properties the same way that you access message fields, by using the dot notation to traverse the message hierarchy. However, the Filtering Language allows you to access message annotations, by using the “#” operator. In the Filtering Language, an annotation is additional information that is not directly related to a message, such as user-provided comments, implementation data, or other information related to the network stack. In these cases, you must use the “#” operator to retrieve this information. The table that follows provides examples of filters that access message properties and annotations.  
  
### Table 20.   Accessing Message Properties and Annotations in Filter Expressions  
  
|Expression|Meaning|  
|----------------|-------------|  
|`HTTP.Host == “www.bing.com”`|This filter returns all HTTP messages that have a **Host** property defined with a value equal to “www.bing.com”.|  
|`Etw::ProcessId==4`|This filter, based on the **ProcessId** **Global Property** (see the **Field Chooser** **Tool Window**), returns each message in the **Analysis Grid** viewer that has a  **ProcessId** that is equal to 4.|  
|`#MessageNumber == 5`|This  filter, based on the **MessageNumber** **Global Annotation** (see the **Field Chooser** **Tool Window**), returns the message in the **Analysis Grid** viewer that has a **MessageNumber** equal to 5. Note that all messages have a **MessageNumber** annotation that is defined in OPN.|  
  
<a name="BKMK_ReferenceEnums"></a>   
## Referencing Enumerations  
 You can refer to enumeration values by using the friendly enumeration name or by using actual field values. The table that follows depicts two different ways to refer to an enumeration.  
  
### Table 21.   Using Enumerations in Filter Expressions  
  
|Expression|Meaning|  
|----------------|-------------|  
|`Ipv4.Protocol == IANA.ProtocolType.UDP`|This filter returns all messages with a Protocol field that is set to UDP and uses the friendly enumeration name to retrieve that value.|  
|`Ipv4.Protocol == 17`|This filter is a variant of the previous one, in that “17” is the enumeration integer value for UDP. You should therefore expect this filter expression to return all messages that have a Protocol field that is set to UDP.|  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about Filter Expressions that use enumerations, including additional examples, see the [Diagnosis Category](../messageanalyzer_content/filtering-live-trace-session-results.md#BKMK_DiagnosisEnums) topic in [Filtering Live Trace Session Results](../messageanalyzer_content/filtering-live-trace-session-results.md).  
___________________\_  
  
<a name="BKMK_UseSpecialFilterFunctions"></a>   
## Using Special Filtering Functions  
 The Filtering Language also provides a set of special functions that enable you to search for a string or hexadecimal value within a message, without having to specify an associated field name to retrieve those values. These functions are described in the following table.  
  
### Table 22. Searching for Raw Data  
  
|Expression|Meaning|  
|----------------|-------------|  
|`contains “some string”`|This filter returns all messages that contain “some string”. The evaluation is case-insensitive and compares all supported string encodings; however, the default encoding is ASCII.|  
|`contains “some string” caseSensitive`|This filter is similar to the first filter in this table, but here case sensitivity is applied to the string evaluation.|  
|`contains “some string” encoding ASCII`|This filter is similar to the first filter only the string evaluation is restricted to a specified encoding, which includes any one of the following:<br /><br /> -   ASCII<br />-   UTF7<br />-   UTF8<br />-   Unicode<br />-   UTF32<br />-   BigEndianUnicode<br />-   Base64 **Note:**  If you do not specify an encoding, all encodings are included in filter scope.|  
|`contains $[AA34]`|This filter returns all messages that contain the specified binary value in hexadecimal format.|  
  
<a name="BKMK_BrowseMessageOrigins"></a>   
## Browsing Message Origins  
 You can use symbols that resemble XPath notation to traverse the protocol stack of any protocol message origin tree in the following ways:  
  
-   **Directory tree traversing** — you can use the backslash symbol ("\\") to traverse the protocol stack similar to the way you navigate a directory tree.  
  
-   **Origins tree traversing** — you can use the double backslash symbol ("\\\\") to look down the stack one or more levels.  
  
 The table that follows provides some examples of using these symbols in filter expressions to traverse the protocol stack.  
  
### Table 23. Traversing the Protocol Stack  
  
|Expression|Meaning|  
|----------------|-------------|  
|`\TCP\IPv4`|This filter returns top-level messages that are TCP where an IPv4 message is one level below TCP in the origins tree. Top-level is indicated by the leading “\” character.|  
|`\HTTP\\IPv4`|This filter returns top-level messages that are HTTP where an IPv4 message exists one or more levels below HTTP in the origins tree.|  
|`\HTTP\TCP\\Ethernet`|This filter returns top-level HTTP messages where a TCP message is directly below HTTP and somewhere below that is an Ethernet message in the origins tree.|  
|`TCP\IPv4`|This filter returns all TCP messages from any level in the origins tree where an IPv4 message is one level below TCP. **Note:**  In this filter expression, note that the leading “\” character is missing. This means that an explicit level in the origins tree is not specified. As a result, a double backslash ("\\\\") is implied when the leading slash (“\”) is not written in the expression, which therefore makes "TCP" semantically equivalent to "\\\TCP".|  
  
 You can also combine traversing notation with various field values and operators, as indicated in the table that follows.  
  
### Table 24. Combining Traversing with Field Values and Operators  
  
|Expression|Meaning|  
|----------------|-------------|  
|`\HTTP\TCP.Port == 80\IPv6 &#124;&#124; UDP`|This filter returns all top-level HTTP messages with a TCP transport where the Port (SourcePort or DestinationPort) is equal to 80, and with either an (IPv6 message directly below) OR (UDP message at any level below) in the origins tree.|  
|`\TCP.Port == 80\IPv4.Address == $[C0A80101]`|This filter returns all top-level TCP messages that have a Port value equal to 80, with IPv4 messages below that have an Address value equal to 192.168.1.1.|  
  
<a name="BKMK_usingAliases"></a>   
## Using Aliases  
 In OPN, protocol fields can be grouped under a common name or alias by using an OPN aspect. The protocols that are included with Message Analyzer use this aspect to declare groups or “aliases” for commonly used fields. For example, the “Address” alias for IPv4 messages is defined to include SourceAddress and DestinationAddress fields, which makes it possible to apply a filter such as `*Address == 10.0.1.13`. This particular filter expression returns all messages that have either SourceAddress or DestinationAddress set to this IP address value, as it is semantically equivalent to the expression `*SourceAddress == 10.0.1.13 || *DestinationAddress == 10.0.1.13`. When fields are grouped under a common name such as “Address”, it implies the disjunction of each of the components in the group. Another example of a common alias is “Port”, which represents the SourcePort and DestinationPort fields. This is why applying a filter expression such as `*Port==443` will return messages from any protocol that defines a SourcePort or DestinationPort field that has a value of 443.  
  
> [!IMPORTANT]
>  As related to OPN aspects, aliases are not actual message fields and therefore you cannot display an *alias* column in the **Analysis Grid** viewer column layout.  
  
 However, this should not be confused with the Message Analyzer **Aliases** feature that enables you to create and substitute a friendly name for a field value with a cryptic name that is difficult to keep track of. For more information about this feature, see [Using and Managing Message Analyzer Aliases](../messageanalyzer_content/using-and-managing-message-analyzer-aliases.md).  
  
> [!NOTE]
>  OPN aspects perform a similar function as attributes do in the C# programming language. For example, attributes consists of metadata that can extend the language or declarative information that a program can use at runtime.  
  
 A compilation of all grouping aliases for protocols that are provided with Message Analyzer will be available in the near future.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about OPN aspects, see the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx) document.  
___________________\_