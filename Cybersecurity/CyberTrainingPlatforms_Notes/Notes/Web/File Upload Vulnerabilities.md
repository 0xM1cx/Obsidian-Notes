```toc
```
## What are file upload vulnerabilities?
File upload vulnerabilities are when a web server allows users to upload file to its filesystem without sufficiently validating things like their name, type, contents, or size. 

Failing to properly enforce restrictions on these could mean that even a basic image upload function can be used to upload arbitrary and potentially dangerous files instead.  This could even include server-side scripts files that enable remote code execution. 

In some cases, the act of uploading the file is in itself enough to cause damage. Other attacks may involve a follow-up HTTP request for the file, typically to trigger its execution by the server. 


## How do file upload vulnerabilities arise?
Given the fairly obvious dangers, it's rare for websites in the wild to have no restrictions whatsoever on which file users are allows to upload. More commonly, developers implement what they believe to be robust validation that is either inherently flawed or can be easily bypassed. 

For example, they may attempt to blacklist dangerous file types, but fail to account for parsing discrepancies when checking the file extensions. As with any blacklist, it's also easy to accidentally omit more obscure file types that may still be dangerous.

In other cases, the website may attempt to check the file type by verifying properties that can be easily manipulated by an attacker using tools like Burp Proxy or Repeater. 

Ultimately, even robust validation measures may be applied inconsistently across the network of hosts and directories that form the website, resulting in discrepancies that can be exploited.

## Exploiting unrestricted file uploads to deploy a web shell
> A web shell is a malicious script that enables an attacker to execute arbitrary commands on a remote web server simply by sending HTTP requests to the right endpoint. 

If you're able to successfully upload a web shell, you effectively have full control over the server. This means you can read and write arbitrary files, exfiltrate sensitive data, even use the server to pivot attacks against both internal infrastructure and other servers outside the network. E.g. the following PHP code could be used to read arbitrary files from the server's filesystem:
```php
<?php echo file_get_contents('/path/to/target/file'); ?>
```
Once uploaded, sending a request for this malicious file will return the target file's contents in the response. 

A more versatile web shell may look something like this:
```php
<?php echo system($_GET['command']); ?>
```

This script enables you to pass an arbitrary system command via a query parameter as follows. 
```http
GET /example/exploit.php?command=id HTTP/1.1
```

## Exploiting flawed validation of file uploads
When submitting HTML forms, the browser typically sends the provided data in the `POST` request with the content type `application/x-www-form-url-encoded`. This is fine for sending simple text like your name or address. However, it isn't suitable for sending large amounts of binary data, such as an entire image file or a PDF document. In this case, the content type `multipart/form-data` is preferred. 

Consider a form containing fields for uploading an image, providing a description of it, and entering your username. Submitting such a form might result in a request that looks something like this:
```http
POST /images HTTP/1.1 
Host: normal-website.com 
Content-Length: 12345 
Content-Type: multipart/form-data; 
boundary=---------------------------012345678901234567890123456 
---------------------------012345678901234567890123456 
Content-Disposition: form-data; name="image"; filename="example.jpg" 
Content-Type: image/jpeg 
[...binary content of example.jpg...] 
---------------------------012345678901234567890123456 
Content-Disposition: form-data; name="description" 
This is an interesting description of my image. 
---------------------------012345678901234567890123456 
Content-Disposition: form-data; name="username" 
wiener 
---------------------------012345678901234567890123456--
```
The message body is split into separate parts for each oof the form's inputs. Each part contains a `Content-Disposition` header, which provides some basic information about the input field it relates to. These individual parts may also contain their own `Content-Type` header, which tells the server the MIME type of the data that was submitted using this input. 

One way that website may attempt to validate file uploads is to check that this input-specific `Content-Type` header matches an expected MIME type. If the server is only expecting image files, for example, it may only allow types like `image/jpeg` and `image/png`. Problems can arise when the value of this header is implicitly trusted by the server. If no validation is performed to check whether the content of the file actually match the supposed MIME type, this defense can be easily bypassed using tools like Burp Repeater. 

