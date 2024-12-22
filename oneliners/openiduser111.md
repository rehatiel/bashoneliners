# openiduser111

## Command:
```
$ tty >/dev/null || { urxvt -e /bin/sh -c "tty >/tmp/proc$$; while test x; do sleep 1; done" & while test ! -f /tmp/proc$$; do sleep .1; done; FN=$(cat /tmp/proc$$); rm /tmp/proc$$; exec >$FN 2>$FN <$FN; }
```

## Explanation:
Explanation

We begin by testing if the script is not in a terminal with tty.
If it is not we start a terminal that runs tty and saves it to a filename. $$ was set by the original script and is its PID. That is opened in the background using & and then the original script waits for the filename to appear, then reads and removes it.
Finally, the main command is a special syntax of the bash builtin command exec that contains nothing but redirections (of stdout, stderr, and stdin) so they will apply to every command in the rest of the script file.

## Limitations:
Limitations
If the script is large, say several gigabytes and the system tries to make two copies of the script, twice the size of RAM or memory will be needed for loading it.

rxvt -e will kill any subprocesses at the end

