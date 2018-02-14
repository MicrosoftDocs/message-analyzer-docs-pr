---
title: "Filter IntelliSense Service | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8baed9ec-4e79-4e7a-8732-6859d1a88272
caps.latest.revision: 33
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Filter IntelliSense Service

<a name="BKMK_FilterIntellisense"></a> To assist you in developing Filter Expressions, Message Analyzer provides a statement completion service known as Filter IntelliSense. The Filter IntelliSense service is a level-sensitive and interactive feature that interprets the text that you enter in Message Analyzer Filter Expression text boxes and responds by displaying scrollable drop-down lists of message elements, such as protocols, message types, structures, fields, properties, annotations, and so on. This feature helps you to navigate through message hierarchy levels to find and select elements that you can configure in Filter Expressions. Similar to the **Field Chooser** **Tool Window**, the Filter IntelliSense service enables you to quickly learn about and work with the message hierarchies of the protocols that are parsed by the PEF Runtime. Because Filter IntelliSense provides visual message element cues in response to text that you enter, it enables you to discover and learn about the Filtering Language syntax on-the-fly as you use Message Analyzer to resolve issues on which you are working. The visual presentations provided by the service also help you to easily recognize the difference between ambiguous and fully qualified filter expressions, such as `HTTP.Method=="GET"` and `HTTP.Request.Method=="GET"`, respectively.  
  
<a name="BKMK_StartIntellisenseService"></a>   
## Starting the Filter IntelliSense Service  
 There are several ways that you can initiate the Filter IntelliSense service. First, you can type specific characters in a blank Filter Expression text box to start the service. For example, you might type the name of a protocol in the text box of any Filter panel on the Filtering toolbar during session results analysis. You can also start the service by initiating the Keyboard shortcut **Ctrl+Spacebar** while the cursor is located in any blank Filter Expression text box.  
  
 The following list describes the results of starting the Filter IntelliSense service with various actions that include character entry in a Filter Expression text box and the keyboard shortcut method:  
  
-   **Enter a valid OPN-qualified identifier character** — displays a list of elements in alphabetical order that match the input text character(s).  
  
-   **Enter the "#" character** — displays a list of global annotations in alphabetical order.  
  
-   **Enter the "\*" character** — displays a list of filter expressions that can use the wildcard character, in alphabetical order.  
  
-   **Press Ctrl+Spacebar** — displays a list of protocols and global annotations in separate groups, with each group in alphabetical order.  
  
> [!NOTE]
>  To place the cursor in any Filter Expression text box, simply click directly in the text box of choice. This includes the text box in any Filter panel on the Filtering toolbar during session analysis, or the **Session Filter** text box that exists in the **New Session** dialog during session configuration.  
  
## Using the Filter IntelliSense Service  

 When you invoke Filter IntelliSense in one of the indicated ways, each listed entity displays with an associated icon that represents its element type, for example, a protocol module, message, structure, operation, property, or field, similar to the way the **Field Chooser** window displays icons to the left of each element. If you select any listed element, the element type, its data type, and one or more fully qualified expressions are displayed in an informational pop-up window to the right of each element.  
  
 If you continue to type with Filter IntelliSense invoked, the element list is filtered to show only the results that match the input text. If you invoke Filter IntelliSense in a blank Filter Expression text box, the results are shown in separate sections for each element type with each section in alphabetical order. If you invoke Filter IntelliSense from below a parent element, it displays child entities and its descendants in separate groups with each group in alphabetical order. If a Filter Expression is abbreviated or ambiguous and can be represented by two or more expressions, a list of represented, fully-qualified expressions will display in an informational pop-up window.  
  
 For example, when you type one or more characters in any Filter Expression text box, Filter IntelliSense tracks the text entries that you enter and responds with a list of elements that match the typed characters, for example, matching protocol or field names. Filter IntelliSense also highlights an element in the list that matches the input character to enable you to conveniently add that selected element to your Filter Expression by pressing **Tab**, **Enter**, or the **Space bar** on your Keyboard. If the selected element is not appropriate for your Filter Expression, you can scroll down the list to find another one by using the down arrow key.  
  
 If you invoke Filter IntelliSense at root level by typing a protocol name followed by a dot (.), a list displays that can include message types, structures, properties, fields, and so on, depending on the protocol and its message hierarchy. From this level, you can also select a field or other message element from the list and integrate it into your Filter Expression by pressing one of the previously specified Keyboard keys. If you type the name of a field only, a pop-up list displays with all possible filter expressions that end with the name of the field you specified. As you continue to traverse the message hierarchy of a particular protocol by using the dotted notation, Filter IntelliSense continues to display the field names that are associated with the current hierarchic level. This process repeats until you reach the last available level in the protocol message hierarchy.  
  
## Service Implementation  

 To implement its functions, the Filter IntelliSense service makes use of a metadata access layer that is made available by underlying classes that provide the routines for fetching statement completion text. The service architecture that underlies these functions includes the following components:  
  
-   Statement Completion Service with a cache  
  
-   Statement Completion Store  
  
-   Query Name Reference Resolver  
  
The presentation of statement completion text in Message Analyzer Filter Expression text boxes occurs in response to the initiation actions specified in [Starting the Filter IntelliSense Service](filter-intellisense-service.md#BKMK_StartIntellisenseService). Note that the Filter IntelliSense service is available for view **Filter** configuration on the Filtering toolbar, even while Message Analyzer is still parsing messages.  
  
**Interactive Intelligence**   
The Filter IntelliSense service contains the interpretive intelligence to anticipate the elements for which you might be searching based on the characters you enter. For example, if you enter the text "Port" in a Filter Expression text box, the service matches the prefix and entities such as "PortName" display in the results list; however, element names such as "DestinationPort" do not display. In addition, the portion of the prefix text that matches the entered text is displayed in bold.  
  
If you invoke Filter IntelliSense at the root level in an empty Filter Expression text box, the results are grouped separately and listed in the following order, with each group alphabetically sorted:  
  
-   Protocol modules  
  
-   Global annotations  
  
If you invoke Filter IntelliSense at the root level in an empty Filter Expression text box and *then* enter text to activate the list filtering feature, the results are grouped separately and listed in the following order, with each group alphabetically sorted:  
  
-   Protocols  
  
-   Global annotations  
  
-   *Messages, \*Structures, \*Fields, \*Properties  
  
-   Messages, Structures, Fields, Properties  
  
If you invoke Filter IntelliSense below a parent element at root level, for example by entering the text "TCP." in a Filter Expression text box, the following child entities are listed together in a single group that is alphabetically sorted:  
  
-   Messages  
  
-   Structures  
  
-   Fields  
  
-   Properties  
  
If you continue to invoke Filter IntelliSense at the child level, lists of fields display that are associated with the various child entities. From the lists, you can select the message elements you require for integration into your Filter Expression.  
  
> [!NOTE]
>  The Filter IntelliSense service does not respond to colon (:) characters that you might normally enter to create explicit paths in Filter Expressions. It also does not respond to other characters such as operators and backslashes, the latter of which you can use to traverse a protocol stack.  
  
---  
  
 **More Information**   
 **To learn more** about explicit paths, see [Traversing the Message Hierarchy with Explicit Paths](using-the-filtering-language.md#BKMK_TraverseMessageHierarchyExpPaths).  
**To learn more** about special methods for traversing a protocol stack, see [Browsing Message Origins](using-the-filtering-language.md#BKMK_BrowseMessageOrigins).  
**To learn more** about annotations, see [Accessing Message Properties and Annotations](using-the-filtering-language.md#BKMK_AccessPropertiesAnnotations).   

---  
  
## See Also  

[Using the Filtering Language](using-the-filtering-language.md)