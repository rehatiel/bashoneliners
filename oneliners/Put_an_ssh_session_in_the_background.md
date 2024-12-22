# Put an ssh session in the background

## Command:
```
$ ~^z
```

## Explanation:
Explanation

Normally, ^z (read: ctrl-z) pauses the execution of the current foreground task. That doesn't work in an ssh session, because it is intercepted by the remote shell. ~^z is a special escape character for this case, to pause the ssh session and drop you back to the local shell.
For all escape characters see ~?
The ~ escape character must always follow a newline to be interpreted as special.
See man ssh for more details, search for ESCAPE CHARACTERS

## Limitations:
No limitations specified

