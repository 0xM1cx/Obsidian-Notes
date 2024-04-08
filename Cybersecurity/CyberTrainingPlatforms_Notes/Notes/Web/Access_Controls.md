## What is access control?
- It is the application of constraints on who or what is authorized to perform actions or access resources. 
- In the context of web applications, access controls is dependent on authentication and session management.
---
- **Authentication** confirms that the user is who they say they are.
- **Session management** identifies which subsequent HTTP request are being made by the same user
- **Access control** determines whether the use is allowed to carry out the action that they are attempting to perform
- Broken access controls are common and often present a critical security vulnerability.
## Vertical privilege escalation
- If a user can gain access to functionality that they are not permitted to access then this is vertical privilege escalation.
- For example, if a non-administrative user can gain access to an admin page where they can delete user accounts, then this is vertical privilege escalation.

### Unprotected functionality
- The most basic vertical privilege escalation. 
- Arises from when an application does not enforce any protection for sensitive functionality.
- For example, administrative functions might be linked from an administrator's welcome page but not from a user's welcome page. But, the use can just navigate to the admin page and is able to have administrative functions. Like 
```url
https://insecure-website.com/admin
```
Just by navigating to that page, the use can now have administrative functions. 

- In some cases, sensitive functionality is concealed by giving it a less predictable URL. This is an example of so-called "security by obscurity". However, hiding sensitive functionality does not provide effective access control because users might discover the obfuscated URL in a number of ways.

### Parameter-based access control methods
- Some applications determine the user's access rights or role at login, and then store this information in a user-controllable location. Like:
	- A hidden field
	- Cookie
	- A preset query string parameter
- The application makes access control decisions based on the submitted value. For example:
```url
https://insecure-website.com/login/home.jsp?admin=true
https://insecure-website.com/login/home.jsp?role=1
```

## Horizontal Privilege Escalation
- This occurs if a user is able to gain access to resources belonging to another use, instead of their own resources of that type.
- For example, if an employee can access the records of other employees as well as their own, then this is horizontal privilege escalation. 
- They use similar types of exploit methods to vertical privilege escalation. For example, a user might access another users accounts, with the same functionalities as his like this:
```url
https://insecure-website.com/myaccount?id=123
```
The attacker can change the id to that of another user to get access to his account.


## Horizontal to vertical privilege escalation
- Often, a horizontal privilege escalation can be turned into a vertical privilege escalation by compromising a more privilege user. 
- For example, a horizontal escalation might allow an attacker to reset or capture the password belonging to another user. If the attacker targets an administrative user and compromises their account, then they can gain administrative access and so perform vertical privilege escalation. 
