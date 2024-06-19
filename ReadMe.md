<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [RESPONSE STATUS CODES](#response-status-codes)
  - [Information Responses](#information-responses)
      - [100 Continue](#100-continue)
      - [101 Switching Protocols](#101-switching-protocols)
      - [102 Processing (WebDAV)](#102-processing-webdav)
      - [103 Early Hints](#103-early-hints)
  - [Successful Responses](#successful-responses)
      - [200 OK](#200-ok)
      - [202 Accepted](#202-accepted)
      - [203 Non-Authoritative Information](#203-non-authoritative-information)
      - [204 No Content](#204-no-content)
      - [205 Reset Content](#205-reset-content)
      - [206 Partial Content](#206-partial-content)
      - [208 Already Reported (WebDAV)](#208-already-reported-webdav)
      - [226 IM Used (HTTP Delta encoding)](#226-im-used-http-delta-encoding)
  - [Redirection Messages](#redirection-messages)
      - [300 Multiple Choices](#300-multiple-choices)
      - [301 Moved Permanently](#301-moved-permanently)
      - [302 Found](#302-found)
      - [303 See Other](#303-see-other)
      - [304 Not Modified](#304-not-modified)
      - [305 Use Proxy Deprecated](#305-use-proxy-deprecated)
      - [306 unused](#306-unused)
      - [307 Temporary Redirect](#307-temporary-redirect)
      - [308 Permanent Redirect](#308-permanent-redirect)
  - [Client error responses](#client-error-responses)
      - [400 Bad Request](#400-bad-request)
      - [401 Unauthorized](#401-unauthorized)
      - [402 Payment Required Experimental](#402-payment-required-experimental)
      - [403 Forbidden](#403-forbidden)
      - [404 Not Found](#404-not-found)
      - [405 Method Not Allowed](#405-method-not-allowed)
      - [406 Not Acceptable](#406-not-acceptable)
      - [407 Proxy Authentication Required](#407-proxy-authentication-required)
      - [408 Request Timeout](#408-request-timeout)
      - [409 Conflict](#409-conflict)
      - [410 Gone](#410-gone)
      - [411 Length Required](#411-length-required)
      - [412 Precondition Failed](#412-precondition-failed)
      - [413 Payload Too Large](#413-payload-too-large)
      - [414 URI Too Long](#414-uri-too-long)
      - [415 Unsupported Media Type](#415-unsupported-media-type)
      - [416 Range Not Satisfiable](#416-range-not-satisfiable)
      - [417 Expectation Failed](#417-expectation-failed)
      - [418 I'm a teapot](#418-im-a-teapot)
      - [421 Misdirected Request](#421-misdirected-request)
      - [422 Unprocessable Content (WebDAV)](#422-unprocessable-content-webdav)
      - [423 Locked (WebDAV)](#423-locked-webdav)
      - [424 Failed Dependency (WebDAV)](#424-failed-dependency-webdav)
      - [425 Too Early Experimental](#425-too-early-experimental)
      - [426 Upgrade Required](#426-upgrade-required)
      - [428 Precondition Required](#428-precondition-required)
      - [429 Too Many Requests](#429-too-many-requests)
      - [431 Request Header Fields Too Large](#431-request-header-fields-too-large)
      - [451 Unavailable For Legal Reasons](#451-unavailable-for-legal-reasons)
  - [Server error responses](#server-error-responses)
      - [500 Internal Server Error](#500-internal-server-error)
      - [501 Not Implemented](#501-not-implemented)
      - [502 Bad Gateway](#502-bad-gateway)
      - [503 Service Unavailable](#503-service-unavailable)
      - [504 Gateway Timeout](#504-gateway-timeout)
      - [505 HTTP Version Not Supported](#505-http-version-not-supported)
      - [506 Variant Also Negotiates](#506-variant-also-negotiates)
      - [507 Insufficient Storage (WebDAV)](#507-insufficient-storage-webdav)
      - [508 Loop Detected (WebDAV)](#508-loop-detected-webdav)
      - [510 Not Extended](#510-not-extended)
      - [511 Network Authentication Required](#511-network-authentication-required)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# RESPONSE STATUS CODES

-Indicates whether a specific HTTP request has been successfully completed.  
-Responses are grouped in five classes:

## Information Responses

#### 100 Continue

-Indicates that the client should <ins>continue the request</ins> or ignore the response if the request is already finished.

#### 101 Switching Protocols

-Sent in response to an Upgrade request header from the client  
-Indicates the <ins>protocol the server is switching to.</ins>

#### 102 Processing (WebDAV)

-Indicates that the server has received and is processing the request, <ins>but no response is available yet.</ins>

#### 103 Early Hints
-primarily intended to be used with the Link header, letting the user agent start preloading resources while the server prepares a response or preconnect to an origin from which the page will need resources.

## Successful Responses

#### 200 OK
-Request succeeded.  
-The result meaning of "success" depends on the HTTP method.  
 
 * **GET:** The resource has been <ins>fetched and transmitted</ins> in the message body.  
* **HEAD:** The representation <ins>headers are included in the response without any message body.</ins>  
* **PUT** or **POST:** The resource describing the result of the action is transmitted in the message body.   
* **TRACE:** The message body contains the request message as received by the server.

#### 202 Accepted 
-Request has been received but not yet acted upon.  
-Intended for cases where another process or server handles the request

#### 203 Non-Authoritative Information  
-Means the returned metadata is not exactly the same as is available from the origin server, but is collected from a local or a third-party copy.

#### 204 No Content
-There is no content to send for this request, but the headers may be useful.

#### 205 Reset Content 
-Tells the user agent to reset the document which sent this request.

#### 206 Partial Content  
-Used when the Range header is sent from the client to request only part of a resource.

#### 208 Already Reported (WebDAV) 
-Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

#### 226 IM Used (HTTP Delta encoding) 
-The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.


## Redirection Messages
#### 300 Multiple Choices 
-Request has more than one possible response and the user agent or user should choose one of them.

#### 301 Moved Permanently 
-The URL of the requested resource has been changed permanently and the new URL is given in the response.

#### 302 Found  
-The URI of requested resource has been changed temporarily.  
-Further changes might be made in the future.

#### 303 See Other
-The server sent this response to direct the client to get the requested resource at another URI with a GET request.
 
#### 304 Not Modified  
-Used for caching purposes  
-Tells the client that the response has not been modified, so the client can continue to use the same cached version of the response.

####  305 Use Proxy Deprecated  
-Indicate that a requested response <ins>must</ins> be accessed by a proxy.   
-It has been deprecated due to security concerns regarding in-band configuration of a proxy.

#### 306 unused 
-This response code is no longer used; it is just reserved.

#### 307 Temporary Redirect  
-The server sends this response to direct the client to get the requested resource at another URI with the same method that was used in the prior request.  

#### 308 Permanent Redirect  
-Resource is now permanently located at another URI, specified by the Location.  
-If a POST was used in the first request, a POST must be used in the second request.

the second request.

## Client error responses
#### 400 Bad Request  
The server cannot or will not process the request due to something that is perceived to be a client error   

#### 401 Unauthorized 
-The client must authenticate itself to get the requested response.    

#### 402 Payment Required Experimental  
-Reserved for future use  
 -Initial aim for creating this code was using it for digital   payment systems, however this status code is used very rarely and no standard convention exists.

#### 403 Forbidden  
 -The client does not have access rights to the content therefore, the server refuses to give the requested resource. 

#### 404 Not Found  
 The server cannot find the requested resource.
 URL is not recognized    

#### 405 Method Not Allowed  
-Request method is known by the server but is not supported by the target resource  

#### 406 Not Acceptable  
-This response is sent when the web server, after performing server-driven content negotiation and it doesn't find any content that conforms to the criteria given by the user agent.  

#### 407 Proxy Authentication Required 
authentication is needed to be done by a proxy. 

#### 408 Request Timeout  
-server would like to shut down this unused connection.   

#### 409 Conflict  
-This response is sent when a request conflicts with the current state of the serve

#### 410 Gone 
-This response is sent when the requested content has been permanently deleted from server, with no forwarding address.

#### 411 Length Required
-Server rejected the request because the Content-Length header field is not defined and the server requires it.

#### 412 Precondition Failed
The client has indicated preconditions in its headers which the server does not.

#### 413 Payload Too Large
-Request entity is larger than limits defined by server. 

#### 414 URI Too Long
The URI requested by the client is longer than the server is willing to interpret.

#### 415 Unsupported Media Type
-The media format of the requested data is not supported by the server, 

#### 416 Range Not Satisfiable
The range specified by the Range header field in the request cannot be fulfilled. 

#### 417 Expectation Failed
-This response code means the expectation indicated by the Expect request header field cannot be met by the server.

#### 418 I'm a teapot
-The server refuses the attempt to brew coffee with a teapot.

#### 421 Misdirected Request
-The request was directed at a server that is not able to produce a response.

#### 422 Unprocessable Content (WebDAV)
-The request was well-formed but was unable to be followed due to semantic errors.

#### 423 Locked (WebDAV)
-The resource that is being accessed is locked.

#### 424 Failed Dependency (WebDAV)
The request failed due to failure of a previous request.

#### 425 Too Early Experimental
Indicates that the server is unwilling to risk processing a request that might be replayed.

#### 426 Upgrade Required
-The server refuses to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol

#### 428 Precondition Required
-The origin server requires the request to be conditional. 

#### 429 Too Many Requests
-The user has sent too many requests in a given amount of time ("rate limiting").

#### 431 Request Header Fields Too Large
-The server is unwilling to process the request because its header fields are too large.

#### 451 Unavailable For Legal Reasons
-The user agent requested a resource that cannot legally be provided, such as a web page censored by a government.

## Server error responses
#### 500 Internal Server Error
-The server has encountered a situation it does not know how to handle.

#### 501 Not Implemented
-The request method is not supported by the server and cannot be handled.

#### 502 Bad Gateway
-This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response.

#### 503 Service Unavailable
-The server is not ready to handle the request. Common causes are a server that is down for maintenance or that is overloaded. 

#### 504 Gateway Timeout
-This error response is given when the server is acting as a gateway and cannot get a response in time.

#### 505 HTTP Version Not Supported
-The HTTP version used in the request is not supported by the server.

#### 506 Variant Also Negotiates
The server has an internal configuration error: the chosen variant resource is configured to engage in transparent content negotiation itself, and is therefore not a proper end point in the negotiation process.

#### 507 Insufficient Storage (WebDAV)
-The method could not be performed on the resource because the server is unable to store the representation needed to successfully complete the request.

#### 508 Loop Detected (WebDAV)
-The server detected an infinite loop while processing the request.

#### 510 Not Extended
-Further extensions to the request are required for the server to fulfill it.

#### 511 Network Authentication Required
-Indicates that the client needs to authenticate to gain network access.