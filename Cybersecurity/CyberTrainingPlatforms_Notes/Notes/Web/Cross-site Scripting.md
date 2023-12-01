**Cross-site scripting(XSS)** is a web security vulnerability that allows an attacker to compromise the interactions that users have with a vulnerable application. It allows an attacker to circumvent to the same origin policy, which is designed to segregate different websites from each other. 

## How does it work?
XSS works by manipulating a vulnerable website so that it returns malicious JS to users. When the malicious code executes inside a victim's browser, the attacker can fully compromise their interaction with the application.

## Proof of Concept
You can confirm most kinds of XSS vulnerabilities by injecting a payload that causes your own browser to execute some arbitrary JavaScript. It's long been a common practice to use the `alert()` function for this purpose because it's short, harmless, and pretty hard to miss when it's successfully called. 

Unfortunately, there's a slight hitch if you use Chrome. From version 92 onward(July 20th, 2021), cross-origin iframes are prevented from calling `alert()`. As these are used to construct some of the more advanced XSS attackers, you'll sometimes need to use an alternative PoC payload.

In this scenario, the `print()` function is recommended. As the simulated victim in our labs uses Chrome, we've amended the affected labs to that they can also be solved using `print()`


**Types of XSS attacks**
- [[#Reflected XSS]]
- [[#Stored XSS]]
- [[#DOM-based XSS]]

### Reflected XSS
This is the simplest variety of cross-site scripting. It arises when an application receives data in an HTTP request and includes that data within the immediate response in an unsafe way. Example: 
```html
https://insecure-website.com/status?message=All+is+well. 
<p>Status: All is well.</p>
```

In this scenario, the application doesn't perform any other processing of the data, so an attacker can easily construct an attack list this:
```html
https://insecure-website.com/status?message=<script>/*+Bad+stuff+here...+*/</script> <p>Status: <script>/* Bad stuff here... */</script></p>
```
If a user visits the URL constructed by the attacker, then the attacker's script executes in the user's browser, in the context of that user's session with the application. At that point, the script can carry out any action, and retrieve any data, to which the user has access. 
### Stored XSS
Also known as **persistent or second-order XSS** arises when an application receives data from an untrusted source and includes that data within its later HTTP responses in an unsafe way. 

The data in question might be submitted to the application via HTTP request; for example, comments on a blog post, user nicknames in a chat room, or contact details on a customer order.  In other cases, the data might arrive from other untrusted sources; E.g., a webmail application displaying messages received over SMTP, a market application displaying socmed posts, or a network monitory application displaying packet data from network traffic. 

Example of a message board application that let's users submit messages, which are displayed to other users:
```html
<p>Hello, this is my message!</p>
```
This application doesn't perform any other processing of the data, so an attacker can easily send a message that attacks other users: 
```html
<p><script>/*Bad code here...*/</script></p>
```
### DOM-based XSS
Also known as **DOM XSS** arises when an application contains some client-side JavaScript that processes data from an untrusted source in an unsafe way, usually by writing the data back to the DOM. 

In the following example, an application uses some JavaScript to read the value from an input field and write that value to an element within the HTML:
```JS
var search = document.getElementById('search').value; 
var results = document.getElementById('results'); 
results.innerHTML = 'You searched for: ' + search;
```

If the attacker can control the value of the input field, they can easily construct a malicious value that causes their own script to execute:
```html
You Searched for: <img src=1 onerror='/* Bad Stuff here...*/'>
```

In a typical case, the input field would be populated from part of the HTTP request, such as a URL query string parameter, allowing the attacker to deliver an attack using a malicious URL, in the same manner as reflected XSS.


## Impact of XSS vulnerabilities
- in a brochureware application, where all users are anonymous and all information is public, the impact will often be minimal. 
- In an application holding sensitive data, such as banking transactions, emails, or healthcare records, the impact will usually be serious. 
- If the compromised user has elevated privileges within the application, then the impact will generally be critical, allowing the attacker to take full control of the vulnerable application and compromise all users and their data.


## How to find and test for XSS vulnerabilities 
- The vast majority of XSS vulnerabilities can be found quickly and reliably using Burp Suite's [web vulnerability scanner](https://portswigger.net/burp/vulnerability-scanner).
  
- Manually testing for **reflected and stored XSS** normally involves submitting some simple unique input(such as a short alphanumeric string) into every entry point in the application, identify every location were the submitted input is return in HTTP responses, and testing each location individually to determine whether suitably crafted input can be used to execute arbitrary JavaScript. In this way, you can determine the context in which the XSS occurs and select a suitable payload to exploit.
  
- Manually testing for DOM-based XSS arising from URL parameters involves a similar process: placing some simple unique input in the parameter, using the browser's developer tools to search the DOM for this input, and testing each location to determine whether it is exploitable. However, other types of DOM XSS are harder to detect. To find [DOM-based vulnerabilities](https://portswigger.net/web-security/dom-based) in non-URL-based input (such as `document.cookie`) or non-HTML-based sinks (like `setTimeout`), there is no substitute for reviewing JavaScript code, which can be extremely time-consuming. Burp Suite's web vulnerability scanner combines static and dynamic analysis of JavaScript to reliably automate the detection of DOM-based vulnerabilities.

## Content Security Policy
**Content Security Policy(CSP)** is a browser mechanism that aims to mitigate the impact of cross-site scripting and some other vulnerabilities. If an application that employs CSP contains XSS-like behavior, then the CSP might hinder or prevent exploitation of the vulnerability. Often, the CSP can be circumvented to enable exploitation of the underlying vulnerability. 


## Dangling Markup Injection
This is a technique that can be used to capture data cross-domain in situations where a  full cross-site scripting exploit is not possible, due to input filters or other defenses. It can often be exploited to capture sensitive information that is visible to other users, including CSRF tokens that can be used to perform unauthorized actions on behalf of the user. 