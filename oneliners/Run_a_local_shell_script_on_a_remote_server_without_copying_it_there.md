# Run a local shell script on a remote server without copying it there

## Command:
```
$ ssh user@server bash < /path/to/local/script.sh
```

## Explanation:
Explanation
Yes this is almost trivial: a simple input redirection, from a local shell script to be executed by bash on the remote server.
The important point being, if you have a complex and very long chain of commands to run on a remote server, it is better to put the commands in a shell script, break the long one-liner to multiple lines for readability and easier debugging.
Replace bash accordingly depending on the language of the script, for example for python:
ssh user@server python < /path/to/local/script.py

## Limitations:
No limitations specified

