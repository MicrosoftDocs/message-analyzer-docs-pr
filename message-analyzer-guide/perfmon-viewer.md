---
title: "Perfmon Viewer | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c0534605-5c62-41af-8c14-23c9f1ae1a11
caps.latest.revision: 17
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Perfmon Viewer
Message Analyzer provides the **Perfmon Viewer**, which is currently a preview feature. If you wish to use the **Perfmon Viewer**, you will need to select its check box on the **Features** tab of the **Options** dialog, which is accessible from the global Message Analyzer **Tools** menu, and then restart Message Analyzer. It will then be available for selection in the **New Viewer** drop-down list on the global Message Analyzer toolbar.  
  
## Understanding the Perfmon Viewer  
 Message Analyzer enables you to view data from **Microsoft Performance Monitor** log files in the \*.blg format with use of the **Perfmon Viewer**. You can view this data similarly to the way it appears in **Performance Monitor**. To assess this type of data, you might begin by creating a custom data collector set with **Performance Monitor** that contains one or more performance counters. **Performance Monitor** enables you to select from a set of templates that each specify  some performance counter presets, or you can manually create your own counters. For example, you could create a custom data collector set that configures one or more performance counters that monitor  and return statistics for various entities such as HTTP services, Event Tracing, Hyper-V adapters, IPv4 performance, SMB operations, TCP performance diagnostics, and so on. After you configure and name a data collector set, it will appear under the **User Defined** node in the **Data Collector Sets** container of the **Performance Monitor** MMC.  
  
 After collecting data, you will need to right-click the data collector set name under the **User Defined** node and select the **Stop** command in the context menu that appears, before you can load the output log data into Message Analyzer. You can then view the collector set log file data by loading it into Message Analyzer through a Data Retrieval Session. After you load and display the data, typically in the **Analysis Grid** viewer, you can open the **Perfmon Viewer** from the **Common** category of the **New Viewer** drop-down list on the global Message Analyzer toolbar. To graphically display the performance counter data stored in the log, you will need place a check mark in each **Show** check box of the **Perfmon Viewer** for specific counters that collected data you want to view. The **Perfmon Viewer** specifies a different color code for the data lines of each preset performance counter and also provides controls that enable you to **Zoom** into preset windows of time for analysis.  
  
> [!TIP]
>  You might consider correlating the performance counter data that you collect with that of another related data source, such as an ETL file, live trace,  or Event Log, for an enhanced analysis perspective.  
  
---  
  
 **More Information**   
 **To learn more** about using multiple data sources in a Data Retrieval Session, see [Configuring Session Scenarios with Selected Data Sources](configuring-session-scenarios-with-selected-data-sources.md).  
---  
  
## Using the Perfmon Viewer Controls for Analysis  
 Several controls are available in the **Perfmon Viewer** to facilitate analysis of collected data. To analyze counter data with the **Perfmon Viewer**, you can use the controls and indicators that exist in the lower and upper sectors of the viewer interface, which are referred to as the Counter Table and the Data Grid, respectively. The controls can change the way you display the data to facilitate analysis. For example, you can select which counters will display data,  set the ranges of the X and Y axis in the data grid to facilitate focused analysis, and select individual data points in the data grid to analyze the counter statistics associated with a selected data point. The controls and indicators in each sector of the viewer interface consist of the following:  
  
-   **Counter Table** — this table is located in the lower sector of the **Perfmon Viewer**. It consists of a list of the performance counters that recorded data in a *.blg file. The table contains the following columns, some with control features and others with data that is associated with each counter that collected data:  
  
    -   **Show** — enables you to select one or more counters so that you can isolate specific data of interest for display in the data grid.  
  
    -   **Color** — provides an indicator of the default color for each counter. Also enables you to change the default color for any particular counter by clicking the down arrow in the **Color** column of a specific counter to display the **Color** dialog, from where you can specify a color of choice.  
  
    -   **Scale** — specifies the current value of the Y-axis scaling for a particular line of counter data. Click the down arrow in the **Scale** column of a particular counter to display a drop-down list containing preset **Scale** values from which you can select. With this control, you can manipulate the range of the Y-axis, which plots the relative deviations of counter values over time.  
  
    -   **Counter** — each row of the counter table displays the name of a counter in this column.  
  
    -   **Instance** — provides an indication of the number of instances associated with a counter, such as you might have with processes or threads running with the counter and collecting data.  
  
    -   **Object** — specifies the name of the object from which a counter is collecting data.  
  
    -   **Computer** — specifies the name of the computer on which a counter is collecting data.  
  
-   **Data Grid** — the Data Grid is located in the lower sector of the **Perfmon Viewer**. It displays the data for any selected counter in the X-Y coordinate domain. The X-axis is calibrated in time while the Y-axis is calibrated for the relative deviation of counter values. To focus in on your counter data, you can change the X-axis calibration by setting **Scale** values, as described earlier, and you can change the Y-axis calibration with use of the configuration toolbar described in the list below.  
  
     You can also select data points in the Data Grid by clicking on a particular point in a counter data line. At that time, you will see the associated counter data appear in the  **Message Stack** **Tool Window** of Message Analyzer and the values of associated data fields will display in the **Details** **Tool Window**. For example, you might review the **Value** field for a selected data point in the **Values** column of the **Details** window.  
  
    > [!TIP]
    >  Through data point selection in the Data Grid, you may be able to correlate information across multiple related logs that you retrieve with Message Analyzer.  
  
     The Data Grid also contains a context menu with the following commands that appear when you right-click anywhere in the Data Grid surface:  
  
    -   **Highlight Selected** — when you select this command, it causes the line of counter data in the grid to be bolded as you select it in the **Show** column of the counter table.  
  
    -   **Show Grid Lines** — toggle this command to alternatively show and hide grid lines in the Data Grid.  
  
    -   **Show Search/Configuration Bar** — when you select this command, it causes the **Search/Configuration Bar** to display. The search control on this toolbar enables you to specify a search string that reflects a particular value for which you are looking in any column. The configuration portion of this bar enables you to recalibrate the X-axis time range (and format) to **Zoom** in on data for focused analysis. Other controls enable you to select or unselect all counters simultaneously.