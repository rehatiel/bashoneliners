# Run a command and copy its output to clipboard (Mac OSX)

## Command:
```
$ echo "Here comes the output of my failing code" | tee >(pbcopy)
```

## Explanation:
Explanation
Often you need to copy the output of a program for debugging purposes. Cool kids on the block may use pastebin servers. But what if you'd just like to copy-and-paste the output to a web form, say?
This one-liner gives a nice demonstration of process substitution. The stdout is piped to tee for duplication. Rather than dumping the output to a file as in the normal case, the output is piped to pbcopy via a temporary file that the OS conjures up on the fly (/dev/fd/XXX). The end result: you can paste the output wherever you want with Command+V.

## Limitations:
Limitations
This is Mac OSX specific. Use xsel on Linux.

