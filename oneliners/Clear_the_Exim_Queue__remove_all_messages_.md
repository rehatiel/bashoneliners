# Clear the Exim Queue (remove all messages)

## Command:
```
$ exim -bp | exiqgrep -i | xargs exim -Mrm
```

## Explanation:
Explanation
Print exim queue, pipe it to exiqgrep to extract message ids, and pass them to exim -Mrm using xargs to remove.

## Limitations:
No limitations specified

