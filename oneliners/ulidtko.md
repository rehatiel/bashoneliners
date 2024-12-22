# ulidtko

## Command:
```
$ watch () { interrupted=false; trap "interrupted=true" INT; while ! $interrupted; do $*; sleep 1 || interrupted=true; done; }
```

## Explanation:
Explanation
Once I needed a classical watch(1) command, but all I got on Mac OS X was -bash: watch: command not found.
So this is a simple interruptable while loop which can poll anything you like, e.g. watch grep alert /var/log/syslog.

## Limitations:
No limitations specified

