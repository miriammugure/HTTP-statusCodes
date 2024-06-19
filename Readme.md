# INFORMATIONAL RESPONSES  
 ## Prefixed with 1xx
<ol>
<li><b>100 CONTINUE</b>  

- This interim response indicates that the client should continue the request or ignore the response if the request is already finished.
<li><b>101 SWITCHING PROTOCOLS</b>  

-  This code is sent in response to an Upgrade request header from the client and indicates the protocol the server is switching to.
<li><b>102 PROCESSING (WebDAV)</b>  

-   This code indicates that the server has received and is processing the request, but no response is available yet   

<li><b>103 EARLY HINTS</b>  

-   This status code, used with the Link header, allows the user agent to preload resources or preconnect to an origin while the server prepares the response.




</ol>

# SUCCESSFUL RESPONSES
## Prefixed with 2xx
<ol>
<li><b>200 OK</b>  

-The request succeeded, meaning:


* GET: Resource fetched and sent in the message body.
 * HEAD: Headers sent without a message body.
* PUT or POST: Action result sent in the message body.
* TRACE: Message body contains the request as received.

<li><b>202 ACCEPTED</b>  

-   The request was received but not yet acted upon. It's noncommittal, used when another process or server handles the request, or for batch processing. No asynchronous response will be sent.

<li><b>201 CREATED</b>  

-   The request succeeded, and a new resource was created as a result. This is typically the response sent after POST requests, or some PUT requests.

<li><b>203 NON-AUTHORITATTIVE INFORMATION</b>  

- This code means the returned metadata is from a local or third-party copy, not the origin server. It's mainly for mirrors or backups; otherwise, use 200 OK

<li><b>204 NO CONTENT</b>  

-   There is no content to send for this request, but the headers may be useful. The user agent may update its cached headers for this resource with the new ones.

<li><b>205 RESET CONTENT</b>  

-  Tells the user agent to reset the document which sent this request.

<li><b>206 PARTIAL CONTENT</b>  

-   This response code is used when the Range header is sent from the client to request only part of a resource.

<li><b>207 MULTI-STATUS WebDAV</b>  

-   Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

<li><b>208 ALREADY REPORTED WebDAV</b>  

-   Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

<li><b>IM Used (HTTP DELTA ENCODING)</b>  

-   The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

</ol>
# REDIRECTION MESSAGES  
## Prefixed with 3xx
<ol>
<li><b>300 MULTIPLE CHOICES</b>  

- The request has more than one possible response. The user agent or user should choose one of them. (There is no standardized way of choosing one of the responses, but HTML links to the possibilities are recommended so the user can pick.)

<li><b>301 MOVED PERMANENTLY</b>  

- The URL of the requested resource has been changed permanently. The new URL is given in the response.

<li><b>302 FOUND</b>  

- This response code means that the URI of the requested resource has been changed temporarily. Further changes in the URI might be made in the future. Therefore, this same URI should be used by the client in future requests.

<li><b>303 SEE OTHER</b>  

- The server sent this response to direct the client to get the requested resource at another URI with a GET request.

<li><b>304 NOT MODIFIED</b>  

- This is used for caching purposes. It tells the client that the response has not been modified, so the client can continue to use the same cached version of the response.

<li><b>305 USE PROXY Deprecated</b>  

- Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. It has been deprecated due to security concerns regarding in-band configuration of a proxy.

<li><b>306 UNUSED</b>  

- This response code is no longer used; it is just reserved. It was used in a previous version of the HTTP/1.1 specification.

<li><b>307 TEMPORARY REDIRECT</b>  

- The server sends this response to direct the client to get the requested resource at another URI with the same method that was used in the prior request. This has the same semantics as the 302 Found HTTP response code, with the exception that the user agent must not change the HTTP method used: if a POST was used in the first request, a POST must be used in the second request.

<li><b>308 PERMANENT REDIRECT</b>  

- This means that the resource is now permanently located at another URI, specified by the Location: HTTP Response header. This has the same semantics as the 301 Moved Permanently HTTP response code, with the exception that the user agent must not change the HTTP method used: if a POST was used in the first request, a POST must be used in the second request.
</ol>

# CLIENT ERROR RESPONSES  
## Prefixed with 4xx
<ol>
<li><b>400 BAD REQUEST</b>  

- The server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing).

<li><b>401 UNAUTHORIZED</b>  

- Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response.

<li><b>402 PAYMENT REQUIRED Experimental</b>  

- This response code is reserved for future use. The initial aim for creating this code was using it for digital payment systems, however this status code is used very rarely and no standard convention exists.

<li><b>403 FORBIDDEN</b>  

- The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401 Unauthorized, the client's identity is known to the server.

<li><b>404 NOT FOUND</b>  

- The server cannot find the requested resource. In the browser, this means the URL is not recognized. In an API, this can also mean that the endpoint is valid but the resource itself does not exist. Servers may also send this response instead of 403 Forbidden to hide the existence of a resource from an unauthorized client. This response code is probably the most well-known due to its frequent occurrence on the web.

<li><b>405 METHOD NOT ALLOWED</b>  

- The request method is known by the server but is not supported by the target resource. For example, an API may not allow calling DELETE to remove a resource.

<li><b>406 NOT ACCEPTABLE</b>  

- This response is sent when the web server, after performing server-driven content negotiation, doesn't find any content that conforms to the criteria given by the user agent.

<li><b>407 PROXY AUTHENTICATION REQUIRED</b>  

- This is similar to 401 Unauthorized but authentication is needed to be done by a proxy.

<li><b>408 REQUEST TIMEOUT</b>  

- This response is sent on an idle connection by some servers, even without any previous request by the client. It means that the server would like to shut down this unused connection. This response is used much more since some browsers, like Chrome, Firefox 27+, or IE9, use HTTP pre-connection mechanisms to speed up surfing. Also note that some servers merely shut down the connection without sending this message.

<li><b>409 CONFLICT</b>  

- This response is sent when a request conflicts with the current state of the server.

<li><b>410 GONE</b>  

- This response is sent when the requested content has been permanently deleted from the server, with no forwarding address. Clients are expected to remove their caches and links to the resource. The HTTP specification intends this status code to be used for "limited-time, promotional services". APIs should not feel compelled to indicate resources that have been deleted with this status code.

<li><b>411 LENGTH REQUIRED</b>  

- Server rejected the request because the Content-Length header field is not defined and the server requires it.

<li><b>412 PRECONDITION FAILED</b>  

- The client has indicated preconditions in its headers which the server does not meet.

<li><b>413 PAYLOAD TOO LARGE</b>  

- Request entity is larger than limits defined by server. The server might close the connection or return a Retry-After header field.

<li><b>414 URI TOO LONG</b>  

- The URI requested by the client is longer than the server is willing to interpret.

<li><b>415 UNSUPPORTED MEDIA TYPE</b>  

- The media format of the requested data is not supported by the server, so the server is rejecting the request.

<li><b>416 RANGE NOT SATISFIABLE</b>  

- The range specified by the Range header field in the request cannot be fulfilled. It's possible that the range is outside the size of the target URI's data.
<li><b>417 EXPECTATION FAILED</b>  

- This response code means the expectation indicated by the Expect request header field cannot be met by the server.

<li><b>418 I'M A TEAPOT</b>  

- The server refuses the attempt to brew coffee with a teapot.

<li><b>421 MISDIRECTED REQUEST</b>  

- The request was directed at a server that is not able to produce a response. This can be sent by a server that is not configured to produce responses for the combination of scheme and authority that are included in the request URI.

<li><b>422 UNPROCESSABLE CONTENT (WebDAV)</b>  

- The request was well-formed but was unable to be followed due to semantic errors.

<li><b>423 LOCKED (WebDAV)</b>  

- The resource that is being accessed is locked.

<li><b>424 FAILED DEPENDENCY (WebDAV)</b>  

- The request failed due to failure of a previous request.

<li><b>425 TOO EARLY (Experimental)</b>  

- Indicates that the server is unwilling to risk processing a request that might be replayed.

<li><b>426 UPGRADE REQUIRED</b>  

- The server refuses to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol. The server sends an Upgrade header in a 426 response to indicate the required protocol(s).

<li><b>428 PRECONDITION REQUIRED</b>  

- The origin server requires the request to be conditional. This response is intended to prevent the 'lost update' problem, where a client GETs a resource's state, modifies it and PUTs it back to the server, when meanwhile a third party has modified the state on the server, leading to a conflict.

<li><b>429 TOO MANY REQUESTS</b>  

- The user has sent too many requests in a given amount of time ("rate limiting").

<li><b>431 REQUEST HEADER FIELDS TOO LARGE</b>  

- The server is unwilling to process the request because its header fields are too large. The request may be resubmitted after reducing the size of the request header fields.

<li><b>451 UNAVAILABLE FOR LEGAL REASONS</b>  

- The user agent requested a resource that cannot legally be provided, such as a web page censored by a government.
</ol>

# SERVER ERROR RESPONSES
## Prefixed with 5xx
<ol>
<li><b>500 INTERNAL SERVER ERROR</b>  

- The server has encountered a situation it does not know how to handle.

<li><b>501 NOT IMPLEMENTED</b>  

- The request method is not supported by the server and cannot be handled. The only methods that servers are required to support (and therefore that must not return this code) are GET and HEAD.

<li><b>502 BAD GATEWAY</b>  

- This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response.

<li><b>503 SERVICE UNAVAILABLE</b>  

- The server is not ready to handle the request. Common causes are a server that is down for maintenance or that is overloaded. Note that together with this response, a user-friendly page explaining the problem should be sent. This response should be used for temporary conditions and the Retry-After HTTP header should, if possible, contain the estimated time before the recovery of the service. The webmaster must also take care about the caching-related headers that are sent along with this response, as these temporary condition responses should usually not be cached.

<li><b>504 GATEWAY TIMEOUT</b>  

- This error response is given when the server is acting as a gateway and cannot get a response in time.

<li><b>505 HTTP VERSION NOT SUPPORTED</b>  

- The HTTP version used in the request is not supported by the server.

<li><b>506 VARIANT ALSO NEGOTIATES</b>  

- The server has an internal configuration error: the chosen variant resource is configured to engage in transparent content negotiation itself, and is therefore not a proper end point in the negotiation process.

<li><b>507 INSUFFICIENT STORAGE (WebDAV)</b>  

- The method could not be performed on the resource because the server is unable to store the representation needed to successfully complete the request.

<li><b>508 LOOP DETECTED (WebDAV)</b>  

- The server detected an infinite loop while processing the request.

<li><b>510 NOT EXTENDED</b>  

- Further extensions to the request are required for the server to fulfill it.

<li><b>511 NETWORK AUTHENTICATION REQUIRED</b>  

- Indicates that the client needs to authenticate to gain network access.

</ol>