#  HTTP response status codes

HTTP response status codes are three-digit numbers that indicate the outcome of an HTTP request made by a client (usually a web browser) to a server. These codes are categorized into five classes based on the type of response.Responses are grouped in five classes:

**1.Informational responses (100 – 199)**

**2.Successful responses (200 – 299)**

**3.Redirection messages (300 – 399)**

**4.Client error responses (400 – 499)**

**5.Server error responses (500 – 599)**

## 1.Informational responses (100 – 199)
### 100 continue
 Indicates that the initial part of a client's request is valid, allowing the client to proceed with sending the request body. This is particularly useful for large uploads to prevent sending the entire payload if the server might reject it based on headers.

### 101 Switching Protocols
Sent in response to a client's Upgrade request, indicating that the server is switching to a different protocol (like WebSocket) as requested. This confirms the change and allows communication to continue using the new protocol.

### 102 Processing
Used in WebDAV to indicate that the server has received a request and is processing it, but no final response is available yet. This helps prevent client timeouts during long-running operations.

### 103 Early Hints
Allows the server to send preliminary response headers before the final response, optimizing loading performance. It helps improve webpage loading by enabling clients to preload resources while the server is still processing the main response.

## 2. Successful responses (200 – 299)
### 200 OK
The request succeeded. The result and meaning of "success" depends on the HTTP method:

**GET:** The resource has been fetched and transmitted in the message body.

**HEAD:** Representation headers are included in the response without any message body.

**PUT or POST:** The resource describing the result of the action is transmitted in the message body.

**TRACE:** The message body contains the request as received by the server.

### 201 Created
The request succeeded, and a new resource was created as a result. This is typically the response sent after POST requests, or some PUT requests.

### 202 Accepted
The request has been received but not yet acted upon. It is noncommittal, since there is no way in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended for cases where another process or server handles the request, or for batch processing.

### 203 Non-Authoritative Information
This response code means the returned metadata is not exactly the same as is available from the origin server, but is collected from a local or a third-party copy. This is mostly used for mirrors or backups of another resource. Except for that specific case, the 200 OK response is preferred to this status.

### 204 No Content
There is no content to send for this request, but the headers are useful. The user agent may update its cached headers for this resource with the new ones.

### 205 Reset Content
Tells the user agent to reset the document which sent this request.

### 206 Partial Content
This response code is used in response to a range request when the client has requested a part or parts of a resource.

### 207 Multi-Status (WebDAV)
Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

### 208 Already Reported (WebDAV)
Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

### 226 IM Used (HTTP Delta encoding)
The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

## 3.Redirection messages (300 – 399)
### 300 Multiple Choices: 
Indicates that the request has multiple possible responses. The client must choose one, but there's no standardized method for automatic selection, making it rarely used.

### 301 Moved Permanently:
 The requested resource's URL has permanently changed, and the new URL is provided in the response.

### 302 Found:
 The resource's URI has temporarily changed. The client should continue using the original URI for future requests.

### 303 See Other:
 The server directs the client to retrieve the requested resource at a different URI using a GET request.

### 304 Not Modified:
 Used for caching. It informs the client that the response hasn't changed, so the cached version can still be used.

### 305 Use Proxy Deprecated:
 Previously indicated that the resource must be accessed through a proxy, but it's now deprecated due to security concerns.

### 306 Unused:
 A reserved response code that is no longer in use.

### 307 Temporary Redirect:
 Directs the client to another URI using the same HTTP method as the original request (e.g., if the original request was a POST, the redirected request must also be a POST).

### 308 Permanent Redirect:
 Indicates that the resource is permanently located at another URI, specified in the Location header, and retains the same method used in the original request.

 ## 4.Client error responses (400 – 499)
 ### 400 Bad Request
The server cannot process the request due to a client error, such as malformed syntax or invalid request framing.

### 401 Unauthorized
Indicates that the client must authenticate itself to access the requested resource. It implies the client is unauthenticated.

### 402 Payment Required
Initially intended for digital payment systems, this code is rarely used, and no standard convention exists for its implementation.

### 403 Forbidden
The server refuses to fulfill the request because the client does not have access rights, even though the client is authenticated.

### 404 Not Found
The server cannot find the requested resource, which may indicate an unrecognized URL or a valid endpoint that does not exist.

### 405 Method Not Allowed
The request method is recognized by the server but is not supported for the targeted resource.

### 406 Not Acceptable
The server cannot find content that matches the criteria specified by the user agent after performing content negotiation.

### 407 Proxy Authentication Required
Similar to 401 Unauthorized, but authentication must be performed through a proxy.

### 408 Request Timeout
Indicates that the server is shutting down an idle connection, typically due to a lack of requests from the client.

### 409 Conflict
Sent when a request conflicts with the current state of the server, often used in WebDAV for error resolution.

### 410 Gone
Indicates that the requested content has been permanently deleted, and clients should remove their references to it.

### 411 Length Required
The server requires a Content-Length header field but it is missing from the request.

### 412 Precondition Failed
Occurs when the server cannot meet the preconditions specified by the client in its headers.

### 413 Content Too Large
The request body exceeds the limits set by the server, which may result in a closed connection or a Retry-After header.

### 414 URI Too Long
The requested URI is longer than the server is willing to process.

### 415 Unsupported Media Type
The media format of the request is not supported by the server, leading to rejection.

### 416 Range Not Satisfiable
The requested range specified in the Range header cannot be fulfilled, possibly exceeding the size of the resource.

### 417 Expectation Failed
The server cannot meet the expectations specified by the Expect request header.

### 418 I'm a teapot
A humorous response indicating that the server refuses to brew coffee with a teapot.

### 421 Misdirected Request
The request was sent to a server that cannot produce a response for the specified combination of scheme and authority.

### 422 Unprocessable Content (WebDAV)
The request is well-formed but cannot be fulfilled due to semantic errors.

### 423 Locked (WebDAV)
Indicates that the resource being accessed is locked.

### 424 Failed Dependency (WebDAV)
The request failed due to the failure of a previous request.

### 425 Too Early Experimental
The server is unwilling to process a request that might be replayed.

### 426 Upgrade Required
The server requires the client to upgrade to a different protocol to fulfill the request.

### 428 Precondition Required
Indicates that the request must be conditional to prevent the 'lost update' problem.

### 429 Too Many Requests
The user has sent too many requests in a short period, leading to rate limiting.

### 431 Request Header Fields Too Large
The server is unable to process the request due to excessively large header fields.

### 451 Unavailable For Legal Reasons
The requested resource cannot be legally provided, such as a web page censored by a government.

 ## 5.Server error responses (500 – 599)
 ### 500 Internal Server Error:
  A general error when the server encounters an unexpected situation and doesn't have a more specific status code to respond with. It covers all server-side issues that can't be categorized elsewhere.

### 501 Not Implemented: 
The server doesn't support the functionality needed to fulfill the request method. Typically, this is returned when the server cannot handle a method that is not required (e.g., DELETE, PATCH), but it must support GET and HEAD.

### 502 Bad Gateway: 
The server, acting as a gateway or proxy, received an invalid response from the upstream server it accessed to fulfill the request. It could result from misconfigurations or issues between servers.

### 503 Service Unavailable:
 The server is temporarily unable to handle the request, often due to overload or maintenance. The server may include a "Retry-After" header to suggest when the service will be available again.

### 504 Gateway Timeout: 
This error occurs when a server acting as a gateway or proxy doesn’t receive a timely response from an upstream server it needs to access to complete the request.

### 505 HTTP Version Not Supported: 
The server does not support the HTTP protocol version that the client used in the request, indicating a mismatch between client and server capabilities.

### 506 Variant Also Negotiates: 
A configuration issue occurs when the server attempts to engage in content negotiation, and the selected variant itself is configured to negotiate, causing a circular reference.

### 507 Insufficient Storage (WebDAV): 
The server cannot store the representation needed to complete the request, typically due to insufficient storage resources on the server side.

### 508 Loop Detected (WebDAV):
 The server has encountered an infinite loop during the processing of the request, usually within a WebDAV context where recursive processing has gone unchecked.

### 510 Not Extended: 
The client made a request that requires further extensions to be supported by the server, but those extensions are not implemented.

### 511 Network Authentication Required: 
The client must authenticate to gain network access, often seen when trying to access restricted networks, such as captive portals that require users to log in first.



