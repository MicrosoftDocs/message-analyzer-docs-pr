---
title: "Creating Unions | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d367301-897f-4276-bb60-993eb2f49d25
caps.latest.revision: 35
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Creating Unions
Message Analyzer enables you to create a **Union** that correlates two or more fields, properties, or annotations, as described in [Configuring and Managing Message Analyzer Unions](configuring-and-managing-message-analyzer-unions.md). Creating a **Union** can help streamline data analysis and can also simplify what might otherwise be cryptic field names that are difficult to work with. You can create a new **Union** by selecting the **New Union** item from the **Unions** drop-down list in the global Message Analyzer **Tools** menu or by clicking the **Unions** button on the global Message Analyzer toolbar. Making such a selection causes the **Edit Union** dialog to display, from where you can provide the input configuration data that is required to create a new **Union**.  
  
 __________________\_  
  
 **Go To Procedure**   
To go directly to a procedure that creates a **Union**, see [Create a Union of Two Data Fields](procedures-using-the-data-viewing-features.md#BKMK_CreateUnion). However, you are advised to review the information contained in this section before doing so.  
__________________\_  
  
## Configuring a Union  
 To configure a **Union** of two or more data fields, properties, or annotations, use the following controls in the **Edit Union** dialog:  
  
-   **Name** — in this text box, specify a **Union** name that is appropriate for your environment. However, note that you cannot prefix a **Union** name with a number; otherwise, you can follow your own naming conventions. Note that Message Analyzer permits you to specify a **Union** name that is similar to one of its child (constituent) field names. For example, a **Union** could be named “command”, even if one of its child field names is “SMB.command”. This is because the result of such a naming, *\<UnionName>*.command, is unique and would not collide with the child field name.  
  
    > [!NOTE]
    >  If the **Union** name that you specify already exists, Message Analyzer displays a message box with the following prompt:    
    > "**The name has been used, please use a different name**"  
  
-   **Type** — consists of a label that indicates the **Union** data type. It is likely that the fields, properties, or annotations that you combine into a **Union** will be of different data types. When this is the case, Message Analyzer performs a fundamental conversion to an appropriate type, as described in [Supporting Type Conversions for Union Fields](creating-unions.md#BKMK_UnionTypeConversions), to ensure that an appropriate data type is generated for your **Union**.  
  
    > [!NOTE]
    >  If you add or remove any field, property, or annotation in the **Edit Union** dialog, the **Type** label may update to reflect a new **Union** data type, depending on the field types you are adding to or removing from the **Union** configuration.  
  
-   **Category** — in this combo box, specify the name of the **Category** in which to place your new **Union**. You have the option to either create a new **Category**, which is retained as an editable drop-down list item for future selection, or you can choose an existing **Category** from the drop-down. Be sure to create or choose a **Category** that is meaningful for your environment. All new categories that you specify become subcategories that appear under the default **My Items** top-level category in the **Unions** drop-down list. However, if you leave the **Category** combo box blank, the **Union** will be stored directly under the **My Items** category.  
  
-   **Add** — click this button to display the **Field Chooser** **Tool Window**, from where you can select the fields, properties, or annotations that you want to combine as a **Union** and create a correlation of fields with equivalent meaning. After you locate each field in the **Field Chooser** window that you want to add to the **Union**, either double-click the name of the field, property, or annotation; or highlight it and click the **Select** button in the dialog to add it to the **Union** configuration. Each field entity that you specify in this manner is added to the **Select fields to include** list box. To create a **Union**, you must have at least two fields, properties, or annotations.  
  
     If you want to get the most out of this feature when you are combining fields, properties, or annotations into a **Union**, you should carefully consider the following suggestions:  
  
    -   The added entities essentially have the same functional meaning, otherwise the resulting **Union** is likely to be irrelevant.  
  
    -   The added entities are optionally of the same data type, to minimize memory consumption (see [Supporting Type Conversions for Union Fields](creating-unions.md#BKMK_UnionTypeConversions)).  
  
    -   The added entities come from *different* data sources rather than the *same* data source or module, as this is the intended use of a **Union**.  
  
        > [!IMPORTANT]
        >  If you want to create  a **Union** of two fields, one from a trace file and one from a log file, they will need to be file types that Message Analyzer supports and the log file will have to be parsed so that a module node for the log will appear in the **Field Chooser** window, from where you can select the fields of the log. To parse text logs, Message Analyzer requires an OPN configuration file. Several configuration files are provided with Message Analyzer by default to parse various types of text logs, such as SambaSysLogs, Netlogon logs, IIS logs, Cluster logs, and others.  
        >   
        >  To initiate the parsing process, you will need to specify a configuration file in the **Text Log Configuration** drop-down list in the **New Session** dialog for a Data Retrieval Session (**Files** tab) and then click the **Start** button in the dialog. Thereafter, the name of the log will appear as a node in **Field Chooser**, from where you can select any of the fields that Message Analyzer parsed for a particular log type whenever you are creating a **Union**.  
  
     Without considering data sources, you might specify arbitrary fields that hold unrelated data, in which case Message Analyzer will only use the first field that you configured in the **Union** — note that this can have unexpected results.  
  
-   **Return value as** options — consist of the following:  
  
    -   **Single value** — this option causes the **Union** to display a single value, even if the correlation results in multiple values for a particular field. When multiple values exist, Message Analyzer picks a value for the **Union** to display, based on the first field that you configured in the correlation.  
  
    -   **Set of multiple values** — this option causes the **Union** to display a set of values when the correlation results in more than one value for a field. For example, Message Analyzer might display a set of IP Addresses as “set (192.168.1.1, 192.168.1.2)” in the **Analysis Grid** column that displays the correlated **Union** values, assuming you add the named **Union** as a new column in the **Analysis Grid** viewer with the **Field Chooser** window.  
  
-   **Remove** — click this button to remove an existing field that you highlight in the **Select fields to include** list box. Note that you can remove fields only one at a time.  
  
-   **Save** — click this button to save the **Union** configuration. At this time, a new **Union** is created and added to the **Unions** drop-down list in the **Category** that you specified.  
  
     **Note** Your new **Union** will also be added to the root **Unions** node in the **Field Chooser** window after a Message Analyzer restart. Note that you will use the **Field Chooser** window to add your new **Union** as a column in the **Analysis Grid** viewer. In addition, the new **Union** becomes an asset that you can share with others through the Message Analyzer sharing infrastructure, as described in [Managing Unions as Shared Items](managing-unions-as-shared-items.md).  
  
<a name="BKMK_UnionTypeConversions"></a>   
## Supporting Type Conversions for Union Fields  
 When you combine two or more fields, properties, or annotations into a **Union**, it is often the case that such entities are of different data types. For instance, you might be combining `byte` and `int` data types in a **Union**, which have incompatible range values and require a type conversion for use in the **Union**. The following describes how Message Analyzer treats compatible and incompatible field types, with respect to type conversions:  
  
-   **No type conversion** — compatible field types do not require any type conversion, such as those fields that are of the *same* data type. This results in the **Union** taking on the same data type as the correlated fields. For example, a **Union** with two correlated fields of type `ushort`, will display **ushort** in the **Type** label of the **Edit Union** dialog.  
  
-   **Implicit type conversion** — Message Analyzer can accommodate for incompatible field types through the use of a transitive implicit type conversion, if an appropriate implicit conversion path exists for one or more of the correlated fields. Basically, a transitive conversion says that if type A can be converted to type B and type B can be converted to type C, then type A can be converted to type C as well. Message Analyzer performs such a transitive type conversion in order to detect the appropriate data type of minimum sufficient value range that can represent all the types in the **Union**. This minimalistic approach ensures that the **Union** consumes the least amount of memory possible. In the case of a **Union** with fields of type `byte` and `int`, the `int` is the minimum type that has a suitable value range to handle the range of values that can occur in fields of these types in the **Union**. Therefore, the **Union** takes `int` as its type, which then displays in the **Type** label in the **Edit Union** dialog.  
  
     ___________________\_  
  
     **More Information**   
    The [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx) contains a type conversion table in section 2.1.7 that enables you to map the conversion path taken by Message Analyzer in the previously mentioned type conversion. For example, the type `byte` can implicitly convert to type `short`, and a `short` can implicitly convert to an `int`, therefore, type `byte` can convert directly to type `int`.   
    ___________________\_  
  
-   **Base type conversion** — incompatible field types would remain incompatible if there were no implicit conversions to a common type available. Therefore, when this is the case, Message Analyzer converts all field types to a common base type called `any`. The `any` type is sufficient to handle the value range of any other data type. The **Union** would then display the `any` type in the **Type** label of the **Edit Union** dialog.  
  
## Performing Other Operations on Unions  
 After you successfully create one or more **Unions**, you can perform the following operation on any **Union** that exists in the **Manage Unions** dialog, as described in [Modifying Unions](modifying-unions.md):  
  
-   **Create a Copy** — this  is the only command available for  built-in **Unions**, given that built-in **Union** assets   cannot be edited.  
  
 You can perform the above operation in addition to the following on any **Union** that exists in the **My Items** category of the **Manage Unions** dialog. Note that these commands are not available for the built-in  **Unions**:  
  
-   **Edit**  
  
-   **Delete**