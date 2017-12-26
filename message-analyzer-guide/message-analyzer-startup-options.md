---
title: "Message Analyzer Startup Options | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 378279ef-3e71-4204-bb2e-a0ad1e702f6a
caps.latest.revision: 31
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---

# Message Analyzer Startup Options

This section describes several different ways in which you can start Message Analyzer. Note that the first time you start Message Analyzer after installation, you are prompted by the **Welcome to Message Analyzer** dialog to opt-in or opt-out of automatic updates to Message Analyzer user Library asset collections. To understand what these options mean, refer to [Syncing Items on First Startup](syncing-items-on-first-startup.md).

 The topics ahead describe various ways of starting Message Analyzer along with the startup options that are available. Also, the option for changing the location of Message Analyzer temporary files to a non-system drive is included.

## Using Various Methods to Start Message Analyzer

 Message Analyzer startup methods consist of the following:

- Click the **Microsoft Message Analyzer** icon in your computer’s **Start** menu or on the system Taskbar.

- Double-click a supported Message Analyzer file, such as a .matp, .matu, or .cap file.

    > [!NOTE]
    > When you double-click a supported trace or log file to start Message Analyzer, or if you use the right-click method indicated next, the file’s message data is automatically loaded into the **Analysis Grid** viewer by default.

- Right-click a supported Message Analyzer file and select the **Open** item from the context menu. Note that in some cases, you might need to select the **Open with Message Analyzer** item in the context menu, for example, with a .cap or .etl file.

- Specify a startup command string at the command line prompt, as described ahead.

> [!NOTE]
> For more information about supported Message Analyzer files, see [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md).

## Starting Message Analyzer From the Command Line

 When you start Message Analyzer from the command line, you can do the following:

- Launch Message Analyzer to the **Start Page**, without opening a trace or log file.

- Start Message Analyzer while opening a specified trace or log file, which displays data in the **Analysis Grid** viewer by default.

- Start Message Analyzer while specifying various command line options associated with locating, logging, and compiling any custom OPN parsers that you have created for Message Analyzer use.

 The basic syntax for starting Message Analyzer from the command line is the following:  `MessageAnalyzer.exe [TraceFile|LogFile] [Options]`

 For example, you can open Message Analyzer from the command line without specifying a trace file, log file, or any options, as follows:  `“C:\Program Files\Microsoft Message Analyzer\MessageAnalyzer.exe”`

 You can also specify a trace or log to open, as indicated in the following example, but it must be in one of the supported file formats, as described in [Locating Supported Input Data File Types](locating-supported-input-data-file-types.md):   `“C:\Program Files\Microsoft Message Analyzer\MessageAnalyzer.exe” <TraceFile.matp>`

## Using the Startup Switches

 The command line switches that are available for starting Message Analyzer at a command prompt are described below. To view these options at the command line, specify the following help switch:  `"C:\Program Files\Microsoft Message Analyzer\MessageAnalyzer.exe" /?`

> [!IMPORTANT]
> With exception of the **TraceFile** argument and the command line usage switch, the following list items enable you to locate, compile, log, and debug custom OPN parsers that you have created for use with Message Analyzer.

- **TraceFile** — specifies the name and path to the trace or log file to open when Message Analyzer starts.

- **/?** — displays the command line usage instructions described here.

- **/OPNLoadPathOnly=\<path>** — specifies the only path from which you will load custom OPN parsers. If this switch is specified, the default OPN load path in Message Analyzer is ignored. Note that this switch cannot be used with the `/OPNLoadPathMerge` option.

- **/OPNLoadPathMerge=\<path>** — adds the specified path to the list of paths from which you will load custom OPN parsers. Note that this switch cannot be used with the `/OPNLoadPathOnly` option.

    > [!IMPORTANT]
    > If you create a new path from which to load custom OPN parsers and you place a native Message Analyzer parser in this path, for example, a user-extended native parser with the same name, Message Analyzer will start improperly.

- **/EnableTracing \<flag>** — specifies whether tracing is enabled. When set to True, tracing is enabled; when set to False, tracing is disabled (the default value if this switch is not specified).

- **/LogMode=\<log mode>** — specifies the output of the compilation log for debugging OPN. The log mode enables you to redirect log messages in the following ways:

  - **/LogMode=File** — saves log messages to a log file. If you do not specify a \<filename> value with the `/LogPath` switch, the log file will be created as %LOCALAPPDATA%\Microsoft\MessageAnalyzer\Parsers.log.

  - **/LogMode=Console** — redirects log messages to the console.

  - **/LogMode=ETW** — redirects log messages to the Windows Event Trace system.

  - **/LogMode=Default** — redirects log messages to the Win32 debug output.

- **/LogPath=\<file name>** — creates a log file with the specified file name. This switch can be used only with the `/LogMode-File` option.

- **/CachePath=\<path>** — specifies a path to an alternate cache folder where custom OPN parser model and codec files will be written and read, so that the default compilation cache for OPN parsers provided with Message Analyzer is not overwritten. Message Analyzer will then point to this folder at startup.

- **/GenerateOPNSymbols** — generates PDB (Program Database) files during OPN compilation for instrumentation and debugging. When a .pdb file is generated, you can attach Message Analyzer to a debugger to debug OPN-generated C# code.

- **/OptimizeOPN=\<flag>** — specifies whether or not OPN compilation should be optimized; for example:

  - **/OptimizeOPN=true** — optimizes OPN compilation. True is the default value, if this switch is unspecified.

  - **/OptimizeOPN=false** — does not optimize OPN compilation. Makes it easier for OPN debugging, which is more difficult to perform when OPN code is optimized. Note that if you specify this flag, Message Analyzer will have to perform recompilation at startup time.

## Changing the Message Analyzer Temporary Files Location

 Message Analyzer enables you to specify a location on a non-system drive for Message Analyzer temporary files. You might do this for the following reasons:

- **Better management of disk space** — avoids excessive use of memory space from Message Analyzer writing to your c:\ drive over a period of time.

- **Better performance** — Message Analyzer has better performance when writing to a non-system drive.

- **Improve performance on Windows 8 and later** — Message Analyzer performs better on the Windows 8 operating system and later if the destination disk is formatted to the Resilient File System (ReFS), instead of the enforced NTFS format of your default system drive.

 Although the main application that benefits from reconfiguration of the temporary files location is usually server components, you still have the option change the location. If you want to do this you will need to open the MessageAnalyzer.exe.config file from the following location (or the installation folder location that you specified when installing Message Analyzer), and modify it as indicated below. Note that you could open this XML file in the Visual Studio IDE for the convenience of auto-formatting:

 `C:\Program Files\Microsoft Message Analyzer\MessageAnalyzer.exe.config`

 Under the `<configuration/>` node in the MessageAnalyzer.exe.config XML file contents, enter the following and specify an appropriate value for  the drive location.

```Configuration
<appSettings>
<add key="TempFolderPath" value="<driveLocation>\temp\matemp" />
</appSettings>

```

## See Also

 [Starting Message Analyzer for the First Time](installing-and-upgrading-message-analyzer.md#BKMK_StartingMAFirstTime)