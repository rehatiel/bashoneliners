# openiduser16

## Command:
```
$ find . -depth  -type d  -empty -exec rmdir {} \;
```

## Explanation:
Explanation
Recursively remove all empty sub-directories from a directory tree using just find. No need for tac (-depth does that), no need for xargs as the directory contents changes on each call to rmdir. We're not reliant on the rmdir command deleting just empty dirs, -empty does that.

## Limitations:
Limitations
Will make many calls to rmdir without using xargs, which bunches commands into one argument string, which is normally useful, but -empty /could/ end up being more efficient since only empty dirs will be passed to rmdir, so possibly fewer executions in most cases (searching / for example).

