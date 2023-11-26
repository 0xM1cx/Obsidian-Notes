**Authentication Vulnerabilities** can allow attackers to gain access to sensitive data and functionality. They also expose additional attack surface for further exploits. 

- The most common authentication mechanism used by websites
- Potential vulnerabilities in these mechanisms
- Inherent vulnerabilities in different authentication mechanisms
- Typical vulnerabilities that are introduced by their improper implementation
- How you can make your own authentication mechanisms as robust as possible. 

## Authentication vs Authorization
**Authentication** is the process of verifying that a user is who they claim to be.
**Authorization** involves verifying whether a user is allowed to do something.

For example, authentication determines whether someone attempting to access a website with the username `Carlos123` really is the same person who created the account.

Once `Carlos123` is authenticated, their permissions determine what they are authorized to do. For example, they may be authorized to access personal information about other users, or perform actions such as deleting another user's account.

## How do authentication vulnerabilities arise?
Most vulnerabilities in authentication mechanisms occur in one of two ways:
- The authentication mechanisms are weak because they fail to adequately protect against brute-force attacks.
- Logic flaws or poor coding in the implementation allow the authentication mechanisms to be bypassed entirely by an attacker. This is sometimes called **"broken authentication"**

In many areas of web development, logic flaws cause the website to behave unexpectedly, which mayor may not be a security issue. However, as authentication is so critical to security, it's very likely that flawed authentication logic exposes the website to security issues. 


---
## Vulnerabilities in password-based login

### Brute-force attacks
A **brute-force** attack is when an attacker uses a system of trial and error to guess valid user credentials. These attacks are typically automated using wordlists of usernames and passwords. Automating this process, especially using dedicated tools, potentially enables an attacker to make vast numbers of login attempts at high speed.

By also using basic logic or publicly available knowledge, attackers can fine-tune brute-force attacks to make much more educated guesses. This considerably increases the efficiency of such attacks. Websites that rely on password-based login as their sole method of authenticating users can be highly vulnerable if they do not implement sufficient brute-force protection.
#### Brute-forcing usernames
During auditing, ***check whether the website discloses potential usernames publicly***. For example, are you able to access user profiles without logging in? Even if the actual content of the profiles is hidden, the name used in the profile is sometimes the same as the login username. You should also check HTTP responses to see if any email addresses are disclosed. Occasionally, responses contain email addresses of high-privileged users, such as administrators or IT support.
#### Brute-forcing passwords
Passwords can similarly be brute-forced, with the difficulty varying based on then strength of the passwords. Many adopt a some form of password policy, which forces users to create high-entropy passwords that are theoretically at least, harder to crack using brute force alone. They involve:
- A minimum number of characters
- A mixture of lower and uppercase letters
- At lease on special character

> The National Institute of Standards and Technology states that password lengths must have a random mix of at least 14-16 characters.

### Username Enumeration
Username enumeration is when **an attacker is able to observe changes in the website's behavior in order to identify whether a given username is valid**. This typically occurs either on the login page, e.g. when you enter a valid username but an incorrect password, or on registration forms when you enter a username that is already taken. 

When attempting to brute-force a login page, you should pay particular attention to any differences:
- **Status codes**: During a brute-force attack, the returned HTTP status code is likely to be the same for the vast majority of guesses because most of them will be wrong. If a guess returns a different status code, this is a strong indication that the username was correct. It is best practice for websites to always return the same status code regardless of the outcome, but this practice is not always followed.
- **Error messages**: Sometimes the returned error message is different depending on whether both the username AND password are incorrect or only the password was incorrect. It is best practice for websites to use identical, generic messages in both cases, but small typing errors sometimes creep in. Just one character out of place makes the two messages distinct, even in cases where the character is not visible on the rendered page.
- **Response times**: If most of the requests were handled with a similar response time, any that deviate from this suggest that something different was happening behind the scenes. This is another indication that the guessed username might be correct. For example, a website might only check whether the password is correct if the username is valid. This extra step might cause a slight increase in the response time. This may be subtle, but an attacker can make this delay more obvious by entering an excessively long password that the website takes noticeably longer to handle.

### Flaws in brute-force protection
It is highly likely that a brute-force attack will involve many failed guesses before the attacker successfully compromises an account. Logically, brute-force protection revolves around trying to make it as tricky as possible to automate the process and slow down the rate at which an attacker can attempt logins. 

#### How to secure your authentication mechanisms
Authentication is a complex topic, outlining ever possible measure you can take to protect your own websites is clearly not possible. However, there are several general principles that you should always follow. 

#### 2 common ways of preventing brute-force attacks
- Locking the account that the remote user is trying to access if they make too many failed login attempts
- Blocking the remote user's IP address if they make too many login attempts in a quick succession. 

Both have varying degrees of protection, but neither is invulnerable, especially if the implementation used flawed logic. 

For example, you might find that your IP is blocked if you fail to log in  too many times. In some implementations, the counter for the number of failed attempts resets if the IP owner logs in successfully. This means that an attacker would simply have to login to their own account every few attempts to prevent this limit from ever being reached.  Merely including your own credentials at regular intervals throughout the wordlist is enough to render this defense virtually useless. 

#### Account locking
One way to prevent brute-forcing on sites is to lock the account if certain suspicious criteria is met, usually a set of number of failed login attempts. Just as with normal login errors, responses from the server indicating that an account is locked can also help an attacker to enumerate usernames. But this fails to prevent brute-forcing in which the attacker is just trying to gain access to any random account they can. 


#### The following method can be used to work around this kind of protection
1. Establish a list of usernames that can be valid. Either through username enumeration or simply based on a list of common usernames. 
2. Decide on a very small shortlist of passwords that you think at lease on user likely uses. Crucially, the number of passwords you select must not exceed the number of login attempts allowed. E.g. if you have worked out that the limit is 3 attempts, you need to pick a maximum of 3 password guesses. The proceed to the next username.
3. Using a tool such as Burp Intruder, try each of the selected passwords with each of the candidate usernames. This way, you can attempt to brute-force every account without triggering the account lock. You only need a single user to use one of the three passwords in order to compromise an account.  
 
Account locking also fails to protect against **credential stuffing** attacks. This involves using a massive dictionary of `username:passwords` pairs, compose of genuine login credentials stolen in data breaches. **Credential stuffing** relies on the fact that many people reuse the same username and passwords on multiple website and, therefore, there is a chance that some of the compromised credentials in the dictionary are also valid on the target. 

#### User Rate Limiting
Another way websites try to prevent brute-force attacks is through user rate limiting. In this case, making too many login requests within a short period of time causes your IP address to be blocked Typically, the IP can only be unblocked in on the following ways:
- Automatically after a certain period of time has elapsed
- Manually by an administrator
- Manually by the user after successfully completing a CAPTCHA

User Rate Limiting is sometimes preferred to account locking due to being less prone to username enumeration and DOS attacks. However, it is still not completely secure. As we saw an example of in an earlier lab, there are several ways an attacker can manipulate their apparent IP in order to bypass the block. 

As the limit is based on the rate of HTTP request sent from the user's IP address, it is sometimes also possible to bypass this defense if you can work out *how to guess multiple password with a single request.* 
### Exploiting HTTP Basic Authentication
In HTTP basic authentication, the client receives an authentication token from the server, which is constructed by concatenating the username and password, and encoding it in Base64. This token is stored and managed by the browser, which automatically adds it to the `Authorization` header of every subsequent request as follows:
```http
Authorization: Basic base64(username:password)
```
This is generally not considered a secure authentication method. Firstly, it involves repeatedly sending the user's login credentials with every request. Unless the website also implements HSTS, user credentials are open to being captured in a MITM attack. 

> **HSTS**: HTTP Strict Transport Security is a simple and widely supported standard to protect visitors by ensuring that their browsers always connect to a website over HTTPS. It exists to remove the need for the common, insecure practice of redirecting users from http:// to https:// URLs.

In addition, implementation of HTTP basic authentication often don't support brute-force protection. As the token consists exclusively of static values, this can leave it vulnerable to being brute-forced. It is also  particularly vulnerable to session-related exploits, notably CSRF, against which it offers no protection on its own. 

---
## Vulnerabilities in multi-factor authentication
It is increasingly common to see both mandatory and optional 2FA based on **something you know** and **something you have**. This usually required users to enter both the traditional password and a temporary verification code from an out-of-band physical device in their possession.

### Two-Factor authentication Tokens
**Verification codes** are usually read by the user from a physical device of some kind. Many high-security websites now provide users with a dedicated  device for this purpose, such as the RSA token or keypad device that you might use to access your online banking or work laptop. These dedicated devices also have the advantage of generating the verification code directly. It is also common for websites to use a dedicated mobile app, such as Google Authenticator, for the same reason. 

Some websites also send verification codes to user's mobile phone as a *text message*. While this is technically still verifying the factor of "something you have", it is open to abuse. Firstly, the code is being transmitted via SMS rather than being generated by the device itself. This creates the potential for the code to be intercepted. There is also a risk of SIM swapping, whereby an attacker fraudulently obtains a SIM card with the victim's phone number. The attacker would then receive all SMS messages sent to the victim, including the one containing their verification code. 

#### Bypassing two-factor authentication
At times, the implementation of two-factor authentication is flawed to the point where it can be bypassed entirely. 

If the user is first prompted to enter a password, and then prompted to enter a verification code on a separate page, the user is effectively in a "logged in" state before they have entered the verification code. In this case, it is worth testing to see if you can directly skip the "logged-in only" pages after completing the first authentication step. Occasionally, you will find that a website doesn't actually check whether or not you completed the second step before the loading page. 

#### Flawed two-factor verification logic
Sometimes flawed logic in two-factor authentication means that after a user has completed the initial login step, the website doesn't adequately verify that the same user is completing the second step. 

For example, the user logs in with their normal credentials in the first step as follows:
```http
POST /login-step/first HTTP/1.1
Host: vulnerable-website.com
...

username=carlos&password=qwerty
```

They are then assigned a cookie that relates to their account, before being taken to the second step of the login process:
```http
HTTP/1.1 200 OK
Set-Cookie: account=carlos

GET /login-steps/second HTTP/1.1
Cookie: account=carlos
```
When submitting the verification code, the request uses this cookie to determine which account the user is trying to access:
```http
POST /login-steps/second HTTP/1.1
Host: vulnerable-website.com
Cookie: account=carlos
...

verification-code=123456
```
In this case, an attacker could log in using their own credentials but then change the value of the `account` cookie to any arbitrary username when submitting the verification code.
```http
POST /login-steps/second HTTP/1.1
Host: vulnerable-website.com
Cookie: account=victim-user
...

verification-code=123456
```
This is extremely dangerous if the attacker is then able to brute-force the verification code as it would allow them to log in to arbitrary users' accounts based entirely on their username. They would never even need to know to the user's password. 

### Brute-forcing 2FA verification codes
As with passwords, websites need to take steps to prevent brute-forcing of the 2FA verification code. This is especially important because the code is often a simple 4 or 6-digit number. Without adequate brute-force protection, cracking such a code is trivial. 

Some websites attempt to prevent this by automatically logging a user out if they enter a certain number of incorrect verification codes. This is ineffective in practice because an advanced attacker can even automate this multi-step process by creating macros for Burp Intruder. The Turbo extension can also be used for this purpose. 

---
### Take care with user credentials
Even the most robust authentication mechanisms are ineffective if you unwittingly disclose a valid set of login credentials to an attacker. It should go without saying that you should **never send any login data over unencrypted connections**. Although you may have implemented HTTPS for your login requests, make sure that you enforce this by **redirecting any attempted HTTP requests to HTTPS** as well.

You should also audit your website to make sure that no username or email addresses are disclosed either through publicly accessible profiles or reflected in HTTP responses.