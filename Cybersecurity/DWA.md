## What are Web Attacks?
Web applications are applications that provide services for users through a browser interface. Today web applications make up a large portion of internet usage. Sites such as Google, Facebook and YouTube (excluding the mobile applications) are actually web applications.

Because web applications are an interface on the internet for many organizations, attackers could exploit these applications and infiltrate into devices, they could capture personal data or cause service breakdowns inflicting a serious amount of financial damage. 

Below you will find some attack methods used to infiltrate web applications. We will address these methods in our “Web Attacks 101” course; we will explain what these methods are, how and why attackers use them and how we can detect such activities.
-   SQL Injection
-   Cross Site Scripting
-   Command Injection
-   IDOR
-   RFI & LFI
-   File Upload (Web Shell)

## Why Detecting Web Attacks Importatnt?
When you look at the daily life of the Average Joe you will see that he uses many web applications throughout the day. There are those who visit Spotify to listen to music, those who visit YouTube to watch videos or those who use social media.

It is no surprise that attackers choose web applications as a gateway for their attacks because all institutions have web applications which mostly contain critical data and because modern day applications are highly complicated and have numerous attack vectors. A study conducted by Acunetix reimburses this idea.

> “””Recent research shows that 75% of cyber attacks are done at the web application level.“”” [1]

If we examine the anatomy of an attack, we see that the best scenario is to prevent the attack in its first phase. For this reason, there are various security precautions that aim to prevent and detect web applications (WAF, IPS, SIEM rules…).

It is crucial that a SOC analyst detects these web application based attacks which are the preference of attackers and takes precautions against them.

**Reference**[1]        [https://www.acunetix.com/websitesecurity/web-application-attack/](https://www.acunetix.com/websitesecurity/web-application-attack/)

# OWASP
The Open Web Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software.

It goes without doubt that OWASP is one of the best resources to gain information about web application security.

#### OWASP Top Ten
OWASP publishes a list of 10 web application vulnerabilities that possess the most critical security risks every couple of years.
The OWASP list published in  2021 contains these critical security risks:
1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Insecure Design
5. Security Misconfiguration
6. Vulnerable and Outdated Components
7. Identification and Authentication Failures
8. Software and Data Integrity Failures
9. Security Logging and Monitoring Failures
10. Server-Side Request Forgery (SSRF)
  
You can read the OWASP publication which contains the most critical security risks [here](https://owasp.org/).
**References**

[1] [https://owasp.org/](https://owasp.org/)

## How Web Applications Works
In order to detect an anomaly we should first understand how the technology works. Applications utilize certain protocols to communicate accurately with each other. Web applications communicate via the Hyper-Text Transfer Protocol (HTTP). Let’s look into how the HTTP protocol works.

For a start, it’s important to know that the HTTP protocol is on the 7th layer of the OSI model. This means that protocols such as the Ethernet, IP, TCP, and SSL are used before the HTTP protocol.

**Examining the HTTP Requests and Response**

#### HTTP Requests
An HTTP Request is used to retrieve a certain resource from a web server. This resource may be an HTML file, video, or json data etc. The web server’s job is to process the received response and present it to the user. 

There is a standard HTTP format, and all requests must comply with this format so web servers can understand the request. If the request is sent in a different format, then the web server will not understand it and it will send an error to the user or the web server may not be able to provide service (which is another attack type).
![[Pasted image 20220513134005.png]]
An HTTP Request line consists of a request line, request headers and a request message body. A request line consists of the HTTP method and the resource requested from the web server. The request header contains certain headers that the server will process. The request message body contains data that is intended to be sent to the server.

In the image above you see an example of an HTTP Request. Let’s examine this HTTP Request line by line.

1.  The GET method states that the resource “/” is requested from the server. Because there is no name, rather a symbol such as “/” means that the web server’s main page is requested.
2.  Nowadays there are web applications that belong to more than one domain found on a single web server, so browsers use“Host” header to describe which domain the requested resource belongs to.
3.  When a web application wants to store information on the client’s device it stores it in a “Cookie” header. Cookies are generally used to store session information. Therefore, you do not have to re enter your username and password when you visit a web application that requires login. 
4.  The “Upgrade-Insecure-Requests” header is used to state that the client wants to communicate with encryption (SSL).
5.  There is information regarding the client’s browser and operating system under the “User-Agent' header'. Web servers use this information to send specific HTTP Responses to the client. You can find some automated vulnerability scanners by looking under this header.
6.  The type of data requested is found under the “Accept” header.
7.  The encoding type that the client understands is found under “Accept-Encoding” header. You can usually find compression algorithm names under this header.
8.  Under the “Accept-Language” header you can find the clients language information. The web server uses this information to display the prepared content in the client’s language.
9.  The “Connection” header shows how the HTTP connection will be made. If there is any data such as “close” found here, it means that the TCP connection will be closed after the HTTP response is received. If you see “Keep-alive” this means that the connection will be continued.
10.  An empty line is put between the HTTP Request Header and the HTTP Request Message Body to make a partition.
11.  Other data intended to be sent to the web application is found within the Request Message Body. If the HTTP POST method is used, then POST parameters can be found here.

#### HTTP Response
Once the web server receives an HTTP Request, it performs the required controls and processes and then sends the requested resource to the client. There is no uniform process here because there are numerous technologies and designs involved. The server may pull data from the database according to what the requested resource is, or it can process according to incoming data. But the HTTP Response Message must reach the client after all the processing.

A HTTP Response Message contains a Status Line, Response Headers, and a Response Body. The Status Line contains the status code (such as 200: OK) and HTTP protocol information. There are headers used for numerous purposes within the Response Header.  Data related to the requested resource is found within the Response Body.

If a web page was requested, there will usually be HTML codes in the Response Body. When the client receives the HTML code, the web browser processes the HTML code and displays the web page.
![[Pasted image 20220513135441.png]]
- **Status Line** -> There is information about the HTTP version and HTTP response status code in the Status Line. HTTP response status code is used to describe the status of the request. There are many HTTP response status codes, but they can be summarized as so:
●      **100-199**: Informational responses
●      **200-299**: Successful responses
●      **300-399**: Redirection messages
●      **400-499**: Client error responses
●      **500-599**: Server error responses

- **Response Headers** -> Here are some HTTP Response Headers that you may come across frequently:
	- Date --> The exact time the server sent the HTTP Response to the client.
	- Connection --> It states how the connection will be handled, just like in the HTTP Request header.
	- Server --> Informaition about the server's OS and the Web server's version.
	- Last-Modified --> Information about when the requested reseource was changed. This header is used for the cache mechanism.
	- Content-Type --> The type of data that is sent.
	- Content-Length --> The size of the data sent.

- **Response Body** -> The HTTP Response Body contains the resources that was sent by the server and requested by the client.

## What is SQL Injection(SQLi)
SQL Injections are critical attack methods where a web application directly includes unsanitized data provided by the user in SQL queries.
The frameworks we use these days to develop web applications have preventative mechanisms in place to protect against SQL Injection attacks. But we still come across SQL Injection vulnerabilities because sometimes raw SQL queries are used, sometimes the framework has an innate SQL Injection vulnerability or the framework is not used properly.

#### SQL Injection Types
There are 3 types of SQL Injections. These are: 
1.  **In-band SQLi (Classical SQLi)**: If a SQL query is sent and a replied to over the same channel, we call these In-band SQLi. It is easier for attackers to exploit these compared to other SQLi categories.
  
2.  **Inferential SQLi (Blind SQLi):** SQL queries that receive a reply that cannot be seen are called Inferential SQLi. They are called Blind SQLi because the reply cannot be seen.
  
3.  **Out-of-band SQLi**: If the reply to a SQL query is communicated over a different channel then this type of SQLi is called Out-of-band SQLi. For example, if the attacker is receiving replies to his SQL queries over the DNS this is called an out-of-band SQLi.

#### How does SQL Injections Works?
Today standard web applications most commonly receive data from a user and use this data to display specific content. The login page is where most SQL Injection attacks happen. Let’s examine how SQL injections work through an example.

A user is generally expected to enter his/her username and password on the login page. On the other side, the web application will use this username and password information to create a SQL query like the one below:

> SELECT * FROM users WHERE username = '**USERNAME**’ AND password = '**USER_PASSWORD**'

The meaning of this SQL query is “bring me all the information about the user from the users table whose name is **USERNAME** and whose password is **USER_PASSWORD**”. If the web application does find a matching user, it will authenticate the user, if it cannot find a user after the query is performed then the login will be unsuccessful.

#### How Attackers Leverage with SQL Injection Attacks
In order to understand why SQL Injection Attacks are so critically important, let's take a look at what a SQL injection attack can cause.
- Authentication bypass
- Command Execution
- Exfiltrating sensitive data
- Creating/deleting/updating database entries


#### How to Prevent SQL Injections
-   **Use a framework:** of course just using a framework will not be sufficient to prevent a SQL Injection attack. It is of utmost importance to use the framework in accordance with documentation.
-   **Keep your framework up to date:** Keep your web application secure by following security updates related to the framework you use.
  
-   **Always sanitize data received from a user:** Never trust data received from a user. On top of that do not only sanitize the form data but also do the same with other data (such as Headers, URLs, etc.)
-   **Avoid using raw SQL queries:** You may have a habit of writing raw SQL queries but you should opt to make use of the benefits a framework provides and you should also make use of the security it provides.

#### Detecting SQL Injection Attacks
We have discussed what attackers can do with a SQL Injection attack in the previous section. Each of the results of a SQL Injection stated above could cause great loss for an institution so as SOC Analysts we should be able to detect these attacks and be able to take precautions against them.

So, how can we detect SQL Injection attacks?
There is more than one answer to this question. These are: 
-   **When examining a web request check all areas that come from the user:** Because SQL Injection attacks are not limited to the form areas, you should also check the HTTP Request Headers like User-Agent.
  
-   **Look for SQL keywords:** Look for words like INSERT, SELECT, WHERE within the data received from users.
  
-   **Check for special characters:** Look for apostrophes (‘), dashes (-), or parentheses which are used in SQL or special characters that are frequently used in SQL attacks within the data received from the user.
-   **Familiarize yourself with frequently used SQL Injection payloads:** Even though SQL payloads change according to the web application, attackers still use some common payloads to check for SQL Injection vulnerabilities. If you are familiar with these payloads, you can easily detect SQL Injection payloads. You can see some frequently used SQL Injection payloads [here](https://github.com/payloadbox/sql-injection-payload-list).

#### **Detecting Automated SQL Injection Tools**

Attackers use many automated devices to detect SQL Injection vulnerabilities. One of the most well known is Sqlmap. Let’s look at the wider picture instead of focusing on a specific tool.

You may use the methods listed below to detect SQL Injection devices:
1.  **Look at the User-Agent:** Automated browser devices generally have their names and versions recorded. You can look at the User-Agent to detect these automated devices.
2. **Check the frequency of requests:** Automated devices were designed to send an estimated amount of many requests per second to be able to test payloads as quickly as possible. A normal user could send 1 request per second, so you can tell if the requests are made by an automated device or not by looking at the number of requests per second.
3. **Look at the contents of the payload:** Automated devices usually record their own names in their payloads. For  example a SQL Injection payload sent by an automated device could look like this:  **sqlmap’ OR 1=1**
4. **Is the payload complicated:** This detection method may not always work but based on my experience, I could say that automated devices send more complicated payloads.

#### **Detection Example**
We have access logs of a web application that was victim to a SQL Injection attack. 

You may not have heard what an access log is before. In short, these are the web server’s access logs. These logs usually contain the source IP address, date, requested URL, HTTP method, user-agent and HTTP Response code. These logs are very useful in investigations.
![[Pasted image 20220513203136.png]]
(SQL Injection Access Logs)

We have an access log in hand. Now what do we do?

Firstly, when we look at the pages that were requested we see that besides pages like “info.php” which is fairly readable, there are also requests made for pages that are complex and have symbols like %. We cannot say that requests for pages like these are malicious but the fact that they are made repetitively and many times is suspicious.

First of all, let’s talk about what the % symbols mean. When we request a page that contains special characters, these requests are not directly transferred to the web server. Instead, our browsers perform a URL encoding (Percent Encoding) of the special characters and replaces each special character with a character string that begins with % and has 2 hexadecimal characters in it. So the pages containing the % symbol above are pages that contain special characters.
![[Pasted image 20220513210154.png]]
Now that we understand what the % symbols mean, let’s revisit the access logs. When we look at the requests, we can easily see that besides the % symbols there are readable words such as “UNION”, “SELECT”, “AND”, “CHR”.  Because these are specific words that belong to SQL, we can determine that we are face to face with a SQL Injection attack.

To save our eyes, let’s make the examination a little easier. You can conduct a search using the keywords “Online URL Decoder” to find web applications that will automatically do the URL decoding for you. In order to read these access logs easier I will get help from these web applications, by doing so I won’t have to strain my eyes or yours.

Let me add a little note. It is not wise to upload something like an access logs which contain critical information on a 3rd party web application. The access logs I uploaded were prepared specifically for this training so there is no problem in my doing so. But you shouldn’t make such mistakes in your professional life.![[Pasted image 20220513210205.png]]
When we do the URL decoding we can more clearly see that this is a SQL Injection attack. So what should we do now? Yes, we have confirmed that it is a SQL Injection attack but do we leave it there?

Of course not. Now we are going to find any other pieces of information that we can from these access logs.
![[Pasted image 20220513210215.png]]
First, let’s look at the request dates. All the SQL Injection payloads were sent on “19/Feb/2022 11:09:24”. We can see that more than 50 requests were made in 1 second. The fact that so many requests were made in such a short time shows us that this is an automatized attack. Additionally, as we have mentioned before, when attackers perform manual tests they choose to test easy payloads first. But when we look at the access logs we see that the payloads are very complicated. This goes to show that the attack may very well be automated.

We have confirmed that a SQL Injection attack has been performed and that it has been performed with an automated device. So we can end our analysis, right?

There is one more step left to do. We need to determine whether the attack was successful or not. You can determine whether a SQL Injection attack has been successful by looking at the response but in your professional career you will almost never have access to the response. We can presume that all responses will be about the same size because the attack is performed on the same page and over the “id” variable. We can estimate the success of the attack by looking at the size of the response.

Unfortunately, the basic web server that was developed to serve as an example cannot supply a reliable response size. Therefore, we cannot estimate if the attack has been successful looking at this example. But with web servers that have been configured correctly, we can find the response size within the access logs. You can examine this area to determine whether there is a notable difference in response sizes. If there is a notable difference you can estimate that the attack has been successful. But in this situation it would be best to escalate this alert to a higher-tier analyst.

**What we know:** 
1.  There has been a SQL Injection attack performed on the “id” parameter on the web application’s main page.
2. The requests came from the IP address: 192.168.31.174.
3. Because there have been 50+ requests per second, this attack has been performed by an automated vulnerability scanning tool.
4. The complex nature of the payloads supports the claim in # 3.
5. We cannot determine whether the response was successful or not because we do not have any information about the response size.