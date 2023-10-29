```toc
```
- A **Uniform Resource Locator** is a instruction in order to locate a specific resource. 
![[34ad66d8b90aaaa35f9536d3b152ea97.png]]

Not everything shown in the above figure is used in every request. 

- **Scheme** - This instructs on what protocol to use for accessing the resource such as HTTP(S) or FTP.
- **User** - Some services require authentication to log in, you can put a username and password into the URL to log in.
- **Host** - The domain name or IP address of the server you wish to access.
- **Port** - The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS in web. But this can be hosted on any port between 1 - 65535.
- **Path** - The file name or location of the resource you are trying to access.
- **Query String** - Extra bits of information that can be sent to the requested path. For example, blog?**id=1** would tell the blog path that you with to receive the article with the id of *1*.
- **Fragment** - This is a reference to a location on the actual page requestion. This is common for long content sites, this can be used so that the user will automatically view the part of the page he has accessed. 


## HTTP Methods
- **GET** - is used for getting information from a web sever
- **POST** - is used for submitting data to the web server and potentially creating new records
- **PUT**  - is used for submitting data to a web server to update information
- **DELETE** - is used for deleting information/records from a web server

## HTTP Status Codes

| Status Code Range            | Description                                                                                                                                                                               |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 100-199 Information Response | These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of the their request. These codes are no longer very common |
| 200-299 Success              | This range of status codes is used to tell the client their request was                                                                                                                   |
| 300-399 Redirection          | These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether                                          |
| 400-499 Client Errors        | Used to inform the client that there was an error in their request                                                                                                                        |
| 500-599 Server Errors        | Reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.                                                                                                                                                                                           |

#### Common HTTP Status Codes:
| Status Code                | Description                                                                                                                                                                                  | 
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | 
| 200 OK                     | The request was completed successfully                                                                                                                                                       |
| 201 Created                | A resource has been created (for example, new user or blog post)                                                                                                                             |
| 301 Moved Permanently      | This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead                                                |
| 302 Found                  | Similar to 301 but this is only a temporary change and it may change again in the near future.                                                                                               |
| 400 Bad Request            | This tells the browser that something was either wrong or missing in their request. This can also be used if the client didn't include something in the parameters that the web server needs |
| 401 Not Authorized         | You are not currently allowed to access this resource until you have been authorized by the Web Application, commonly with a username and password                                           |
| 403 Forbidden              | You do not have permission to view this resource even when authorized.                                                                                                                       |
| 405 Method Not Allowed     | The resource does not allow this method request, for example, you send a GET request to the resource /create-repository with expects a POST request method.                                  |
| 404 Page Not Found         | The page/resource you requested does not exist                                                                                                                                               |
| 500 Internal Service Error | The server has encountered some kind of error with your request that it doesn't know how to handle properly.                                                                                 |   
| 503 Service Unavailable    | This server cannot handle your request as it's either overloaded or down for maintenance.                                                   


## Common Request Headers
- **Host** - Some webserver host multiple websites so by providing the host headers you can tell it which one you require. Otherwise, you'll just receive the default website for the server
- **User-Agent** - This is your browser and version number
- **Content-Length** - Web server sends how much data to expect in the web request. To ensure that data isn't missing.
- **Accept-Encoding** - Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet. 
- **Cookie** - Data sent to the server to help remember your information. 

## Common Response Headers
- **Set-Cookie** - Information to store which gets sent back to the webserver on each request. 
- **Cache-Control** - How long to store the content of the response in the browser's cache before it requests it again.
- **Content-Type** - Tells the client what type of data is being returned.
- **Content-Encoding** - What method of compression has been used. 