# `tail -f` a file until text is seen

## Command:
```
$ tail -f /path/to/file.log | sed '/^Finished: SUCCESS$/ q'
```

## Explanation:
Explanation
tail -f until this exact line is seen:
Finished: SUCCESS

The exit condition does not have to be an exact line, it could just well be a simple pattern:
... | sed '/Finished/ q'

## Limitations:
No limitations specified

