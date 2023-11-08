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

## Brute-force attacks
A **brute-force** attack is when an attacker uses a system of trial and error to guess valid user credentials. These attacks are typically automated using wordlists of usernames and passwords. Automating this process, especially using dedicated tools, potentially enables an attacker to make vast numbers of login attempts at high speed.

By also using basic logic or publicly available knowledge, attackers can fine-tune brute-force attacks to make much more educated guesses. This considerably increases the efficiency of such attacks. Websites that rely on password-based login as their sole method of authenticating users can be highly vulnerable if they do not implement sufficient brute-force protection.

### Brute-forcing usernames
During auditing, *check whether the website discloses potential usernames publicly*. For example, are you able to access user profiles without logging in? Even if the actual content of the profiles is hidden, the name used in the profile is sometimes the same as the login username. You should also check HTTP responses to see if any email addresses are disclosed. Occasionally, responses contain email addresses of high-privileged users, such as administrators or IT support.

### Brute-forcing passwords
Passwords can similarly be brute-forced, with the difficulty varying based on then strength of the passwords. Many adopt a some form of password policy, which forces users to create high-entropy passwords that are theoretically at least, harder to crack using brute force alone. They involve:
- A minimum number of characters
- A mixture of lower and uppercase letters
- At lease on special character

> The National Institute of Standards and Technology states that password lengths must have a random mix of at least 14-16 characters.


## Username Enumeration
**Username enumeration** is when an attacker is able to observe changes in the website's behavior in order to identify whether a given username is valid. This typically occurs either on the login page, e.g. when you enter a valid username but an incorrect password, or on registration forms when you enter a username that is already taken. 

When attempting to brute-force a login page, you should pay particular attention to any differences:
- **Status codes**: During a brute-force attack, the returned HTTP status code is likely to be the same for the vast majority of guesses because most of them will be wrong. If a guess returns a different status code, this is a strong indication that the username was correct. It is best practice for websites to always return the same status code regardless of the outcome, but this practice is not always followed.
- **Error messages**: Sometimes the returned error message is different depending on whether both the username AND password are incorrect or only the password was incorrect. It is best practice for websites to use identical, generic messages in both cases, but small typing errors sometimes creep in. Just one character out of place makes the two messages distinct, even in cases where the character is not visible on the rendered page.
- **Response times**: If most of the requests were handled with a similar response time, any that deviate from this suggest that something different was happening behind the scenes. This is another indication that the guessed username might be correct. For example, a website might only check whether the password is correct if the username is valid. This extra step might cause a slight increase in the response time. This may be subtle, but an attacker can make this delay more obvious by entering an excessively long password that the website takes noticeably longer to handle.


## Bypassing two-factor authentication
If the user is first prompted to enter a password, and then prompted to enter a verification code on a separate page, the user is effectively in a "logged in" state before they have entered the verification code. In this case, it is worth testing to see if you can directly skip the "logged-in only" pages after completing the first authentication step. Occasionally, you will find that a website doesn't actually check whether or not you completed the second step before the loading page. 