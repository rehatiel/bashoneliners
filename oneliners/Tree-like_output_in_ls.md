# Tree-like output in ls

## Command:
```
$ ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/   /' -e 's/-/|/'
```

## Explanation:
Explanation
This one-liner initially does a recursive listing of the current directory: ls -R.
Any output other that the directory names, identified by : at the very end of each line (hence :$), is filtered out: grep ":$".
Finally there's a little of sed magic replacing any hierarchy level (/) with dashes (-).

## Limitations:
Limitations
Works for me with Bash under Linux, Mac OS X, Solaris.

