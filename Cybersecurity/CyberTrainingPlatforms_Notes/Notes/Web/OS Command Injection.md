```toc
```
## What is OS command injection
Also known as **shell injection**. It allows an attacker to execute OS commands on the server that is running an application, and typically fully compromise the application and its data. Often, an attacker can leverage an OS command injection vulnerability to compromise other parts of the hosting infrastructure, and exploit trust relationships to pivot the attack to other systems within the organization.

## Types of Command Injection
1. **In-band Command Injection**. Consists of an attacker executing commands on the host operating system via a vulnerable application and *receiving the response of the command in the application*.
2. **Blind Command Injection**. Consists of an attacker executing commands on the host operating system via a vulnerable application *that does not return the output from the command within its HTTP response*
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

---
The application implements no defenses against OS command injection, so an attacker can submit the following input to execute an arbitrary command:
```shell
& echo aiwefwlguh &
```

If this input is submitted in the `productID` parameter, the command executed by the application is:
```shell
stockreport.pl & echo aiwefwlguh & 29
```
The `echo` command causes the supplied string to be echoed in the output. This is a useful way to test for some types of OS command injection. The `&` character is a shell command separator. In this example, it causes three separate commands to execute, one after another. The output returned to the user is:
```shell
Error - productID was not provided
aiwefwlguh
29: command not found
```

The three lines demonstrate that:
- The original `stockreport.pl` command was executed without its expected arguments, and so returned an error message.
- The injected `echo` command was executed, and the supplied string was echoed in the output
- The original argument `29` was executed as a command, which caused an error.

Placing the additional command separator `&` after the injected command is useful because it separates the injected command from whatever follows the injection point. This reduces the chance that what follows will prevent the injected command from executing. 

Inline is adding css styling to an element wherein the css syntax is the value of the style attribute of an element. Hence, inline because it is part of the element in the line. On the other hand, internal css is when CSS code is in the same document but it is in a separate element in the <style></style>. Lastly, the external CSS is the developer puts their CSS code on an external css file and imports it in the HTML. 
