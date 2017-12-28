---
title: "Understanding the Filtering Language Basics | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a96cfd35-0427-4b23-a4c2-a3e32c22b40f
caps.latest.revision: 60
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Understanding the Filtering Language Basics

To assist you in understanding the Filtering Language, you should experiment with some of the built-in Filter Expressions that Message Analyzer provides in the centralized filter **Library**. You should also review the descriptions of these filters in the [Filtering Live Trace Session Results](filtering-live-trace-session-results.md) topic of this documentation and then apply them to a trace, to get a sense of how real-world filter expressions work when analyzing trace results.  
  
 This section provides concepts and constructs that you will need to understand to create your own Filter Expressions. In this section, you will learn how to use the basics of the Filtering Language to construct Filter Expressions. This includes the use of operators and literals, traversing the protocol message hierarchy, and other considerations such as case sensitivity, filter applicability, semantic equivalence, and the meaning of negation.  
  
## Using Operators  

 When creating custom Filter Expressions, you can use the basic Boolean operators that follow. You can also use the textual equivalent of these operators, for example, AND, OR, and NOT in your filter expressions:  
  
-   **&&** — represents the logical AND function. Typically used when combining filter expressions.  
  
-   **&#124;&#124;** — represents the logical OR function. Typically used when combining filter expressions.  
  
-   **!** — represents the logical NOT function. Typically used for negation.  
  
 You can also apply the following relational operators to applicable Filter Expressions when you need to restrict fields to specific values:  
  
-   **==** — Equals. An operator that evaluates two filter expression operands for value equality.  
  
-   **!=** — Not equals. An operator that evaluates two filter expression operands for value inequality. Note that this operator also evaluates nonexistence as a form of negation.  
  
-   **~=** — Not equals. This operator negates the condition on a value only but does not evaluate nonexistence as a form of negation.  
  
> [!NOTE]
>  The following examples further clarify the difference between the “!=” and “~=” operators. A filter expression such as `TCP.SourcePort != 443` returns all TCP messages that have a **SourcePort** value that is not equal to 443, together with all messages that are not TCP. By using the ~= operator in this expression, for example `TCP.SourcePort ~= 443`, the condition on the value is negated and the filter expression will return TCP messages with a **SourcePort** that is not equal to 443, but non-TCP messages will not also be included.  
  
-   **>** — Greater than. This operator is used to evaluate whether one filter expression operand is greater than the other.  
  
-   **>=** — Greater than or equal to. This operator is used to evaluate whether one filter expression operand is greater than or equal to the other.  
  
-   **<** — Less than. This operator is used to evaluate whether one filter expression operand is less than the other.  
  
-   **<=** — Less than or equal to. This operator is used to evaluate whether one filter expression operand is less than or equal to the other.  
  
-   **in** — Membership in an array, set, or map. This operator is used in a filter expression to determine whether a particular left-side field or literal value exists in a user-specified right-side collection of values, such as an array. For example: `IPv4.Address in [192.0.1.1, 192.0.0.0, 192.0.0.2]` or `TCP.SourcePort in [6608, 6609, 6610]`.  
  
---  
  
 **More Information**   
 **To learn more** about how to apply relational operators, see the built-in Filter Expressions described in [Filtering Live Trace Session Results](filtering-live-trace-session-results.md).   

---  
  
 The Filtering Language also supports the following bitwise and arithmetic operators that you can apply to field expressions:  
  
-   **Boolean and bitwise operators**:  &#124;, ^, &, ~, and !.  
  
-   **Bit shift operators**:  <\< and >>.  
  
-   **Arithmetic operators**:  +, -, *, /, and %.  
  
 For example, the following is a valid filter expression that uses arithmetic operators: `TCP.SourcePort + 1 == TCP.DestinationPort / 2`.  
  
## Using Literals  

 The Filtering Language supports all literals for built-in Open Protocol Notation (OPN) types, such as integer, floating point, Boolean, char, string, and so on. The language also supports protocol-specific literals, as indicated in the examples of the table that follows:  
  
### Table 17.   Using Literals in Filter Expressions  
  
|Literal type|Example|  
|------------------|-------------|  
|IPv4|“127.0.0.1”|  
|IPv4 subnet|“10.10.249.1/21”|  
|IPv6|“2001:0db8:85a3:0000:0000:8a2e:0370:7334”, “2001::A001”|  
|IPv6 subnet|“2001: b8::/32”|  
|MAC|“48-2C-6A-1E-59-3D”|  
|Binary|“$[FFFE]”|  
|GUID|“{448ea956-38ff-4620-b022-dd88cac6c896}”|  
|Arrays|“[80, 339, 993]”|  
  
> [!NOTE]
>  When a field is declared as optional in OPN, the special value “nothing” is used to represent when the field is not present in an incoming message. You can include this special value in a filtering expression to represent such a case. For additional details about optional declarations and the use of the “nothing” value, see the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx) on the Microsoft downloads site.  
  
<a name="BKMK_traverseMessageHierarchy"></a>   
## Traversing the Message Hierarchy  
 The Filtering Language enables you filter messages based on different entities, such as protocol names, message types, structures, properties, or other field names. You can also filter for annotations, which generally fall into the “field name” category. As indicated earlier in this topic, you can also restrict the messages returned by an applied filter to specific values contained in their fields, and you can combine atomic filters with standard Boolean and relational operators.  
  
 If you want to create a filter that passes messages from a specific protocol that contains a particular field name or value, you can use the dot (.) notation to traverse the message type hierarchy by specifying a top-level protocol name, followed by the message type, and ending with a field. Whenever you need to traverse the message type and field hierarchy of a particular protocol using dotted notation, you can use the following fully-qualified expression pattern:  
`ProtocolName.MessageType.Field1.Field2. ...Fieldn`  
  
 For example, in the following figure you see the hierarchy for TCP, which you can view in an Analysis Session when you display the **Field Chooser** **Tool Window**:  
  
 ![Field Chooser Tool Window message hierarchy](media/fig67-field-chooser-tool-window-message-hierarchy.png "Fig67-Field Chooser Tool Window message hierarchy")  
  
 **Figure 67: Field Chooser Tool Window – TCP message hierarchy display**  
  
 With the TCP message hiearchy as a reference, you could inspect the hierarchy to view the available fields so that you can write filters similar to the following:  
  
-   **`TCP.Segment.SourcePort==443`**  — filters out all TCP messages except those that traverse port 443 (HTTPS).  
  
-   **`TCP.Segment.Flags.Syn`**  — enables you to look at the state of the **SYN** bit for all TCP messages in your trace results.  
  
    > [!NOTE]
    >  To examine these values, you can add a **SYN** column to your **Analysis Grid** viewer column configuration with the **Field Chooser**.  
  
-   **`TCP.Segment.Flags.Syn==True`**  — filters out all TCP messages except those that have their **SYN** flag bit set to True (indicating that a TCP message is part of a TCP three-way handshake for connection setup).  
  
> [!NOTE]
>  When you enter text in a Filter Expression text box to configure a Filter Expression, the Filter IntelliSense Service is activated. This service enables you to navigate message hierarchies on-the-fly, to locate specific message elements that you can integrate into your Filter Expression, as described in [Filter IntelliSense Service](filter-intellisense-service.md).  
  
> [!TIP]
>  Based on the highlighted field in the TCP message hierarchy shown in the previous figure, you can add the **DestinationPort** field as a new column to the **Analysis Grid** viewer (**Add as Column** command in the context menu), and as a new **Group** to the **Grouping** viewer (**Add as Grouping** command). To do this, the respective viewer will need to be in focus. You can also display the **DestinationPort** definition from the TCP.opn file in a separate viewing tab by choosing the **Go To Definition** command in the right-click **Analysis Grid** viewer context menu.  
  
<a name="BKMK_OtherFilteringConsiderations"></a>   
## Other Filtering Considerations  
 When creating custom Filter Expressions, you should also consider the following:  
  
-   **Case sensitivity** — in general, filters are case-insensitive, unless case-sensitivity options are accepted for a particular expression type. For example, “UDP” and “udp” are functionally equivalent.  
  
-   **Filter applicability** — in the **Analysis Grid** viewer, messages are grouped as expandable, top-level parent nodes containing expandable, lower-level child-node messages that comprise the origin tree, as described in [Viewing Message Data](viewing-message-data.md). These expansion nodes are each labeled by a **Message Number**. The child messages usually consist of the message protocol stack, the base ETW module, and can also include reassemblies such as you have with TCP virtual messages. When you apply a Filter Expression to a message collection, all messages that match the filtering criteria are returned, including all top-level messages that contain one or more origins tree messages where a match is found, regardless of whether the top-level messages specifically met the filtering criteria.  
  
     For example, if you apply a filter expression such as “Ethernet”, the filter will return all Ethernet messages in addition to upper-layer protocol messages such as IP, TCP or UDP, and so on, because these messages form part of the origins tree.  
  
-   **Semantic equivalence** — the semantics of the “!=” operator is equivalent to negating a filter that contains the operator “==”. For example, for any expressions of A and B, the filter “!(A == B)” is entirely equivalent to “A != B”. Therefore if you use the operator “!=”, its implied negation produces the previously described complement set of messages. This means that a filter such as `!(TCP.SourcePort == 443)` is semantically equivalent to the filter `TCP.SourcePort != 443`.  
  
-   **Negation** — if you apply a hypothetical filter named “TCPFilter” to a message collection, the filter “!TCPFilter” would return the complement set of messages that “TCPFilter” returned from the collection. For a more specific example, if you apply a filter expression such as `TCP.SourcePort == 443`, it will return all TCP message traffic that traversed TCP port 443. If you negate and apply this expression as `!(TCP.SourcePort == 443)`, it will specifically filter out all TCP messages that have a **SourcePort** field with a value of 443. In addition, other messages that meet the negated filter criteria will be passed by this filter, including other protocol messages in the collection that do not have a TCP **SourcePort** field defined, which in this case would mean all messages that are not TCP. This is the case because negation is inclusive of nonexistence.  
  
-   **Precedence** — most operators that you use in a Filter Expression are designated with a predefined evaluation order of precedence. Generally, the use of parentheses in a Filter Expression helps to define how the expression is evaluated. However, without the use of parentheses, some ambiguity can be introduced in the interpretation of your Filter Expressions. Therefore, when you use the ! (NOT) and == (EQUALITY) operators in a Filter Expression, the compiler gives precedence to the == operator when evaluating the expression. For example, this would make the expression `!F==true` semantically equivalent to `!(F==true)`.  
  
---  
  
 **More Information**   
 **To learn more** about OPN concepts that may help you write Filter Expressions, see the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx) document.   
 
---