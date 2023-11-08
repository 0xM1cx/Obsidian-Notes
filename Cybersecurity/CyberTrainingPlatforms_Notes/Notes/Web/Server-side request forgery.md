**SSRF** is a web security vulnerability that allows an attacker to cause the server-side application to make requests to an unintended location.

In a typical SSRF attack, the attacker might cause the server to make a connection to internal-only services within the organization's infrastructure. In other cases, they may be able to force the server to connect to arbitrary external systems. This could leak sensitive data, such as authorization credentials.

## SSRF attack against the server
In an SSRF attack against the server, the attacker causes the application to make an HTTP request back to the server that is hosting the application, via its loopback network interface. This typically involves supplying a URL with a hostname like `127.0.0.1` or `localhost`(a commonly used name for the same adapted)

Example, when a user wants to view if a certain product is in stock at a certain store; to provide the stock information, the application must query various back-end REST APIs. It does this by passing the URL to the relevant back-end API endpoint via a front-ed HTTP request. When a user views the stock status for an item, their browser makes the following request:
```http
POST /product/stock HTTP/1.0 
Content-Type: application/x-www-form-urlencoded 
Content-Length: 118 

stockApi=http://stock.weliketoshop.net:8080/product/stock/check%3FproductId%3D6%26storeId%3D1
```
 
This causes the server to make a request to the specified URL, retrieve the stock status, and return this to the user. In the example below, an attack can modify the request to specify a URL local to the server:
```http
POST /product/stock HTTP/1.0
Content-Type: application/x-www-form-urlencoded
Content-Length: 118

stockAPI=http://localhost/admin
```

The server fetches the contents of the `/admin`  URL and returns it to the user.

An attacker can visit the `/admin` URL, but the administrative functionality is normally only accessible to authenticated users. This means an attacker won't see anything of interest. However, if the request to the `/admin` URL comes from the local machine, the normal access controls are bypassed. The application grants full access to the administrative functionality, because the request appears to originate from a trusted location.

### Why do application behave this way, and implicitly trust requests that come from the local machine?
The various reasons include:
1. The access control check might be implemented in a different component that sits in front of the application server. When a connection is made back to the server, the check is bypassed.
2. For disaster recovery purposes, the application might allow administrative access without logging in, to any user coming from the local machine. This provides a way for an administrator to recover the system if they lose their credentials. This assumes that only a fully trusted user would come directly from the server.
3. The administrative interface might listen on a different port number to the main application, and might not be reachable directly by users.


