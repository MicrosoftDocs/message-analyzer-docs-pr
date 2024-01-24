---
title: "Applying a Time Filter to Session Results | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.service: windows-server-threshold
ms.reviewer: ""
ms.suite: ""
ms.subservice: networking
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 613117c7-6fab-4704-8909-b4b9632577fc
caps.latest.revision: 39
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Applying a Time Filter to Session Results

Message Analyzer enables you to filter messages in data viewers that you have opened, such as the **Analysis Grid** and **Chart** viewers, based on a configured time window in which you elect to view messages. This feature is called a **Time Filter** and it is accessible from the **Add Filter** drop-down list on the Message Analyzer Filtering Toolbar that displays above the analysis surface where data viewers appear when selected. You can configure a **Time Filter** for Live Trace Session results similar to the way you configure a **Time Filter** for a Data Retrieval Session with some exceptions, as described in [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md), which includes employing controls that you  can use to define the **Start Time** and **End Time** of a time window in which to view messages. However, the   scope of these **Time Filters** is different, as are  some label and naming nomenclatures of the user interfaces involved.  
  
 The difference in scope of these **Time Filters** has to do with the context in which they are applied. For example, if you apply a **Time Filter** to data that you load into Message Analyzer through a Data Retrieval Session, only the messages that fall within the time window that you specify in the time-filter configuration are retrieved. All other messages are filtered out when the data is loaded, which therefore makes such filtered messages  unavailable in the chosen Message Analyzer data viewer. Thereafter, the filtered-out messages can be restored only by undoing the **Time Filter** configuration and reloading the data from the **Edit Session** dialog. On the other hand, although a **Time Filter** for a set of trace results applies the same type of time-slot filtering, it does so in the context of an already parsed message collection. This means that the original raw trace data is preserved in the Message Store even if the message display is altered by the way you manipulate the data. As a result, a **Time Filter** for trace results provides the convenience of enabling you to toggle back and forth between the original trace results and the time-filtered trace results, which can be a benefit to your analytical processes.  
  
<a name="BKMK_PerfVsUsability"></a>   
## Considering Performance vs. Usability Factors for Time Filter Application  
 You can apply a **Time Filter** against a set of trace results after it is loaded into Message Analyzer or you can apply an *input* **Time Filter** at the moment when you actually import the same data into Message Analyzer.  To decide which is best in your circumstances, you might want to consider the tradeoffs between performance and usability, especially when loading data from very large files.  
  
 **Applying a Time Filter When Retrieving Data**   
When you apply a **Time Filter** to a Data Retrieval Session, the amount of data being loaded is reduced to a specified time window, which results in less impact on CPU and memory resources, and therefore demonstrates better performance. However, the resulting data set has all messages removed that are outside the specified time window, which could have an impact on usability and data analysis in terms of message context and other relationships. Moreover, an input **Time Filter** might obscure conversation contexts in the filtered message collection that you import, whereas a **Time Filter** applied to a set of trace *results* does not. To avoid the loss of data in the case of the former, you would need to edit the Data Retrieval Session by setting a new **Time Filter** window in the **New Session** dialog and then reload the data. In the case of the latter, Message Analyzer enables you to remove or resize and reapply the **Time Filter** to the current set of trace results as necessary, making it more convenient to work with the data, given that a data reload is unnecessary.  
  
 Also note that for some input file types, Message Analyzer may not be able to determine the start and end times, in which case the **Time Filter** controls in the **New Session** dialog for a Data Retrieval Session will be disabled. However, you can always utilize the **Time Filter** feature after the data displays in your Analysis Session, as needed, regardless of the input file type.  
  
---  
  
 **More Information**   
 **To learn more** about applying a **Time Filter** when loading data from logs and trace files into Message Analyzer, including the file types for which Message Analyzer can determine start and end times, see [Applying an Input Time Filter to a Data Retrieval Session](applying-an-input-time-filter-to-a-data-retrieval-session.md).  

---  
  
 **Applying a Time Filter to Live Trace Session Results**   
On the other hand, if you wait to apply a **Time Filter** to a set of messages that are already displayed in a data viewer such as the **Analysis Grid**, an applied **Time Filter** must check the time stamps on each message in the entire collection against the filtering criteria, which can impact performance if there is a very high message volume. However, usability is improved since you can easily restore the entire message set, including conversation contexts, with a single click of the **Apply** button in the **Time Filter** panel on the Filtering toolbar after altering the time window as needed, for ease of analysis.  
  
## Configuring a Time Filter for a Set of Trace Results  

 When you are ready to configure a **Time Filter** for a set of trace results, select the **Add Time Filter** command that displays when you click the **Add Filter** drop-down list on the Message Analyzer Filtering Toolbar that appears just above the analysis surface where all data viewers display. This action displays the **Time Filter** panel that contains **Start Time** and **End Time** text boxes that by default  display the original time window boundaries of the displayed message collection, along with a set of time slider controls that enable you to adjust the window of time in which you want to view data.  
  
 As you change the time window with the slider controls, the time values in the **Start Time** and **End Time** text boxes display also change.   When you finish adjusting the time slider controls, the corresponding new start and end time values define the selected time window in which you are choosing to view data.  
  
> [!TIP]
>  You have the option to apply a **Data Source** filter to a set of trace results to isolate the messages from specified Data Source providers that were used during data capture, as described in [Filtering Data Sources](filtering-data-sources.md). By combining a **Data Source** filter with a **Time Filter**, you can obtain a very narrowly focused set of results that drills down to a specific window of time in which data was captured by a specific Data Source.  
  
 As you set the slider controls, Message Analyzer creates a Filter Expression in the background that will facilitate the time-filtering action. Note that you can manually specify time stamps in the **Start Time** and **End Time** text boxes; however, any time stamp that is outside the message collection time boundaries will create an erroneous **Time Filter**.  
  
## Applying a Time Filter  

 After you set the time window configuration for a **Time Filter** as previously described, you can apply the filter by clicking the **Apply** button on the **Time Filter** panel. Message Analyzer responds by displaying only the messages that fall within the time window you specified. If you want to return to the unfiltered display of original message data, click the **Remove** button on the **Time Filter** panel. This action removes the effects of the previously applied **Time Filter**, but does not alter the time window configuration that you specified. If you want to reapply the **Time Filter**, you can do so by clicking the **Apply** button again on the **Time Filter** panel. You can toggle back and forth between the filtered and unfiltered view configurations as many times as you want, as the time window values that you set for a particular session viewer will persist until you change them.  
  
> [!NOTE]
>  As you alternately apply and remove a **Time Filter** configuration, you can observe the activation of session progress indicators in the **Session Explorer** **Tool Window**.  
  
## See Also  

[Using the Filtering Toolbar](using-the-filtering-toolbar.md)