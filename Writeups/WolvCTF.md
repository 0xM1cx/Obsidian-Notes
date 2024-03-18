## Made Sense(To be Edited)
Challenge Description:
i couldn't log in to my server so my friend kindly spun up a server to let me test makefiles. at least, they thought i couldn't log in :P
[https://madesense-okntin33tq-ul.a.run.app](https://madesense-okntin33tq-ul.a.run.app)

Upon opening the link we are greeted with this page 

![[Pasted image 20240316213434.png]]

clicking at the `source` you can see that this is a flask application. 
```python
import os
from pathlib import Path
import re
import subprocess
import tempfile
from flask import Flask, request, send_file

app = Flask(__name__)
flag = open('flag.txt').read()
    
def write_flag(path):
    with open(path / 'flag.txt', 'w') as f:
        f.write(flag)

def generate_makefile(name, content, path):
    with open(path / 'Makefile', 'w') as f:
        f.write(f"""
SHELL := /bin/bash
.PHONY: {name}
{name}: flag.txt
\t{content}
""")


@app.route('/', methods=['GET'])
def index():
    return send_file('index.html')
  
@app.route('/src/', methods=['GET'])
def src():
    return send_file(__file__)

# made sense
@app.route('/make', methods=['POST'])
def make():
    target_name = request.form.get('name')
    code = request.form.get('code')
    print(code)
    
    if not re.fullmatch(r'[A-Za-z0-9]+', target_name):
        return 'no'
    if '\n' in code:
        return 'no'
    if re.search(r'flag', code):
        return 'no'

    with tempfile.TemporaryDirectory() as dir:
        run_dir = Path(dir)
        write_flag(run_dir)
        generate_makefile(target_name, code, run_dir)
        sp = subprocess.run(['make'], capture_output=True, cwd=run_dir)
        return f"""
<h1>stdout:</h1>
{sp.stdout}
<h1>stderr:</h1>
{sp.stderr}
    """
app.run('localhost', 8000)
```

Looking the the code we see that when we submit our inputs, the make() will be invoked and the said inputs must NOT satisfy some of the conditions. In the first condition the Target name must only be alphanumeric, in the second condition specifies that the code we put in the text area must not have a new line and must not have a `flag`.
```python
if not re.fullmatch(r'[A-Za-z0-9]+', target_name):
        return 'no'
    if '\n' in code:
        return 'no'
    if re.search(r'flag', code):
        return 'no'
```

Looking further in the following functions it makes a directory in the the servers file system and them makes a flag.txt file. then runs the make command in that temp directory. Given this idea, we need to make the temp file content to spit out the contents of the file. This is easy because the make command will run on the same directory with the flag.txt file. So a simple `cat *` would spit out the contents of all the files in the current directory. After that we get this:
![[Pasted image 20240316225747.png]]

FLAG: `wctf{m4k1ng_vuln3r4b1l1t135}`

## 