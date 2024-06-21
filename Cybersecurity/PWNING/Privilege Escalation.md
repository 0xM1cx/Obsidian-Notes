- **SUID** - it is a special file permission in UNIX and LINUX systems that allows users to execute a file with the permission of the file's owner rather than the permission of the user who is running the file. 


## Binary Exploitation
- If you see the function `gets()`, it is vulnerable to a buffer overflow. This is because this functions does not check if the user input is out of bounds. 

### Tools
- checksec - used to check executable and kernel properties. It helps to identify if a security feature is identified correctly. 
- cyclic - tool is commonly used in the context of exploit development and debugging, particularly for identifying the exact offset of a buffer overflow. This outputs patterns to be used to test the stack. 