# List open files

## Command:
```
$ lsof -n
```

## Explanation:
Explanation
With the -n flag it will not try to resolve network numbers to host names for network files, making it run a bit faster.
With the -c option you can select processes executing a matching command. And with the -t flag the output will be simply process ids without a header, suitable to use with kill. For example you can kill Google Chrome process gone crazy like this:
kill -HUP $(lsof -n -c /google/i -t)

Here /google/i is a regular expression pattern with case insensitive matching.

## Limitations:
No limitations specified

