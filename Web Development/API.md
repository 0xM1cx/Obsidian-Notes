# APIs

### What is an API?

An API is a set of rules that state how applications interact. An API lets one application request data from another system.

![Untitled](APIs%20d16ef/Untitled.png)

### Why are APIs important?

An API lets one application use the capabilities of another system. This means that if you want to build and e-commerce application, you can concentrate on building only your product. You can use the API of different applications for payments, billings, authentication, etc.

### Request, Response and Resource

The three main components of an API are Request, Response, and Resource. You would make a **request** to a server. The server will return a **response** that will contain data regarding a **resource**.

### Anatomy of an API Request

| Name | Description |
| --- | --- |
| Endpoint | The URL that you request for |
| Method | The type of your request. E.g. POST, GET, PUT, UPDATE |
| Headers | Additional information for either the client or the server |
| Body | Information sent to the server |

![Untitled](APIs%20d16ef/Untitled%201.png)

Endpoint ⇒
![[APIs d16ef/Untitled 2.png]]
Method ⇒
![Untitled](APIs%20d16ef/Untitled%203.png)
Headers ⇒
![[APIs d16ef/Untitled 4.png]]
Body ⇒
![[Untitled 5.png]]



### Anatomy of an API Response

| Name | Description |
| --- | --- |
| Headers | Additional information for either the client or the server |
| Body | Data related to the resource requested from the server |

![Untitled](APIs%20d16ef/Untitled%206.png)

Headers ⇒ 

![Untitled](APIs%20d16ef/Untitled%207.png)

Body ⇒ 

![Untitled](APIs%20d16ef/Untitled%208.png)

## **What is HTTP?**

**HTTP** (or Hypertext Transfer Protocol) is a protocol generally used by web services for serving HTML documents. A client requests to a server for a resource, and the server sends a response.

## **What are the different methods of HTTP?**

HTTP has a fixed number of methods that the client can use to indicate what type of operation it wants to perform via the request. These request methods are also known as HTTP verbs.

*There are 9 HTTP methods:*

1. **GET** - This is used to request data from a server.
2. **POST** - This is used to send some data to the server.
3. **DELETE** - This method is used to delete a specified resource.
4. **PATCH** - This is often used to update on the server. The difference for this method is that this method is used to partially modify a resource.
5. **PUT** - This also often used to update on the server. This method isused to update the entire resource on the server.
6. **HEAD** - This is identical to *GET* wherein it also asks for a response, the main difference is thaht this methods does not send a response body.
7. **TRACE** - This method is designed for diagnostic purposes. If enabled, the web server will respond to requests that use the TRACE method by echoing in its response the exact request that was received.
8. **CONNECT** - This method starts a *two-way communications with the requested resource*. It can be used to open a tunnel.
9. **OPTIONS** - This method is used to describe the communication options for the target resource.

***GET, POST, PATCH, PUT and DELETE are the most popular.***


## Status Codes
When the server returns a response, a three-digit number is also sent as part of the response. This three-digit number is also known as the "*status code*".  Status codes help in identifying the type of the response:

| *Name*        | *Range of Status Codes* |
| ------------- | ----------------------- |
| Informational | 100-199                 |
| Successful    | 200-299                 |
| Redirection   | 300-399                 |
| Client Error  | 400-499                 |
| Server Error  | 500-599                        |


## What is a REST API?
A REST API is an API that follows the design principles of the REST (or REpresentational State Transfer) architecture.

REST APIs communicate via HTTP requests to perform CRUD (or Create, Read, Update, and Delete) operations.

---
## Different Types of HTTP headers
When a client requests to the server, the client can pass additional information as a part of the request via HTTP headers. As mentioned earlier, headers are case insensitive.

Headers can contain information about the type of data that the client is sending to the server. It can also contain information about authenticating a user agent with the server.

### Request Headers
In an HTTP request, [the Request headers](https://developer.mozilla.org/en-US/docs/Glossary/Request_header) pass information about the request. It contains information about the requested resource and the client making the request. A request header can contain information about the type of the request, the URL to which the request is being made, authentication details, cache policy as well as the user agent.

### Accept
The [Accept](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) HTTP header informs the server about the type of data that the client can understand. 
```
Accept: text/html
Accept: application/xhtml+xml
Accept: image/png
```

### ### Accept-Encoding
The [Accept-Encoding](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Encoding) HTTP header informs the server about the type of encoding the client is able to understand.
```
Accept-Encoding: gzip
Accept-Encoding: gzip, compress
```

### Authorization
The [Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) HTTP header is used to pass credentials which lets the server authenticate a client and provide access to protected resources.
```
Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
Authorization: Bearer eyYWxhZGRpbjpvcGVuc2VzYW1l
```