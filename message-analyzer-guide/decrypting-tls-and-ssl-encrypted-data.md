---
title: "Decrypting TLS and SSL Encrypted Data | Microsoft Docs"
ms.custom: ""
ms.date: "2016-10-26"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6094e2d6-e977-4e3d-bae9-7472c925f85f
caps.latest.revision: 37
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Decrypting TLS and SSL Encrypted Data
In addition to the many tools that Message Analyzer provides to filter, analyze, and visualize network traffic and other data, Message Analyzer also provides a **Decryption** feature that can help you diagnose traces that contain encrypted Transport Layer Security (TLS) and Secure Sockets Layer (SSL) traffic. Decrypting TLS/SSL traffic can be critical to troubleshooting network, protocol, performance, and connectivity issues. The Message Analyzer **Decryption** feature also resolves existing limitations of the **Microsoft-PEF-WebProxy** Fiddler message provider, such as the non-transparency of errors and the inability to capture other TLS/SSL encrypted traffic besides HTTPS.  
  
> [!NOTE]
>  Please be aware that decryption of TLS v1.2 messages is also supported, as is TDS/TLS.  
  
 The Message Analyzer **Decryption** feature enables you to view data for Application layer protocols that are encrypted with TLS and SSL, such as the HTTP and Remote Desktop (RDP) protocols. However, to enable a **Decryption** session in Message Analyzer, you will need to import a certificate that contains a matching identity for a target server, specify a required password, and then save the configuration. You can then either load a saved trace file into Message Analyzer through a Data Retrieval Session or start a Live Trace Session that will be enabled for decryption.  Thereafter, Message Analyzer decrypts the trace by using the server certificate and password that you provided. After the trace results display in the **Analysis Grid** viewer, a **Decryption** **Tool Window** holds the decryption analysis information. If there are decryption failures, errors are reported to the **Decryption** window, where a red **Error** icon displays for each message that failed the decryption process. Detailed error descriptions are also provided in the **Decryption** window to assist in troubleshooting and analysis. If there are no errors reported, then the **Decryption** window displays either a blue **Info** icon for each message that was successfully decrypted, or a yellow **Warning** icon that flags each message for which a certificate could not be found.  
  
## Workflow Overview  
 Decryption works within the existing Message Analyzer architecture to simplify its usage and results analysis. After you provide and save one or more server certificates and passwords, Message Analyzer will decrypt target traffic that is encrypted with the Transport Layer Security (TLS) or Secure Sockets Layer (SSL) security protocols for any session containing such traffic in the current Message Analyzer instance. Note that existing certificates are recovered from the certificate store after Message Analyzer restarts; however, for security purposes, passwords are not. Therefore, if you want decryption to occur after a Message Analyzer restart, you will need to manually re-enter passwords each time. In any single instance of Message Analyzer where you have entered passwords for existing or new certificates, Message Analyzer can decrypt target messages whenever you load a saved file or run a live trace that retrieves such messages. Thereafter, Message Analyzer displays the decrypted data in the **Analysis Grid** viewer at an upper layer of the protocol stack and provides a separate **Decryption** window that presents decryption session analysis information, including status and errors. You can also save a trace that contains decrypted data in the .matp format, just as you would any other trace. All the Message Analyzer tools and features that normally enable you to manipulate and analyze message data are available for use in a decryption session, including the **Details**, **Message Data**, **Field Data**, and **Message Stack** **Tool Windows** that enable you to focus on specific message fields, properties, values, and layers.  
  
 The following steps are an overview of the workflow that you will typically follow when working with the **Decryption** feature:  
  
1.  Import and store server certificates and add passwords as required on the **Decryption** tab of the **Options** dialog that is accessible from the Message Analyzer global **Tools** menu, as described in [Adding Certificates and Passwords](decrypting-tls-and-ssl-encrypted-data.md#BKMK_AddCertsPwds).  
  
2.  Start a Live Trace Session or load a saved file through a Data Retrieval Session that contains target messages to enable Message Analyzer to decrypt as many conversations as possible, as described in [Decrypting Trace Data](decrypting-tls-and-ssl-encrypted-data.md#BKMK_DecryptTraceData).  
  
3.  View decryption status information and analyze results in the **Decryption** window grid, as described in [Analyzing Decryption Session Data](decrypting-tls-and-ssl-encrypted-data.md#BKMK_AnalyzeDecryptData).  
  
4.  Select message rows in the **Decryption** window and observe corresponding selection of decrypted messages in the **Analysis Grid**, as described in [Viewing Decrypted Messages](decrypting-tls-and-ssl-encrypted-data.md#BKMK_ViewDecryptedMsgs).  
  
5.  Use the **Analysis Grid** viewer along with the **Details**, **Message Data**, and **Message Stack** windows to analyze the decrypted data, as described in [Viewing Decrypted Messages](decrypting-tls-and-ssl-encrypted-data.md#BKMK_ViewDecryptedMsgs).  
  
6.  Save a decrypted trace in .matp format for sharing with others or for use in other applications, as described in [Saving Decryption Session Data](decrypting-tls-and-ssl-encrypted-data.md#BKMK_SaveDecryptedData).  
  
<a name="BKMK_AddCertsPwds"></a>   
## Adding Certificates and Passwords  
 To add a server certificate to the Message Analyzer certificate store, you must add it to the grid of the **Certificates** pane on the **Decryption** tab of the **Options** dialog that is accessible from the Message Analyzer **Tools** menu. To import a certificate into the Message Analyzer certificate store, click the **Add Certificate** button on the toolbar of the **Decryption** tab to open the **Add Certificate** dialog, navigate to the directory where the certificate is located, select the certificate, and click the **Open** button to exit the dialog. Each time you add a certificate in this manner, the **Password** field displays to enable you to manually enter a password for the certificate you are adding. The **Decryption** feature can decrypt conversations only if a corresponding certificate exists in the store and a password is provided for it. If you do not enter a password, or if it is an incorrect password, you will be prompted to add the correct information.  
  
 All certificates and passwords that you add to the grid on the **Decryption** tab of the **Options** dialog are saved to the certificate store and persist in the current Message Analyzer instance, unless you remove them by clicking the **Clear List** button in the toolbar on the **Decryption** tab. Note that if you remove certificate entries from the list and click **OK** to exit the **Options** dialog, neither the certificates nor the passwords will be listed in the grid following a Message Analyzer restart.  
  
## Obtaining a Server Certificate  
 If you require a security certificate from a server on which you are capturing encrypted message traffic, you can obtain one by using the Certificate Manager MMC to export a server-side certificate (from the server). Note that the client-side version of such a certificate does not have the information needed to decrypt the data. Cipher suites are typically decided by the server configuration. Note that you may have to make modifications to the client- or server-side to locate a cipher suite that is supported by Message Analyzer.  
  
## Enabling Certificates  
 Certificates and passwords are not enabled for a Data Retrieval Session or a Live Trace Session unless you specifically select them prior to the session. To enable or disable a certificate in the certificate list, either select or unselect the check box to the left of the certificate name, respectively. In addition, you can enable or disable all certificates simultaneously by either selecting or unselecting the **Name** check box, respectively. Before loading data or running a live trace that you want to decrypt, make sure that your certificate/s are enabled by selecting the appropriate certificate check box in the certificate list; you should also ascertain that a password for the certificate displays in hidden text in the **Password** column. When you are finished adding certificates and passwords, click the **OK** button to exit the **Options** dialog, at which time the certificate and password are stored. Thereafter, the certificate that you added is accessible to all subsequent decryption sessions, including those following Message Analyzer restarts; however, the password is made available for decryption sessions that use that certificate in the current Message Analyzer instance only.  
  
<a name="BKMK_DecryptTraceData"></a>   
## Decrypting Trace Data  
 After adding the appropriate certificate/s to the grid on the **Decryption** tab of the **Options** dialog and specifying the corresponding password/s, you are ready to load data into Message Analyzer or to run a live trace that retrieves the applicable messages that you want to decrypt. You can load data through a Data Retrieval Session or run a Live Trace Session with decryption enabled in the same way you load any other file or run any other trace with Message Analyzer. Prior to loading a file in a Data Retrieval Session or starting a Live Trace Session with decryption enabled, you are advised to select the **Analysis Grid** viewer from the **Start With** drop-down list in the **New Session** dialog for ease of analysis. After you load your data or you stop a Live Trace Session and the **Decryption** process completes, message data displays in the **Analysis Grid** viewer and the decryption analysis data displays in the **Decryption** **Tool Window**.  
  
 Message Analyzer also makes it convenient for you to decrypt messages that were captured in multiple simultaneous conversations across different servers. Rather than decrypting the conversations one by one, you can simply input a list of certificates and passwords into the certificate store for the current Message Analyzer instance and then load the trace files containing the target conversations into Message Analyzer through a Data Retrieval Session. Thereafter, Message Analyzer will match the provided certificates to the appropriate conversations and decrypt as many messages as possible.  
  
<a name="BKMK_AnalyzeDecryptData"></a>   
## Analyzing Decryption Session Data  
 After Message Analyzer decrypts messages in a trace, you can analyze the results in the **Decryption** window. If this **Tool Window** is not already open, you can display it by clicking the Message Analyzer **Tools** menu, selecting the **Windows** item, and then clicking **Decryption** in the menu that displays. The **Decryption** window contains the following columns of information:  
  
-   **Type** — lists the different **Decryption** types with different icons, which have the meanings that follow. Note that messages that are associated with these icons are displayed in the **Message** column:  
  
    -   **Info** — this blue icon indicates that a message was successfully decrypted, as the necessary certificates and passwords were located in the certificate store. The informational message associated with this icon might consist of the name of the certificate that was used in the decryption.  
  
    -   **Warning** — this yellow icon indicates that a message could not be decrypted, as the corresponding certificate and password were unavailable. The warning message associated with this icon might consist of public key information for the missing certificate that can help you to locate it.  
  
    -   **Error** — this red icon indicates that a message could not be decrypted because an error occurred, for example, as the result of an incomplete TCP handshake. The error message associated with this icon might consist of error information and troubleshooting advice.  
  
-   **Timestamp** — specifies message time stamps in a user friendly format.  
  
-   **ProtocolVersion** — lists the version of the protocol message that was subject to the **Decryption** process.  
  
-   **SourcePort** — displays the TCP source ports that carried the conversations that were subject to the **Decryption** process.  
  
-   **DestinationPort** — displays the TCP destination ports that carried the conversations that were subject to the **Decryption** process.  
  
-   **SourceAddress** — displays the source IP addresses that carried the conversations that were subject to the **Decryption** process.  
  
-   **DestinationAddress** — displays the destination IP addresses that carried the conversations that were subject to the **Decryption** process.  
  
-   **Decrypted Message Count** — lists the number of messages that were decrypted.  
  
-   **Undecrypted Message Count** — lists the number of messages that were not decrypted.  
  
-   **Message** — specifies informational messages related to one of the decryption icons, to provide additional details about the **Decryption** process, for example **Error** information.  
  
<a name="BKMK_ViewDecryptedMsgs"></a>   
## Viewing Decrypted Messages  
 To view the decrypted data itself, select a message row in the **Decryption** window and observe that it drives message selection in the **Analysis Grid** viewer. For example, if Message Analyzer decrypted HTTPS data, a top-level HTTP message might now be selected in the **Analysis Grid** viewer, as shown in the figure that follows, depending on the message row you selected in the **Decryption** window. Application Layer HTTPS messages are normally encrypted when the Microsoft Windows Internet (WinInet) Service passes them to cryptographic components such as the TLS security protocol, which in turn passes encrypted/secure data to the Transport Layer. As a result of TLS encryption, Message Analyzer does not normally process and display such messages unless you use the **Decryption** feature. When you do, you can see the encrypted message layer as part of the origins stack beneath the decrypted message at top-level in the **Analysis Grid** viewer. In the example of the following figure, the node of the decrypted HTTP message is expanded so that you can see the encrypted message layer (TLS) and the original protocol stack in the origins tree.  
  
 ![Decrypted data and message stack](media/fig29-decrypted-data-and-message-stack.PNG "Fig29-Decrypted data and message stack")  
  
 **Figure 29: Decrypted data and message stack**  
  
 Because message selection in the **Analysis Grid** viewer in turn drives the display of data in the **Details**, **Message Data**, and **Message Stack** window, you can use these **Tool Windows** to view the decrypted and encrypted message data, which includes field data in the **Details**, hexadecimal data in the **Message Data**, and top-level messages with origins layers in the **Message Stack** window. Note that field selection in the **Details** window drives the display of corresponding hexadecimal data in the **Message Data** window, such that you can view the hexadecimal value of any message field that you select.  
  
<a name="BKMK_SaveDecryptedData"></a>   
## Saving Decryption Session Data  
 You can save decrypted trace data in the same manner that you save any other trace data. You simply select the **Save** item in the Message Analyzer **File** menu to display the **Save As** dialog, where you can select one of three save options, as follows:  
  
-   **All Messages** — enables you to save all messages from a **Decryption** session that are displayed in the **Analysis Grid** viewer.  
  
-   **Filtered Messages** — enables you to save a filtered message set, for example, if you applied a view **Filter** to your **Decryption** session results.  
  
-   **Selected Messages** — enables you to save only specific messages that you select in an **Analysis Grid** viewer session tab; for example, you might want to save specific decrypted messages and their origins messages of the associated protocol stacks.  
  
 After you specify one of the indicated save options, you can save your data as follows:  
  
-   **Save As** — click this button to save your decrypted data in the native .matp trace file format. If you reload such a file, it is unnecessary to enable **Decryption** again to see the decrypted data in a Message Analyzer viewer such as the **Analysis Grid**.  
  
-   **Export** — click this button to save your data in the .cap trace file format. If you select this option, your decrypted data will not be saved; however, you can reapply **Decryption** to this file when you reload it so that you can view the decrypted data again.  
  
 ___________________\_  
  
 **More Information**   
 **To learn more** about starting and configuring a new Data Retrieval Session or a Live Trace Session, see [Starting a Message Analyzer Session](starting-a-message-analyzer-session.md).  
**To learn more** about saving trace data, see the [Saving Message Data](saving-message-data.md) section.   
___________________\_  
  
## See Also  
 [Decryption Tool Window](decryption-tool-window.md)