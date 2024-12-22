# Write both stdout and stderr to the same file

## Command:
```
$ do_something.sh &> out.log
```

## Explanation:
Explanation
Note: this is not always the same as:
do_something.sh >out.log 2>out.log

Using &> will ensure that the order of lines coming from stdout and stderr is preserved.

## Limitations:
Limitations
This works in /bin/bash and may not work in /bin/sh or other stripped down variants of bash.

