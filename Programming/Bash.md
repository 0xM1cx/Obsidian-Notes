##### Comments
Any text following the `#` is considered a comment.

To find out the full path path of the shell interpreter use this command: `which bash`

##### Variables
Shell variables are created once they are assigned a value. Variable name is case sensitive and can consist of a combination of letters and the underscore. Value assignment is done using the `=` sign. ***Note that no space is permitted on either side of the = sign when initializing variables.***
Example
```Bash
User_Name="Jerry"
UserAge=17
welcomeMessage="Welcome    Jerry"
```

Encapsulating the variable name with `${}` is commonly used rather than the backslash `\` to avoid ambiguity.
```bash
User_Name="Morty"
echo "Welcome ${User_Name}"
```

Encapsulating the variable name with double quotes `""` will preserve any white space value.
```bash
greeting='Hello        world!'
echo $greeting" now with spaces: $greeting"
```

Variables can be assigned with the value of a command output. This is referred to as substitution. Substitution can be done by encapsulating the command with backticks or with `$()`.
```bash
FILELIST=`ls`
FileWithTimeStamp=/tmp/my-dir/file_$(/bin/date +%Y-%m-%d).txt
```

```bash
BIRTHDATE="Jan, 2000"
Presents=10
BIRTHDAY= `date -d "$BIRTHDATE" +%A`
```