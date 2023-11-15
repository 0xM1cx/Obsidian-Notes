```toc
```
## What is OS command injection
Also known as **shell injection**. It allows an attacker to execute OS commands on the server that is running an application, and typically fully compromise the application and its data. Often, an attacker can leverage an OS command injection vulnerability to compromise other parts of the hosting infrastructure, and exploit trust relationships to pivot the attack to other systems within the organization.

## Useful commands

| Purpose of Command    | Linux         | Windows         |
| --------------------- | ------------- | --------------- |
| Name of Current User  | `whoami`      | `whoami`        |
| Operating System      | `uname -a`    | `ver`           |
| Network Configuration | `ifconfig`    | `ipconfig /all` |
| Network Connections   | `netstat -an` | `netstat -an`   |
| Running Processes     | `ps -ef`      | `tasklist`      |

## Injecting OS commands
in this example, a shopping application lets the user view whether an item is in stock in a particular store. This information is accessed via a URL:
```http
https://insecure-website.com/stockStatus?productID=381&storeID=29
```
To provide the stock information, the application must query various legacy systems. For historical reasons, the functionality is implemented by calling out to a shell command with the product and store IDs as arguments:
```
stockreport.pl 381 29
```
This command outputs the stock status for the specified item, which is returned to the user.


