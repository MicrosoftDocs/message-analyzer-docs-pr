---
title: "Managing Trace Scenarios | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.locale: "en-us"
ms.assetid: 08aa0fb2-3798-4cbf-b965-b3a03ef65d64
caps.latest.revision: 27
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Managing Trace Scenarios
Message Analyzer provides facilities for managing your local **Trace Scenarios** Library. This means you can create and modify **Trace Scenarios**, set them as **Favorites** (by clicking the star to the left of a scenario in the **Trace Scenarios** Library), and share them with others. The Message Analyzer Sharing Infrastructure enables you to choose **Trace Scenario** items in your local Library and share them with others, and you can also add **Trace Scenario** items to your local Library from others. To do this, Message Analyzer enables you to **Export** your **Trace Scenarios** to a designated location to make them accessible to other users on your team or to the larger Message Analyzer community; or you can **Import**  **Trace Scenarios** from other users who make their scenarios available to you in the same manner. This includes any custom **Trace Scenario** templates that you or others have created. Designated share locations can include a user-defined SMB share, a Web server resource, or a custom subscriber feed in the Message Analyzer Sharing Infrastructure that you configure from the **Settings** tab in the **Asset Manager** dialog, which is accessible from the Message Analyzer global **Tools** menu. When you export one or more **Trace Scenarios**, they are saved to a designated location as an asset collection file (*.asset) so that others can import one or more items in the collection.  
  
## Manage Trace Scenarios Dialog  
 You can manage **Trace Scenarios** from the **Manage Trace Scenario** dialog, which displays when you click the **Manage Trace Scenarios** item in the **Select Scenario** drop-down list on the **ETW Providers** toolbar of the **New Session** dialog. From the **Manage Trace Scenario** dialog, you can export and import **Trace Scenarios**, in addition to performing other scenario management tasks, as described in the subtopics that follow.  
  
 **Exporting Trace Scenarios**   
The **Manage Trace Scenarios** dialog enables you to select the items you want to export in an asset collection for sharing or backup. After you select one or more **Trace Scenarios** that you want to share with others, click the **Export** button on the toolbar of the **Manage Trace Scenario** dialog to display the **Save Library** dialog, from where you can specify **Title**, **Description**, and **Organization** information. After you click **Save** in the **Save Library** dialog, the **Select Library Location** dialog displays and enables you to navigate to the location where you want to save your **Trace Scenario** asset file, which is typically a remote share or other feed that you configure from the **Settings** tab of the **Asset Manager** dialog.  
  
> [!NOTE]
>  In a future Message Analyzer release, the  Sharing Infrastructure may support the full publishing process for Message Analyzer asset collections that are shared on user-configured feeds. Currently, you can download **Trace Scenario** asset collections from user feeds, but you cannot yet configure them to automatically synchronize with periodic updates, unless you perform the manual configuration process described in [Manual Item Update Synchronization](manual-item-update-synchronization.md). Also, you can always synchronize to and download asset collection updates from the **Message Analyzer** feed on the **Downloads** tab of the **Asset Manager** dialog to obtain the latest asset collections, such as **Trace Scenarios**,  **Filters**, **Color Rules**, **View Layouts**, and so on.  
  
 **Importing Trace Scenarios**   
The **Manage Trace Scenarios** dialog enables you to import asset collections that others have shared to some predefined location. To perform this task, click the **Import** button on the toolbar of the **Manage Trace Scenarios** dialog to display the **Select Library to Open** dialog. From this dialog, you can navigate to the local or network location where asset files are stored for sharing. After you select a \*.asset file, click the **Open** button in the **Select Library to Open** dialog to display the **Select Items to Import** dialog. From this dialog, you can specify the items from the asset collection that you want to import, along with the **Category** in which to place the imported scenarios in your local **Trace Scenarios** Library, or you can accept the default **Category** location. Click **OK** to exit the dialog and post the **Trace Scenarios** to the Library **Category** that you specified.  
  
> [!NOTE]
>  **Trace Scenario** items that you import will appear under the **My Items** top-level category in the subcategory name that you specified, after a Message Analyzer restart.  
  
 **Other Management Tasks**   
The **Manage Trace Scenario** dialog also enables you to open the **Edit Trace Scenario** dialog by right-clicking any **Trace Scenario** in the **My Items** category of the **Trace Scenarios** library and then selecting the **Edit** item from the context menu that displays. From the **Edit Trace Scenario** dialog, you can modify certain metadata that is associated with any scenario before exporting it as an asset file, as follows:  
  
-   **Name** — change the name of a **Trace Scenario**.  
  
-   **Description** — modify the **Trace Scenario** description.  
  
-   **Category** — select a different **Category** in which to place the scenario, or you can create a new **Category**.  
  
> [!NOTE]
>  You cannot edit or delete any of the predefined **Trace Scenarios** that are provided by default in your Message Analyzer installation. You can edit scenario information or delete scenarios under the top-level **My Items** category only. The **My Items** category is reserved as user space in the **Trace Scenarios** library.  
  
 You can also create a copy of any **Trace Scenario** in any category, for example to move a copy to the **My Items** **Category**, by right-clicking any **Trace Scenario** in the **Manage Trace Scenario** dialog and selecting the **Create a Copy** item in the context menu that displays. When you do this, the **Edit Trace Scenario** dialog displays, from where you can modify any of the previously indicated parameters associated with the scenario and then **Save** it. Lastly, if you want to remove a **Trace Scenario** from the **My Items** category of the Library, you can right-click the scenario and select the **Delete** item in the same context menu. Note that the **Delete** command in the right-click context menu is disabled for all of the predefined **Trace Scenarios**, which prevents the removal of any of the predefined scenarios in your Message Analyzer installation.  
  
---  
  
 **More Information**   
 **To learn more** about the Message Analyzer Sharing Infrastructure and the common **Manage \<AssetType>** dialog format that is used to manage various Message Analyzer Library asset collections, see the [Sharing Infrastructure](sharing-infrastructure.md) topic.   
---