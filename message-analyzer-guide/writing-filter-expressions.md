---
title: "Writing Filter Expressions | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bb94f94-3e4f-44b9-985a-2adc54e2bafd
caps.latest.revision: 30
author: "GregGill"
ms.author: "greggill"
manager: "ronstarr"
---
# Writing Filter Expressions
This section provides you with practical knowledge that you can utilize to create your own Filter Expressions with the Message Analyzer Filtering Language. This language is a derivative of the full OPN language that developers use to write OPN protocol descriptions that Message Analyzer utilizes to parse the messages of such protocols. As a result, there are various elements, constructs, and syntax that both languages share. Any Filter Expressions that you create can be saved in the centralized filter **Library**. Thereafter, you can use them as a **Session Filter** when configuring a new session, or as a view **Filter** when analyzing trace results in an Analysis Session.  
  
 To aid your understanding of the Filtering Language, you are advised to work with some of the built-in Filter Expressions in the centralized filter **Library** in parallel with the studies that you do here. The goal is to accelerate the learning process through observation and assessment of working example results. You can even work with any existing Filter Expression by creating a copy, modifying the copy, and saving it as a new Filter Expression in your central user **Library** without affecting the original filter configuration. This enables you to start with a known working filter configuration and perform some experimental modifications to see the effects of your changes when applied to a set of trace results.  
  
 Although you can specify a Filter Expression as a **Session Filter** when configuring a Data Retrieval Session or a Live Trace Session, the topics in this section focus on applying view **Filters** in an Analysis Session with the default **Analysis Grid** viewer, because this environment provides the most robust environment for demonstrating filtering functionality.  
  
 ______________________\_  
  
 **What You Will Learn**   
In this section, you will learn about the Filtering Language and how to create some simple Filter Expressions, in addition to others that are more complex. The material begins with an introductory overview to help you get started with custom Filter Expressions and includes a few simple examples followed by a description of the Filter IntelliSense Service. The discussions then move into understanding the basics about the Filtering Language, which includes the use of logical operators, arithmetic operators, and literals; how to traverse message hierarchies; and applying other filtering considerations. A walkthrough of filter features, special functions, and other capabilities concludes this section. In addition, examples are provided that combine different language features, including various applications of Filter Expression syntax, semantics, statements, truncation, traversers, aliases, and so on. This content is covered in the  topics below:  
[Introduction to Creating and Applying Filters](../messageanalyzer_content/introduction-to-creating-and-applying-filters.md)  
[Understanding the Filtering Language Basics](../messageanalyzer_content/understanding-the-filtering-language-basics.md)  
[Using the Filtering Language](../messageanalyzer_content/using-the-filtering-language.md)  
______________________\_  
  
## See Also  
 [Procedures: Using the Data Filtering Features](../messageanalyzer_content/procedures-using-the-data-filtering-features.md)