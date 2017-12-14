---
title: "Comments Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 4539f029-65f6-4f26-816b-1f3c90e58039
caps.latest.revision: 21
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Comments Tool Window
Message Analyzer provides the **Comments** **Tool Window** to enable you to add a comment to any message that you select in any **Analysis Grid** viewer instance. This includes filtered views that display a subset of a full set of trace results.  
  
 You typically configure comments to contain important reminders or other information snippets that are significant to data analysis, so that you or others can quickly locate them when resuming data analysis. Therefore, when sharing a trace with commented messages, it will be easier for others to search for and focus on any issues you have flagged with comments. To configure a comment, you can access the **Comments** window as an item in the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu.  
  
## Configuring a Comment  
 You can add a single comment to any message that you select in the **Analysis Grid** viewer. You can also add multiple comments to a single message that is selected in the **Analysis Grid** viewer, which includes both top-level and child messages. However, if you add one or more comments to a *group* of selected messages, the comment/s will be attached to the last selected message only. After you display the **Comments** window, select a particular message in the **Analysis Grid** viewer that you want to comment. You can then configure the comment by using the following features of the **Comments** window in the indicated manner:  
  
-   **Add** — click the **Add** button on the toolbar of the **Comments** window to display the comments input configuration. To configure multiple comments, click the **Add** button successively as required.  
  
-   **Title** — enter a title for your comment in this text box.  
  
-   **Author** — your user name and the date-time for the comment entry are specified in this text box by default, but you can change it as required.  
  
-   **Comment** — specify the text of your comment in the text box below the **Author** text box.  
  
-   **Save Changes** — clicking the **Save Changes** icon enables you to save the specified comment configuration.  
  
-   **Cancel Edit** — clicking the **Cancel Edit** icon enables you to remove the currently specified comment configuration. If you click the **Cancel Edit** icon, it changes to the **Delete Comment** icon and the **Save Changes** icon changes to the **Edit Comment** icon.  
  
     At this point, you can either resume editing or delete the comment configuration altogether. If you click the **Delete Comment** icon, the **Delete Comment** dialog displays to confirm the deletion. If you click the **Edit Comment** icon, an empty comment configuration displays to enable you to create your comment configuration as required. However, if you happen to have an existing comment selected, clicking the **Edit Comment** button opens the comment configuration for editing.  
  
## Searching for Commented Messages  
 To search for messages that contain configured comments, click the **Previous** and **Next** directional search controls against a set of trace results to find them. You can also use the keyboard left or right arrow keys to select either the **Previous** or **Next** search control and then use the keyboard `ENTER` key successively to search a trace for comments. Note that for large traces, the searches might not be instantaneous. Also, when the search in a specified direction reaches the last message containing a comment, the search simply resumes in round-robin fashion, should you continue searching in the current direction.  
  
> [!NOTE]
>  If you added a comment to a child message and the origins tree containing the child message is not expanded in the **Analysis Grid** viewer while you are searching for commented messages, only the top-level message or operation containing the commented child message will be highlighted in the **Analysis Grid** viewer. Otherwise, if the child messages are in the expanded state in the **Analysis Grid** viewer, each child message in the stack will be highlighted in succession until the message is reached where the comment was originally configured.  
  
## Saving and Loading Trace Files Containing Comments  
 If you want to save comments that you have configured in a message collection, you can only do so by saving your messages in the Message Analyzer native .matp format. You can save a message collection that contains comments by using the **Save/Export Session** dialog; however, you must click the **Save As** button rather than the **Export** button to facilitate the save; otherwise, your comments will not be saved in a .cap file which is the result of saving with the **Export** command. When you reload a saved message collection containing comments, for example through **Open**, **Recent Files**, or a Data Retrieval Session, the **Comments** window automatically opens when Message Analyzer is finished loading the data. Thereafter, you can use the **Previous** and **Next** buttons in the **Comments** window to locate the associated commented messages in the **Analysis Grid** viewer. In this way, you or another user can navigate through all of your commented messages.