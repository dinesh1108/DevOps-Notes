# Script executable permission

So get into the directory of shell script and change the permission to `755` since the task is about giving the **exeutable permissions** but we need to give the **read and executable permission** then only it will work since script needs read and execuatbale &#x20;



**2. Scripts (e.g., `.sh`, `.py`, `.pl`)**

A script is just a text file containing English-like commands. When you try to "execute" a script (like `./script.sh`), the system actually launches an Interpreter (like `/bin/bash` or `/bin/python`).

* The Interpreter then has to open the file and read the text inside to know what to do.
* If you give Execute permission (`x`) but not Read permission (`r`), the system allows you to _start_ the process, but the Interpreter immediately crashes because it's forbidden from reading the code inside the file.
* Result: `111` (`--x--x--x`) FAILS for scripts because the interpreter cannot read the code.
