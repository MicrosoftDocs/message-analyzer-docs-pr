---
title: "Understanding Message Pattern Matching | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 395396f3-0924-499a-8c1e-f795ffe9cd7c
caps.latest.revision: 55
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Understanding Message Pattern Matching
Message Analyzer enables you to process a set of trace results to retrieve groups of messages that meet the sequential pattern criteria of manually configured or built-in **Pattern** expressions. Whenever you execute a **Pattern** expression by selecting one in the **AVAILABLE PATTERNS** pane of the **Pattern Match** viewer, an API is accessed that calls into the pattern matching engine which starts the search for a pattern match based on the definition of the selected **Pattern** expression.  
  
> [!NOTE]
>  The underlying technology that you use to create **Pattern** expressions is part of the full Open Protocol Notation (OPN) language, as described in the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx).  
  
## Accessing Built-In Pattern Expressions  
 Message Analyzer provides you with the option to use several built-in OPN **Pattern** expressions that are included in every Message Analyzer installation by default. You can access the built-in expressions only after you open the **Pattern Match** viewer, where they are included as a list in the **AVAILABLE PATTERNS** pane of this viewer. You can run a **Pattern** expression against a set of trace results by simply placing a check mark in the check box to the left of the **Pattern** expression that you want to execute, for example, the **TCP Retransmit Pairs** expression. Message Analyzer then begins searching for patterns that match the **Pattern** expression criteria and initially displays any matches that are found in a Matched pattern selector that appears in the **MATCHES** pane of the **Pattern Match** viewer.  
  
> [!NOTE]
>  Message Analyzer also provides an **Example Sequence Expression** for HTTP methods under the **My Items** category in the **AVAILABLE PATTERNS** pane of the **Pattern Match** viewer that you can edit however you want, as a practice development scenario.  
  
> [!IMPORTANT]
>  Microsoft will continue to develop pattern matching capabilities and make them available either from the Message Analyzer Sharing Infrastructure, and/or as part of the installation package in ongoing Message Analyzer release versions. This will include additional built-in **Pattern** expressions and extended functionality for the pattern matching engine.  
  
## Understanding Pattern Expressions  
 This section provides a code walkthrough of two of the built-in **Pattern** expressions that are related to TCP operations. By understanding the concepts of these working **Pattern** expressions, you can apply this knowledge when creating expressions of your own. The built-in **Pattern** expressions that are presented as examples consist of the following:  
  
-   **TCP Retransmit Pairs** — the OPN behavior scenario that defines this **Pattern** expression is encapsulated in the following OPN code:  
  
    ```  
    using TCP;  
    using IPv4;  
    using IPv6;  
    using Utility;  
  
    // Identifies pairs of TCP messages with same Sequence and Ack numbers, // the same payload size, and the same   
    // IP source and destination addresses. Payload values must not be zero and KeepAlive messages   
    // are ignored. . .  
  
    virtual operation TCPRetrans  
    {  
      uint SeqNum = seqNum != 0 ? seqNum : seqNum6;  
      uint OrgMessageNumber = mn != 0 ? mn as uint : mn6 as  uint;  
      uint DestMessageNumber = mnretrans != 0 ? mnretrans as uint : mnretrans6 as uint;  
      (IPv4Address | IPv6Address) SourceAddress = sa != null ? sa : sa6;  
      (IPv4Address | IPv6Address) DestinationAddress = da != null ? da : da6;  
  
      override string ToString()  
      {  
        return "Frame: " + DestMessageNumber.ToString() + " Sequence Number " + SeqNum.ToString() +   
        " is a duplicate of frame " + OrgMessageNumber.ToString();  
      }  
    }  
    = backtrack(Segment{Payload.Count >= 1})  
    (  
    Segment{SequenceNumber is var seqNum, AcknowledgementNumber is var ack, !KeepAlive(value), Payload is var pyl,   
    GetMessageNumber(value) is var mn}  \\IPv4.Datagram { SourceAddress is var sa, DestinationAddress is var da}  
      ->  
      Segment{SequenceNumber == seqNum, AcknowledgementNumber == ack, Payload.Count == pyl.Count,   
      GetMessageNumber(value) is var mnretrans}  \\IPv4.Datagram { SourceAddress.Octets == sa.Octets,   
      DestinationAddress.Octets == da.Octets }  
    )  
    |  
    (  
      Segment{SequenceNumber is var seqNum6, AcknowledgementNumber is var ack6, !KeepAlive(value), Payload is var pyl6,   
      GetMessageNumber(value) is var mn6}  \\IPv6.Datagram { SourceAddress is var sa6, DestinationAddress is var da6}  
      ->  
      Segment{SequenceNumber == seqNum6, AcknowledgementNumber == ack6, Payload.Count == pyl6.Count,   
      GetMessageNumber(value) is var mnretrans6}  \\IPv6.Datagram { SourceAddress.Octets == sa6.Octets,   
      DestinationAddress.Octets == da6.Octets }  
    );  
  
    // The KeepAlive method projects the KeepAlive annotation into a   
    // boolean. The method returns only the ‘false’ case to ensure that   
    // KeepAlive messages are not evaluated. .  
    bool KeepAlive(Segment s)  
    {  
      return (s#IsKeepAlive != nothing)? (s#IsKeepAlive as bool) : false;  
    }  
  
    uint GetMessageNumber(any message x)  
    {  
      var origins = x.Origins;  
      if (origins.Count == 0)  
        return x#MessageNumber as uint;  
      else  
        return GetMessageNumber(origins[0]);             
    }  
    ```  
  
     This OPN scenario finds all TCP messages that were retransmitted as lost TCP segments and presents them in the Message Analyzer **Pattern Match** viewer as matched instances that each contain a pair of messages with an identical TCP SequenceNumber and AcknowledgementNumber. The results of this **Pattern** expression can provide an indication of network issues, for example, TCP retransmits are required because packets are being dropped by the network.  
  
     To retrieve these messages, this **Pattern** expression evaluates the input stream for the SequenceNumbers, AcknowledgementNumbers, and Payload values of TCP messages, along with the source and destination IP addresses to ensure a match. To simplify this walkthrough, only the IPv4 case is discussed, although the IPv6 case that follows the “&#124;” operator (OR) in the code is functionally similar:  
  
    1.  ***Virtual operation***  — following the using statements is a "virtual  operation” that provides for definition of variables and exposure of properties that are used in **Pattern** expression evaluations; for example, to hold source and destination IPv4 or IPv6 address values to check for matches; and to hold other TCP field values that are used to create a custom output message for display in the Message Analyzer UI whenever this **Pattern** expression finds a match.  
  
         ***Custom output message***  — as part of the virtual operation, the overridden ToString() method is used to create a custom output message based on values returned in the expression; it can also be any custom string value that you specify. The string value displays under the **Summary** column in the **MATCHED INSTANCES** pane of the **Pattern Match** viewer for each matched instance after the **Pattern** expression completes its evaluation.  
  
    2.  ***Backtracking***  — the line of code containing the “backtrack” statement indicates that the evaluation should start with, and always backtrack to, the next TCP Segment that has a Payload count that is greater than or equal to one.  
  
    3.  ***Segment evaluation***  — the line of code containing the first “Segment” statement retrieves the following entities from the first TCP message Segment in the trace results that has a Payload greater than or equal to one, and applies the indicated processing:  
  
        -   SequenceNumber — the variable “seqNum” is set to the numerical value of the first SequenceNumber.  
  
        -   AcknowledgementNumber — the variable “ack” is set to the numerical value of the first AcknowledgementNumber.  
  
        -   Payload — the variable “pyl” is set to the numerical value of the first Payload so that payload counts can be checked.  
  
        -   GetMessageNumber — a method that sets the variable “mn” to the current message number and returns it.  
  
        > [!NOTE]
        >  Observe that the KeepAlive method explicitly rules out TCP KeepAlive messages for evaluation, because they are not considered to be TCP retransmits.  
  
    4.  ***IP addresses***  — the line of code containing the “IPv4.Datagram” statement gets values that set the “sa” and “da” variables based on the values of the IPv4 SourceAddress and DestinationAddress, respectively. Note that the expression uses the double backslash characters “\\\” to get at the IPv4 level of the TCP origins tree, as described in [Browsing Message Origins](using-the-filtering-language.md#BKMK_BrowseMessageOrigins).  
  
    5.  ***Segment evaluation***  — the line of code containing the second “Segment” statement causes the expression to continue to evaluate the input stream until a TCP message Segment is found with:  
  
        -   A SequenceNumber that is identical to the numerical value currently set in the variable “seqNum”.  
  
        -   An AcknowledgementNumber that is identical to the numerical value currently set in “ack”.  
  
        -   A Payload count value that is identical to the value currently set in “pyl.Count”.  
  
        -   Source and destination IP addresses that match the last segment evaluation.  
  
        > [!TIP]
        >  The line of code containing the “->” operator tells the expression to go forward evaluating messages until a match is found and to pass over all nonmatching messages.  
  
         ***Match found***  — if the SequenceNumber and AcknowledgementNumber are identical to those in the last segment evaluation, the payload count value is equal to “pyl.Count”, and the source and destination address are the same as the last segment evaluation, then the message is a TCP retransmit; in which case, the variable “mnretrans” is set to the retransmit message number which is returned by the GetMessageNumber method and passed to the virtual operation for output.  
  
    6.  ***Output***  — when two TCP messages are detected that meet the indicated criteria of this **Pattern** expression, the appropriate variable values are then abstracted to the virtual operation, which extracts the values needed for the **Pattern** expression output to appear as a **Retransmit Pair** in the Message Analyzer **Pattern Match** viewer.  
  
    7.  ***Continuing evaluations***  — the evaluation process backtracks to the next TCP message Segment that meets the indicated Payload requirements following the initial evaluation point, and the process is repeated until all messages in the input stream (the trace results) have been evaluated.  
  
-   **Three-Way Handshake** — the OPN behavior scenario that defines this **Pattern** expression is encapsulated in the following OPN code:  
  
    ```  
    using TCP;  
    using IPv4;  
    using IPv6;  
    using Utility;  
  
    // Looks for a TCP 3-way handshake with an IPv4 or IPv6 transport.    
    // Returns the approximate response time that equals the time delta  
    // between the Syn -> SynAck.  
  
    // A Virtual Operation creates special messages where properties  
    // are exposed and display as columns, and also provide a friendly  
    // description. .  
  
    virtual operation TCP3Way  
    {  
      TimeSpan AproxRTT = approxrtt != null ? approxrtt : approxrtt6;  
      (IPv4Address | IPv6Address) Source = sa != null ? sa : sa6;  
      (IPv4Address | IPv6Address) Destination = da != null ? da : da6;  
      ushort SourcePort = sp != 0 ? sp : sp6;  
      ushort DestinationPort = dp != 0 ? dp : dp6;  
      int ServerMaxSegmentSize = SrvMaxSegSize !=0 ? SrvMaxSegSize : 0;  
      int ServerScaleFactor = SrvScale !=0 ? SrvScale : 0;  
      int ServerSackPermitted = SrvSackPerm !=0 ? SrvSackPerm : 0;  
      int ClientMaxSegmentSize = CliMaxSegSize !=0 ? CliMaxSegSize : 0;  
      int ClientScaleFactor = CliScale !=0 ? CliScale : 0;  
      int ClientSackPermitted = CliSackPerm !=0 CliSackPerm : 0;  
  
       override string ToString()   
       {  
        return "TCP Session";  
       };  
    }  
    // scenario ThreeWayHandshake   
    // Note: former use of “scenario” is replaced by a virtual operation.  
  
    // Backtrack causes the sequence to start the evaluation with a TCP   
    // message that has it’s SYN flag set to True, and to always go back   
    // to evaluate the next message that has it’s SYN flag set to True,   
    // following the original evaluation. This causes all messages in   
    // the input stream (trace results) to be processed. .  
    = backtrack(Segment{Flags is TCP.Flags{SYN == true}})  
  
    // Check on IPv4 transport. .  
    (  
    // Look for TCP over IPv4 that is not adjacent in the stack; this   
    // allows for finding tunnel TCP sessions. The expression saves and   
    // remembers the Address/Port values and timestamp which is used  
    // for comparison in other parts of this expression. .  
  
      \TCP.Segment{Flags is TCP.Flags{SYN == true}, SequenceNumber is var IPv4SeqNumRequest, SourcePort is var sp,   
      DestinationPort is var dp, GetTimestamp(value) is var starttime, value.TransportKey is var transportV4,   
      GetMaxSegSize(value) is var SrvMaxSegSize, GetSackPermitted(value) is var SrvSackPerm, GetScaleFactor(value) is var SrvScale}  
      \\IPv4.Datagram{SourceAddress is var sa, DestinationAddress is var da, value.NetworkKey is var networkV4}  
      ->   
      \TCP.Segment{Flags is TCP.Flags{SYN == true, ACK==true}, SequenceNumber is var IPv4SeqNumResponse,   
      AcknowledgementNumber == IPv4SeqNumRequest + 1, SourcePort == dp, DestinationPort == sp,   
      GetTimestamp(value) - starttime is var approxrtt, value.TransportKey == transportV4, GetMaxSegSize(value) = var CliMaxSegSize,   
      GetSackPermitted(value) = var CliSackPerm, GetScaleFactor(value) = var CliScale}  
      \\IPv4.Datagram{SourceAddress.Octets == da.Octets, DestinationAddress.Octets == sa.Octets, value.NetworkKey == networkV4}  
      ->  
      \TCP.Segment{Flags is TCP.Flags{ACK==true}, SequenceNumber == IPv4SeqNumRequest + 1,   
       AcknowledgementNumber == IPv4SeqNumResponse + 1, SourcePort == sp, DestinationPort == dp, value.TransportKey == transportV4}  
      \\IPv4.Datagram{SourceAddress.Octets == sa.Octets, DestinationAddress.Octets == da.Octets, value.NetworkKey == networkV4}  
    )  
    |  
    //IPv6 transport version   
    (  
      \TCP.Segment{Flags is TCP.Flags{SYN == true}, SequenceNumber is var SeqNumRequest, SourcePort is var sp6,   
      DestinationPort is var dp6, GetTimestamp(value) is var starttime6, value.TransportKey is var transportV6}  
      \\IPv6.Datagram{SourceAddress is var sa6, DestinationAddress is var da6, value.NetworkHashCode is var networkV6}  
      ->  
      Segment{Flags is TCP.Flags{SYN == true, ACK==true}, SequenceNumber is var SeqNumResponse,  AcknowledgementNumber == SeqNumRequest + 1,   
      SourcePort == dp6, DestinationPort == sp6,  GetTimestamp(value) - starttime6 is var approxrtt6, value.TransportKey == transportV6}  
       \\IPv6.Datagram{SourceAddress.Octets == da6.Octets, DestinationAddress.Octets == sa6.Octets,  value.NetworkHashCode == networkV6}  
      ->  
      Segment{Flags is TCP.Flags{ACK==true}, SequenceNumber == SeqNumRequest + 1,  AcknowledgementNumber == SeqNumResponse + 1, SourcePort == sp6,   
      DestinationPort == dp6, value.TransportKey == transportV6}  
       \\IPv6.Datagram{SourceAddress.Octets == sa6.Octets, DestinationAddress.Octets == da6.Octets,value.NetworkHashCode == networkV6}  
    );  
  
    // Property used to retrieve the timestamp which is only at the  
    // choke point message, which is the bottom one. .  
    DateTime GetTimestamp(any message x)  
    {  
       var origins = x.Origins;  
       if (origins.Count == 0)  
         return x#Timestamp as DateTime;  
       else  
         return GetTimestamp(origins[0]);             
    }  
    // Gets the value of the MaxSegmentSize from TCP options for initial and // backtracked message comparisons. .  
    int GetMaxSegSize(TCP.Segment x)  
    {  
        if(x.Options != nothing && x.Options is array<TcpOption>){  
            array<TcpOption> opts = x.Options as array<TcpOption>;  
            foreach(TcpOption o in opts)  
            {  
                if(o is MaxSegmentSize)  
                {  
                    MaxSegmentSize mss = o as MaxSegmentSize;  
                    return mss.MaxSegmentSize;  
                }  
            }  
        }  
        return 0;  
    }  
  
    // Gets the value of WindowsScaleFactor from TCP options for initial   
    // and backtracked message comparisons. .  
    int GetScaleFactor(TCP.Segment x)  
    {  
        if(x.Options != nothing && x.Options is array<TcpOption>){  
            array<TcpOption> opts = x.Options as array<TcpOption>;  
            foreach(TcpOption o in opts)  
            {  
                if(o is TCP.WindowsScaleFactor)  
                {  
                    WindowsScaleFactor s = o as WindowsScaleFactor;  
                    return s.ShiftCount;  
                }  
            }  
        }  
        return 0;  
    }  
  
    // Checks the SackPermitted value in TCP options for initial   
    // and backtracked message comparisons. .  
    int GetSackPermitted(TCP.Segment x)  
    {  
        if(x.Options != nothing && x.Options is array<TcpOption>){  
            array<TcpOption> opts = x.Options as array<TcpOption>;  
            foreach(TcpOption o in opts)  
            {  
                if(o is TCP.SackPermitted)  
                {  
                    SackPermitted s = o as SackPermitted;  
                    return s.Length;  
                }  
            }  
        }  
        return 0;  
    }  
  
    ```  
  
     This OPN scenario finds all TCP messages that form a three-way communication pattern that is typical of setting up a TCP connection, where IPv4 or IPv6 are used as transports.  The output of this **Pattern** expression can provide an overview of TCP connections which may indicate configuration problems that are impacting performance.  
  
     For reference and convenience, a table is included ahead that shows the pattern of SYN and ACK field values and relative SequenceNumber and AcknowledgementNumber value representations to illustrate the signature of a three-way handshake pattern that successfully opened a TCP connection. To retrieve the TCP messages, this **Pattern** expression evaluates the input stream for SYN and ACK flag settings, SequenceNumbers, AcknowledgementNumbers, SourcePort, DestinationPort, round trip time, and the Source and Destination IP addresses to ensure a match.  
  
     Note that this **Pattern** expression also returns the values of various TCP fields to further enhance the analysis process, for example, the client and server **MaxSegmentSize**, **WindowsScaleFactor**, and **SackPermitted** TCP option values, which expose how these options were negotiated during the initial stages of a connection request. The values of these options are held by corresponding client and server variables, for example, the ClientScaleFactor and ServerScaleFactor vars. Note that the TCP options configuration might be the cause of TCP performance issues.  
  
    > [!NOTE]
    >  To simplify this walkthrough, only the IPv4 case is discussed, although the IPv6 case that follows the “&#124;” operator (OR) in the code is functionally similar:  
  
    ### Table 12.             TCP Handshake Connection Negotiation  
  
    |**Computer Node**|**Message Sent**|**SYN Flag Value**|**ACK Flag Value**|**SequenceNumber**|**AcknowledgementNumber**|  
    |-----------------------|----------------------|------------------------|------------------------|------------------------|-------------------------------|  
    |Sending|Connection Request|True|False|x|0|  
    |Receiving*|Request Acknowledgement|True|True|y|x+1|  
    |Sending|Sync Acknowledgement|False|True|x+1|y+1|  
  
     The **TCP Three-Way Handshake** **Pattern** expression identifies this pattern across a set of trace results and returns them first to the **MATCHES** pane of the **Pattern Match** viewer as a summary button, which in turn you must click to display the full results set in the **MATCHED INSTANCES** pane of the viewer. To accomplish this, the code uses the following processing elements and constructs:  
  
    1.  ***Virtual operation***  — following the using statements is a "virtual operation" that provides for definition of variables and exposure of properties that are used in **Pattern** expression evaluations; for example, to hold source and destination IPv4 or IPv6 address values to check for matches; a round trip time value; and to hold other TCP field values that are used in the evaluations such as SourcePort and DestinationPort. Other declarations in the virtual operation are for variables that hold the values of TCP **MaxSegmentSize**, **WindowsScaleFactor**, and **SackPermitted** options on the sending and receiving nodes. These variables correlate TCP option values in the returned **Pattern** expression results for analysis purposes.  
  
         ***Custom output message***  — as part of the virtual operation, the overridden ToString() method is used to create a custom output message, which can be based on values returned in the expression, or it can be any custom string value that you specify. The string value displays in the **Summary** column of the **Pattern Match** viewer when you click a **Matches** pane summary button after the executing **Pattern** expression completes its evaluation.  
  
    2.  ***Backtrack***  — the line of code that contains the “backtrack” statement tells the **Pattern** expression to always start with, or backtrack to, a TCP segment that has its SYN flag set to true, which is indicative of a TCP message that is requesting to open a connection on a target node.  
  
    3.  ***Segment evaluation***  — the line of code containing the first “TCP.Segment” statement looks at the first TCP message that has its SYN flag set to true, which is characteristic of a connection request from a sending node, that can be *accepted* by a receiving node. The **Pattern** expression then sets the values of the following variables for comparison with other messages:  
  
        -   “IPv4SeqNumRequest” — is set to the SequenceNumber of this initial TCP request message.  
  
        -   “sp" — is set to the SourcePort value of this message to identify the source port involved in the IP conversation where the handshake is being set up.  
  
        -   "dp" — is set to the DestinationPort value of this message to identify the destination port involved in the IP conversation where the handshake is being set up.  
  
        -   "starttime" — is set to the return value of the GetTimestamp() method. The time value in this variable is subtracted from the return value of the GetTimeStamp() method in the next TCP.Segment section to calculate the approximate round trip time that is set in the variable "approxrtt" in that section of code.  
  
        -   “transportV4” — is set to the value of the **TCP.Segment.TransportKey** field. Provides a hash constant value that is the difference between the source and destination TCP ports currently under evaluation. Provides a faster comparison of the current TCP port pair.  
  
            > [!NOTE]
            >  For further details, right-click the **TransportKey** field in **Field Chooser** **Tool Window** and select **Go To Definition** in the context menu that appears to show the OPN definition of this field. You can also add this field to the **Analysis Grid** viewer column layout to see what a typical value might look like. Also, right-click a field value and select the **Include Hex for Numeric Values** command in the context menu that appears, to view the hexadecimal value that is used as the hash constant.  
  
        -   “SrvMaxSegSize” — is set to the value of the TCP MaxSegmentSize option; the method GetMaxSegSize() is called to return the value.  
  
        -   “SrvSackPerm” — is set to the value of the TCP SackPermitted option; the method GetSackPermitted() is called to return the value.  
  
        -   “SrvScale” — is set to the value of the TCP WindowsScaleFactor option; the method GetScaleFactor() is called to return the value.  
  
        -   "sa" — is set to the IPv4 SourceAddress of this message to identify the source node that is involved in the IP conversation where the handshake is being set up.  
  
        -   "da" — is set to the IPv4 DestinationAddress of this message to identify the destination node that is involved in the IP conversation where the handshake is being set up.  
  
        -   “networkV4” — is set to the value of the **IPv4.Datagram.NetworkKey** field. Provides a hash constant value that is the difference between the source and destination IPv4 addresses under evaluation. Provides a faster comparison of the current IPv4 address pair.  
  
    4.  ***Segment evaluation***  — the line of code containing the second "TCP.Segment" section looks for the next TCP message that has both its SYN flag and ACK flag set to true, which is the signature of an acknowledgement reply *issued* by a receiving node to indicate a successful connection, that is, along with appropriate TCP SequenceNumber and AcknowledgementNumber values. This line of code also captures the SequenceNumber of this message in the ”IPv4SeqNumResponse” variable and detects whether the AcknowledgementNumber of this message is equal to the SequenceNumber of the first message sent, plus 1. This would indicate that the message is a component part of the handshake, as long as the message is in the same established IP conversation and port communication, as they would be in an associated ACK response. To verify that this is the case, the **Pattern** expression checks the values of the following variables:  
  
        -   "dp” — is checked against the current message SourcePort to see if the values are identical. Note that the source and destination ports switch for the first ACK message.  
  
        -   "sp" — is checked against the current message DestinationPort to see if the values are identical.  
  
        -   "approxrtt" — is calculated by subtracting the "starttime" value of the last "TCP.Segment" from the current return value of the GetTimeStamp() method. This value is specified in the **ApproxRTT** column of the **Pattern Match** viewer when you expand the results node after the **Pattern** expression completes its evaluation.  
  
        -   “transportV4” — is set to the value of the **TCP.Segment.TransportKey** field, as previously described.  
  
        -   “CliMaxSegSize” — is set to the value of the TCP MaxSegmentSize option; the method GetMaxSegSize() is called to return the value.  
  
        -   “CliSackPerm” — is set to the value of the TCP SackPermitted option; the method GetSackPermitted() is called to return the value.  
  
        -   “CliScale” — is set to the value of the TCP WindowsScaleFactor option; the method GetScaleFactor() is called to return the value.  
  
        -   "da.Octets" — is checked against the current message IPv4 SourceAddress.Octets value to see if the values are identical.  
  
        -   "sa.Octets" — is checked against the current IPv4 Destination Address.Octets value.  
  
        -   “networkV4” — is set to the value of the **IPv4.Datagram.NetworkKey** field, as previously described.  
  
    5.  ***Segment evaluation***  — the line of code containing the third "TCP.Segment" section looks for the next TCP message that has its ACK flag set to true, its SequenceNumber equal to the value of the first message’s SequenceNumber plus 1 (“SeqNumRequest +1”), and an AcknowledgementNumber equal to the value of the second message’s SequenceNumber plus 1 (“SeqNumResponse + 1”), while also ensuring that the message is in the same IP conversation and is using the same ports. This pattern is characteristic of a successful connection that is in turn acknowledged by the sending node that made the initial connection request, which can be *accepted* by the receiving node.  
  
    6.  ***Output***  — as these patterns are met, Message Analyzer returns the three-way handshake messages to the **Pattern Match** viewer for display. To learn more about how to display the results of executing a **Pattern** expression, see [Using the Pattern Match Viewer](using-the-pattern-match-viewer.md).  
  
    7.  ***Continuing evaluations***  — the **Pattern** expression then backtracks to the next TCP segment (where the SYN flag = true) following the initial evaluation point and the process is repeated until all messages in the input stream (trace results) have been evaluated.  
  
## Writing Pattern Expressions  
 Message Analyzer enables you to write your own **Pattern** expression in “free form”, meaning that you must develop the expression without any UI automation support such as you have from the **Quick** tab of the **Pattern Editor**. To write your own **Pattern** expression in “free form”, the **Pattern Editor** provides the features you will need. However, you will most likely need to learn more about OPN, although you can review the code descriptions provided here to help you obtain a rudimentary understanding of how the language works for building **Pattern** expressions.  
  
> [!TIP]
>  When writing **Pattern** matching scenarios, it might be helpful to make the assumption that conversations are initiated by the client (sender) and that Message Analyzer is running on the server, the (*receiving) node (see the previous table).  
  
 When writing **Pattern** matching scenarios, you can take advantage of a friendly method for creating **Patterns**, by using the **Quick** tab of the **Pattern Editor**. The simplest way to do this is to right-click a message of interest in the **Analysis Grid** viewer and select the **Create Pattern** command in the context menu that appears. This action will open the **Pattern Editor** pre-populated with information that derives from the selected message.  
  
---  
  
 **More Information**   
 **To learn more** about the **Pattern Editor**, see [Using the Pattern Editor](using-the-pattern-editor.md).   
**To learn more** about executing sequential **Pattern** expressions, see the TechNet Blog article [Sequence Match View: Identifying Interesting Network Patterns](http://blogs.technet.com/b/messageanalyzer/archive/2013/08/23/sequence-match-view-identifying-interesting-network-patterns.aspx).  
**To learn more** about OPN, see the [OPN Programming Guide](http://download.microsoft.com/download/3/E/8/3E845130-349C-4EFC-B634-C7DBD46140B7/OPN%20Programming%20Guide%20v4.4.docx).   
---