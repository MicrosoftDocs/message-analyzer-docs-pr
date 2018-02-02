---
title: "Bookmarks Tool Window | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ea20d47-882f-4f1e-a25b-a94b4721f8d5
caps.latest.revision: 34
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Bookmarks Tool Window

Message Analyzer provides a **Bookmarks** **Tool Window** that enables you to configure the following types of bookmarks:  
  
-   **Message Bookmarks** — enables you to specify a bookmark for any single message or group of messages that you select in the **Analysis Grid** viewer. You typically set such bookmarks in a trace for quick location of messages that have some related importance or critical context for the data analysis process. Bookmarks make it convenient to locate these messages at any time, since you can save them with your message data in the *.matp format. It also makes it convenient to share the trace with others along with the bookmarks that you configured to highlight the important focus areas.  
  
-   **Pattern Bookmarks** — enables you to specify bookmarks for one or more matched instance messages in the **Pattern Match** viewer, after executing a Pattern expression against a set of trace results. You can set these types of bookmarks to quickly locate messages for specific matched instances of a Pattern expression, as described in [Viewing Matched Instance Message Data](using-the-pattern-match-viewer.md#BKMK_ViewMatchedInstanceData), although the method to do so is different than you would do in the **Analysis Grid** viewer, as described in [Viewing Bookmarked Data](bookmarks-tool-window.md#BKMK_ViewingBookmarks).  
  
## Displaying the Bookmarks Tool Window  

 If the **Bookmarks** window is not displaying in an Analysis Session, you can open it by clicking the **Bookmarks** item in the **Windows** submenu that is accessible from the global Message Analyzer **Tools** menu. You can also undock and reposition the **Bookmarks** window in a more convenient location by taking advantage of the docking navigation control that displays after you drag the **Bookmarks** window by its tab away from the default docking location.  
  
<a name="BKMK_configuringBKMKs"></a>   
## Configuring Bookmarks  
 After you display the **Bookmarks** window, you can configure bookmarks for messages in the **Analysis Grid** viewer and for matched instances in the **Pattern Match** viewer. To begin, select a message or matched instance as appropriate for the entity that you want to bookmark, and then select the corresponding command in the **Add** drop-down menu on the toolbar of the **Bookmarks** window:  
  
-   **Message Bookmark** — creates a bookmark for one or more messages that you select in the **Analysis Grid** viewer. The **Bookmarks** configuration grid is populated with a row of data that represents the selected message/s.  
  
-   **Pattern Bookmark** — creates a bookmark for one or more matched instances that you select in the **Pattern Match** viewer. The **Bookmarks** configuration grid is populated with a row of data that represents the selected matched instance/s that contain the book marked messages.  
  
The **Bookmarks** grid contains the following information columns:  
  
-   **Name** — this sortable column provides a default name value of “**Selected messages**” or “Pattern Group \<n>”, where \<n> is a number placeholder. You can modify this column with a name of your choice, either by double-clicking the existing name in this text box or by right-clicking the text and selecting the **Edit ‘Name’** item in the context menu that appears. The existing text is then highlighted for edit mode.  
  
-   **References** — specifies a single message number or a comma-separated list of the message numbers for the messages you selected in the **Analysis Grid** viewer, or displays a **Selected Pattern Match Instance** (containing one or more messages) that you selected in the **Matched Instances** section of the **Pattern Match** viewer for which you are configuring a bookmark.  
  
-   **Category** — this sortable column is empty by default, but you can specify your own **Category** name for any bookmark. You can do this either by double-clicking the **Category** text box for a particular bookmark row in the **Bookmarks** configuration grid, or by right-clicking the **Category** text box in a bookmark row and selecting the **Edit ‘Category’** item in the context menu that appears. You can then create a new **Category** name or edit an existing one.  
  
-   **Messages** — this column specifies the number of messages that exist in a bookmark row. To view these messages, click on the  book icon.  
  
-   **Flag** icon — this sortable column is empty by default, but you can configure it with a chosen flag color to indicate a self-defined level of importance, interest, or critical context that a bookmarked entity represents. You can set a **Flag** color by right-clicking a bookmark row under the **Flag** column, clicking the **Flags** item in the context menu that appears, and then selecting the **Flag** color in the context submenu.  
  
-   **Link** icon — this sortable column enables you to attach one or more files to a bookmark, as described in [Adding Attachments and Comments](bookmarks-tool-window.md#BKMK_AttachFile-CommentsToBkmk).  
  
-   **Comment** icon — this sortable column enables you to add one or more comments to a bookmark, as described in [Adding Attachments and Comments](bookmarks-tool-window.md#BKMK_AttachFile-CommentsToBkmk).  
  
-   **Pattern** icon — becomes active when you are adding a bookmark to a **Pattern Group** row. This occurs after you select a pattern match in the **Matched Instances** section of the **Pattern Match** viewer and then select the **Pattern Bookmark** command from the **Add** drop-down menu on the toolbar of the **Bookmarks** window.  
  
-   **Scope** — this column is set to **Shared** by default, which enables all users to see the bookmarks you configure. However, in a future Message Analyzer release, you may be able to limit the scope to **Private** so that only you can view the bookmarks you configure in a particular set of trace results.  
  
## Using the Bookmarks Toolbar Commands  

 The commands that are available on the **Bookmarks** toolbar consist of the following:  
  
-   **Add** drop-down menu — provides the commands that enable you to configure a **Message Bookmark** or a **Pattern Bookmark**. The enabled/disabled state of these commands corresponds with the session viewer that is in focus.  
  
-   **Delete** — enables you to delete a bookmark that you select/highlight in the **Bookmark** configuration grid.  
  
-   **View** drop-down list — provides list options that enable you to display bookmarked messages or matched instances in different views:  
  
    -   **Analysis Grid** — select this option to display the messages in a **Selected messages** group in a separate instance of the **Analysis Grid** viewer, for analysis of message details and stack information.  
  
    -   **Message Gantt** — select this option to display the messages in a **Selected messages** group in a separate instance of the **Gantt** viewer, to correlate the message time range and IP address pair information of the book marked messages.  
  
    -   **Pattern Viewer** — select this option to display the **\<n> message(s)** locator button in the **MATCHES** pane of the **Pattern Match** viewer for a **Pattern Group** bookmark that you selected in the **Bookmarks** configuration grid. By clicking the message locator, you can display the pattern match instance that corresponds with the **Pattern Group** bookmark that you selected in the **Bookmarks** configuration grid. This is the method you will use to redisplay previously book marked pattern match instances.  
  
    -   **Pattern Gantt** — select this option to display the messages of a **Pattern Group** in a separate instance of the **Gantt** viewer, to correlate the message time range and IP address pair information of the pattern matched messages.  
  
<a name="BKMK_AddBookMarksToExisting"></a>   
## Adding Bookmarks to an Existing Bookmark or Group  
 After you create a **User Bookmark** for one or more messages, or create a **Pattern Group** bookmark with one or more messages of a **MATCHED INSTANCE** from the **Pattern Match** viewer in it, you can continue to add bookmarked messages to either of these entities. You can do this by selecting the **Message Bookmark** item in the **Add** drop-down menu to display a submenu that lists any existing **User Bookmark** or **Pattern Group** bookmarks. By selecting an existing bookmark or group in this submenu, you will add any message that is highlighted to the selected bookmark or group. This is true whether you are adding highlighted messages in the **Analysis Grid** viewer or the **Pattern Match** viewer.  
  
 You can use this feature to add messages to a bookmark in any conceivable combination. For example, if you are working in the **Pattern Match** viewer, you can add the messages of a selected **MATCHED INSTANCE** to an existing **Pattern Group** bookmark. You could also add one or more messages that are highlighted in the **Analysis Grid** viewer to an existing **Pattern Match** group, or you can add the messages of a **MATCHED INSTANCE** to an existing **User Bookmark**.  
  
<a name="BKMK_AttachFile-CommentsToBkmk"></a>   
## Adding Attachments and Comments  
 To attach a file or add a comment to a bookmark, you must first click the book icon in the **Name** column of the **Bookmarks** configuration grid for the **Selected message** or **Pattern Group** row where you want to attach a file or add a comment. When you click the book icon (or double-click any non-editable field), a drop-down displays with the following three tabs, from where you can perform the indicated tasks:  
  
-   **Messages** — the default tab that enables you to view all message rows where you added a bookmark, which includes a display of message numbers and a corresponding **Summary** description for each message in the selected **Bookmarks** message row. Whether you click the book icon for a **Selected messages** row or **Pattern Group** row, the **Messages** tab displays the same type of information.  
  
-   **Links** — this tab enables you to add one or more file attachments to a bookmark. You can do this by clicking the open folder icon on the **Links** tab to launch the **Open** dialog and navigate to a file you want to attach; then click the **+** button (green icon with **Add Link** tooltip) to add the attachment to the attachment list. You can also delete any existing attachment by selecting it in the attachment list and clicking the delete (**X**) button.  
  
-   **Comments** — this tab enables you to specify one or more comments for any **Bookmarks** message row by clicking the **+Add** button and entering an optional comment **Title**, descriptive text for the comment, and saving the comment by clicking the **Save Changes** icon. You can also delete any existing **Comment** for a selected **Bookmarks** message row by clicking the delete (**X**) button.  
  
 > [!TIP]
 >  You can also configure a comment from the **Comments** **Tool Window**, which contains the identical interface components for configuring comments that you use in the **Bookmarks** window. However, the **Comments** window enables you to create comments that are independent of bookmark configuration.  
  
-   **Patterns** — this tab enables you to view all the **Pattern Group** rows where you added bookmarks. This tab contains a header that specifies the following information for each row of data:  
  
    -   **Pattern** — the name of the Pattern expression that you executed.  
  
    -   **Instance** — the identifying number of the matched instance you selected for a bookmark.  
  
    -   **Messages** — the number of messages that exist in the selected **Pattern Group** that displays in a **Bookmarks** configuration row.  
  
> [!NOTE]
>  The book icon in each data row in the **Bookmarks** configuration grid is enhanced with certain glyphs whenever a configured bookmark has an attached file and/or a specified comment. These glyphs consist of the same icons that delineate the **Link** and **Comment** column headers in the **Bookmarks** configuration grid, respectively.  
  
## Using Context Menu Commands  

The **Bookmarks** **Tool Window** contains a right-click context menu where you can access several commands that perform the actions indicated below when selected:  
  
-   **View Message Range in ‘Analysis Grid’** — enables you to display the range of messages that a bookmark contains in a separate instance of the **Analysis Grid** viewer.  
  
-   **Add Message Range to Filter** — enables you to automatically create the code for a view **Filter** based on the messages contained in a bookmark row. When applied, the filter will remove all messages from the current **Analysis Grid** viewer instance, except the messages that fall within the range of the selected bookmark. Note that for best results, the **Analysis Grid** viewer that is in the same session as the **Pattern Match** viewer must have the focus.  
  
 > [!TIP]
 >  This makes it convenient to save only the messages that were bookmarked by clicking the **Save As** item in the Message Analyzer **File** menu to open the **Save/Export Session** dialog.  
  
-   **Delete Bookmark** — enables you to delete any selected bookmark in the **Bookmarks** configuration grid.  
  
-   **Show Details** — enables you to expand the details of a selected message row as a drop-down in the **Bookmarks** window. This action also occurs when you click the book icon in a message row.  
  
-   **Flags** — enables you to choose a flag color to define a critical issue or level of importance that a particular set of bookmarked messages represents.  
  
-   **Open Links** — enables you to open one or more files attached to a **Bookmarks** message row. For example, if an attachment is a trace file, the message contents of the file will display in a separate **Analysis Grid** viewer session tab. If an attachment is an image, it will open in the default image viewer on your system for the particular file type.  
  
-   **Copy Selected Rows** — enables you to copy the text in the data columns of a selected **Bookmarks** data row.  
  
-   **Copy ‘columnName’** — enables you to copy the name of certain  bookmark columns, for example, the **Name** and **Category** columns. The single-quoted text in this command is a placeholder for the actual selected column.  
  
-   **Edit ‘columnName’** — enables you to specify and edit the name of certain bookmark columns, for example, the **Name** and **Category** columns. The single-quoted text in this command is a placeholder for the actual selected column.  
  
## Saving and Loading Trace Files Containing Bookmarks  

 If you want to save bookmarks that you have configured in a message collection, you can only do so by saving your messages in the Message Analyzer native .matp format. When saving a message collection that contains bookmarks, note that if you use the **Export** option in the **Save/Export Session** dialog to save your message collection to a .cap file, bookmarks will not be saved. When you reload a saved message collection containing bookmarks, for example, through **Open**, **Recent Files**, or a Data Retrieval  Session, the bookmarks you configured will display in the **Bookmarks** window, which should automatically open when messages are loaded.  
  
> [!IMPORTANT]
>  If you are adding bookmarks to a file that you loaded into Message Analyzer through a Data Retrieval Session, you must click the **Save** button on the global Message Analyzer toolbar to save your bookmarks.  Otherwise, they will not appear in such a file when you reopen it.  
  
<a name="BKMK_ViewingBookmarks"></a>   
## Viewing Bookmarked Data  
 To view bookmarked messages, load a saved file that contains bookmark data into the **Analysis Grid** viewer. Also, if you expect to be viewing book marked messages associated with **MATCHED INSTANCES** of the **Pattern Match** viewer, you should display the **Pattern Match** viewer from the **New Viewer** drop-down list that is accessible from the global Message Analyzer **Session** menu or on the global toolbar. Also ensure that the **Bookmarks** **Tool Window** — which is accessible from the **Windows** submenu in the global **Tools** menu — is also displayed.  
  
 Thereafter, you can use the following methods to view bookmarked messages:  
  
-   **Selected messages drop down** — with the **Analysis Grid** viewer in focus, highlight any **Selected messages** row in the **Bookmarks** window and then click the book icon for the selected row to display a drop-down containing your bookmarked message/s. Select each message in the drop-down to drive selection of the associated bookmarked messages in the **Analysis Grid** viewer.  
  
-   **Pattern Group message locator** — with the **Pattern Match** viewer in focus, highlight any **Pattern Group** row in the **Bookmarks** window and then select the **Pattern Viewer** item in the **View** drop-down list on the **Bookmarks** toolbar to display the message locator button in the **MATCHES** pane of the **Pattern Match** viewer. Then do the following:  
  
    -   Click the message locator button to display the pattern match instance (associated with the selected **Pattern Group** row) in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer.  
  
    -   Select the matched instance that displays and observe the display of messages associated with the bookmark in the **Messages** section of the **Pattern Match** viewer.  
  
    -   Select each of these messages to interactively drive selection of each message in the **Analysis Grid** viewer for further analysis, for example, to examine message **Details**.  
  
        > [!NOTE]
        >  To provide a more convenient view of message selection correlation, undock the **Pattern Match** viewer by dragging it by its tab away from the default location, and then use the docking navigation controls to reposition it directly adjacent to the **Analysis Grid** viewer.  
  
    ---  
  
    **More Information**   
    **To learn more** about the docking features, see [Working with Message Analyzer Window Layouts](working-with-message-analyzer-window-layouts.md).    

    ---  
  
-   **Pattern Group drop down** — click the book icon to the left of the **Pattern Group** of interest in the **Bookmarks** window to display a drop-down that contains the messages associated with a particular bookmarked **MATCHED INSTANCE** in the **Pattern Match** viewer.  
  
     You can then click each message in the drop-down to interactively drive selection of corresponding messages in the **Analysis Grid** viewer. As previously described, you can undock and reposition the **Pattern Match** viewer for a better view of message selection correlation.  
  
With these methods, you or another user can navigate through all bookmarked messages and pattern match instances.