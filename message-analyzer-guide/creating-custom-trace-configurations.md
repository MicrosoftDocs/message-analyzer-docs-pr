---
title: "Creating Custom Trace Configurations | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 2ddbbc46-2d40-44d2-a741-ebda0721520d
caps.latest.revision: 24
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Creating Custom Trace Configurations
Message Analyzer enables you to create your own **Trace Scenario** templates by customizing the properties of an existing scenario and then saving your customized version as a **Trace Scenario** template with a specified name and category, without actually starting a trace and collecting data in a Live Trace Session. When you save **Trace Scenario** templates, they become part of the **Trace Scenarios** Library where they represent a master trace configuration that can include one or more providers, **Fast Filters**, a **Session Filter**, ETW **Keyword** bitmask or error **Level** filters, or advanced filters that you specify in the **Trace Scenario** configuration prior to saving the template. You can also choose the data viewer that your **Trace Scenario** will use by default whenever you decide to run the template configuration in a Live Trace Session.  
  
 Some of the advantages of creating your own preconfigured **Trace Scenarios** are that you can do the following:  
  
-   Create any number of **Trace Scenarios** that serve as trace templates for common usage contexts, where you focus on retrieving unique message data in each context.  
  
-   Have the convenience of quick access to a **Trace Scenario** template that specifies a trace configuration you typically run on a consistent basis.  
  
-   Share **Trace Scenario** templates that might be useful to your team members or the larger Message Analyzer community.  
  
-   Obtain useful **Trace Scenarios** from other team members or community sources.