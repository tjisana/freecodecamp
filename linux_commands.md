### [Linux Command Cheat Sheet](https://www.freecodecamp.org/news/the-linux-commands-handbook/)

`rmdir <>` Used to remove only directories that are _empty_

`find <location> [options]`
e.g.
* `find . -name '*.py'` will find all files with .py extension
* `find ~/Desktop -type d -iname '*.py'` will find all _folders_ with .py extension
* `find ~/Desktop -type f -iname '.py` will find all files with .py extension 
* `find . -iname 'Desktop' -or -iname` allows you to search for two conditions

`ln -s <original> <link>` creates soft links

`tar -zxvf <filename>`
* z (un)zip
* x means ex̲tract files from the archive.
* v means print the filenames v̲erbosely.
* f means the following argument is a f̱ilename.

`alias ll=ls -alph` N.B. this only lasts for the current session. Add this to the ~/.zshrc file to make it permanent

Be careful with quotes if you have variables in the command: if you use double quotes, the variable is resolved at definition time. If you use use single quotes, it's resolved at invocation time. Those 2 are different:

- `alias lsthis="ls $PWD"`

- `alias lscurrent='ls $PWD'`

`cat <file>` print file contents to STD output
`cat file1 file2 > file3` concatenate two files into one

`cat` is often used in combination with the pipe operator `|` to feed a file's content as input to another command: `cat file1 | anothercommand.`

The best use case of `tail` in my opinion is when called with the -f option. It opens the file at the end, and watches for file changes.

Any time there is new content in the file, it is printed in the window. This is great for watching log files, for example:

`tail -f /var/log/system.log`
To exit, press ctrl-C.

You can print the last 10 lines in a file:

`tail -n 10 <filename>`
You can print the whole file content starting from a specific line using + before the line number:

`tail -n +10 <filename>`

`grep <search string> <filename>`
can also be used in conjunction with pipe operator `|` eg `less index.md | grep -n document.getElementById`

`diff <file1> <file2>` tells you the difference between two files

`chown <owner> <file>`

- `chmod u+x <filename>`
- `chmod 777 <filename>`

`basename /Users/flavio/test.txt` will return test.txt

`dirname /Users/flavio/test.txt` will return /Users/flavio/


`env USER=flavio node app.js`
The env command can be used to pass environment variables without setting them on the outer environment (the current shell).

In `python` we use

`import os`

`os.environ` to import system environmental variables.
We may also have a .env file. We can use python's dotenv package to import that file and put the variables in the system's environmental variables.
Finally we can use the linux `env` command to pass an environmental variable to an application
`env KERR=TJ python3` will pass the env variable KERR, value TJ to python3
