---
title: "Addendum 2: HTTP Status Codes | Microsoft Docs"
ms.custom: ""
ms.date: "10/26/2016"
ms.prod: "windows-server-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "networking"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 594bd932-2dab-4d91-8c10-5054c55923de
caps.latest.revision: 23
author: "greggigwg"
ms.author: "greggill"
manager: "ronstarr"
---
# Addendum 2: HTTP Status Codes
This section contains reference information for the HTTP protocol that you can use to troubleshoot HTTP messages with Message Analyzer.  
  
## HTTP Status Codes  
 The table that follows describes common HTTP client and server **StatusCodes** and associated **ReasonPhrases** that can be returned from HTTP message exchanges between client browsers and web servers. Definitions for these codes and phrases are widely known to most networking audiences; however, they are reproduced here for user convenience, to provide the benefit of having this information readily available when performing various procedures in this documentation.  
  
### Table A1. HTTP StatusCode and ReasonPhrase Definitions  
  
|StatusCode|ReasonPhrase|Definition|  
|----------------|------------------|----------------|  
|**Common Client Errors**|||  
|400|Bad Request|Indicates a syntax error in the request, which is therefore denied. This is basically an error message from the web server indicating that the web browser incorrectly attempted to access a resource or the request was corrupted.|  
|401|Authorization Required|Indicates that the request header did not contain the necessary authentication codes and therefore the requesting client is denied access. This error usually occurs when a website visitor attempts to access a restricted webpage but does not have authorization to do so, often because of a login failure.|  
|403|Forbidden|Can indicate that a client is not permitted to view a particular file or has attempted to access a forbidden directory. This StatusCode is also returned when the web server is unable to accommodate more visitors. Note that this error is similar to the 401 authentication error, although in the case of the 403 error, there was no login opportunity available.|  
|404|Not Found|Indicates that a requested resource was not found on the server, typically because it does not exist. This error can also be caused by the invalid spelling of a URL, a broken link, or the resource was moved to another location.|  
|405|Method Not Allowed|Indicates that the method being used by a requestor to access a resource is not permitted.|  
|406|Not Acceptable|Indicates that the requested resource exists but cannot be returned to the client system because of an incompatible format.|  
|407|Proxy Authentication Required|Indicates that the request must be authorized before proceeding any further.|  
|408|Request Timed Out|Often the result of heavy network traffic, which could indicate that a web server is overburdened.|  
|409|Conflicting Request|Might be that there are too many concurrent requests for a resource, which can be indicative of the inability of a server to handle the amount of requests it is receiving.|  
|410|Gone|Indicates that a resource previously existed in a particular location, but is no longer present there.|  
|411|Content Length Required|Indicates that the request is missing the required Content-Length header.|  
|412|Precondition Failed|Indicates that the client does not have the required configuration set up for a resource to be delivered by the web server.|  
|413|Request Entity Too Long|Indicates that the requested resource is too large to process.|  
|414|Request URI Too Long|Indicates that the entered URI address is too long for the server.|  
|415|Unsupported Media Type|Indicates that the file type specified in the request is unsupported.|  
|**Common Server Errors**|||  
|500|Internal Server Error|Could indicate an overloaded web server that cannot properly handle the requests it is receiving.|  
|501|Not Implemented|Indicates that the request cannot be performed by the web server.|  
|502|Bad Gateway|This error usually indicates one or more of the following:<br /><br /> - Improperly configured proxy servers.<br /><br /> - Faulty IP communication between back-end computer nodes.<br /><br /> - The client’s ISP is overloaded.<br /><br /> - A firewall is improperly functioning.<br /><br /> Typically can be resolved by clearing the client cache to force a different proxy server into use to resolve the web server content.|  
|503|Service Unavailable|Indicates that the requested service, file, or resource is currently unavailable.|  
|504|Gateway Timeout|Indicates that the server gateway has timed out, which could indicate that one or more servers are over-burdened by heavy network traffic. Time-outs can occur when a server in a chain of servers does not receive a timely response from another server, indicating slow communication between upstream computers.|  
|505|HTTP Version Not Supported|Indicates that the server does not support the HTTP version in use for the client request.|